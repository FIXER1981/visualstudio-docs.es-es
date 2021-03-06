---
title: 'Cómo: usar AsyncPackage para cargar VSPackages en segundo plano | Microsoft Docs'
ms.date: 11/15/2016
ms.topic: conceptual
ms.assetid: dedf0173-197e-4258-ae5a-807eb3abc952
caps.latest.revision: 9
ms.author: gregvanl
ms.openlocfilehash: f59838913ed3f9bc6679336393f6db9181291e3d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68204026"
---
# <a name="how-to-use-asyncpackage-to-load-vspackages-in-the-background"></a>Uso de AsyncPackage para cargar VSPackages en segundo plano
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La carga e inicialización de un paquete de VS puede dar lugar a e/s de disco. Si dicha e/s se produce en el subproceso de la interfaz de usuario, puede provocar problemas de capacidad de respuesta. Para solucionar este tema, Visual Studio 2015 presentó la  <xref:Microsoft.VisualStudio.Shell.AsyncPackage> clase que habilita la carga de paquetes en un subproceso en segundo plano.  
  
## <a name="creating-an-asyncpackage"></a>Creación de un AsyncPackage  
 Puede empezar creando un proyecto de VSIX (**archivo/nuevo/proyecto/Visual C#/extensibilidad/Proyecto VSIX**) y agregando un VSPackage al proyecto (haga clic con el botón derecho en el proyecto y **agregue/nuevo elemento/elemento C#/extensibilidad/paquete de Visual Studio**). Después, puede crear los servicios y agregarlos al paquete.  
  
1. Derive el paquete de <xref:Microsoft.VisualStudio.Shell.AsyncPackage> .  
  
2. Si va a proporcionar servicios cuya consulta puede hacer que el paquete se cargue:  
  
    Para indicar a Visual Studio que el paquete es seguro para la carga en segundo plano y para participar en este comportamiento, <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> debe establecer la propiedad **AllowsBackgroundLoading** en true en el constructor de atributos.  
  
   ```csharp  
   [PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]  
  
   ```  
  
    Para indicar a Visual Studio que es seguro crear una instancia del servicio en un subproceso en segundo plano, debe establecer la <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttributeBase.IsAsyncQueryable%2A> propiedad en true en el <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> constructor.  
  
   ```csharp  
   [ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]  
  
   ```  
  
3. Si va a cargar a través de contextos de la interfaz de usuario, debe especificar **PackageAutoLoadFlags. BackgroundLoad** para <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> o el valor (0X2) en las marcas escritas como el valor de la entrada de carga automática del paquete.  
  
   ```csharp  
   [ProvideAutoLoad(UIContextGuid, PackageAutoLoadFlags.BackgroundLoad)]  
  
   ```  
  
4. Si tiene trabajo de inicialización asincrónica, debe invalidar <xref:Microsoft.VisualStudio.Shell.AsyncPackage.InitializeAsync%2A> . Quite el método **Initialize ()** proporcionado por la plantilla VSIX. (El método **Initialize ()** de **AsyncPackage** está sellado). Puede usar cualquiera de los <xref:Microsoft.VisualStudio.Shell.AsyncPackage.AddService%2A> métodos para agregar servicios asincrónicos al paquete.  
  
    Nota: para llamar **base.InitializeAsync ()**, puede cambiar el código fuente a:  
  
   ```csharp  
   await base.InitializeAsync(cancellationToken, progress);  
   ```  
  
5. Debe tener cuidado de no realizar llamadas RPC (quitar llamada a procedimiento) del código de inicialización asincrónico (en **InitializeAsync**). Esto puede ocurrir cuando se llama a <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> directa o indirectamente.  Cuando se requieren cargas de sincronización, el subproceso de la interfaz de usuario se bloqueará mediante <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> . El modelo de bloqueo predeterminado deshabilita las RPC. Esto significa que, si intenta usar una RPC de las tareas asincrónicas, se interbloqueará si el subproceso de la interfaz de usuario está esperando a que se cargue el paquete. La alternativa general es serializar el código en el subproceso de la interfaz de usuario, si es necesario, mediante algo como el **generador de tareas**que se puede unir <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> o algún otro mecanismo que no usa una RPC.  No use **ThreadHelper. Generic. Invoke** o bloquee normalmente el subproceso de llamada en espera para llegar al subproceso de la interfaz de usuario.  
  
    Nota: debe evitar el uso de **GetService** o **QueryService** en el método **InitializeAsync** . Si tiene que usarlos, deberá cambiar primero al subproceso de la interfaz de usuario. La alternativa es usar <xref:Microsoft.VisualStudio.Shell.AsyncServiceProvider.GetServiceAsync%2A> desde **AsyncPackage** (convirtiéndolo en <xref:Microsoft.VisualStudio.Shell.Interop.IAsyncServiceProvider> ).  
  
   C#: creación de un AsyncPackage:  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]       
[ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]   
public sealed class TestPackage : AsyncPackage   
{   
    protected override Task InitializeAsync(System.Threading.CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)   
    {               
        this.AddService(typeof(SMyTestService), CreateService, true);   
        return Task.FromResult<object>(null);   
    }   
}  
```  
  
## <a name="convert-an-existing-vspackage-to-asyncpackage"></a>Convertir un VSPackage existente en AsyncPackage  
 La mayor parte del trabajo es el mismo que la creación de un nuevo **AsyncPackage**. Debe seguir los pasos 1 a 5 anteriores. También debe tener especial precaución en lo siguiente:  
  
1. No olvide quitar la invalidación de **inicialización** que tenía en el paquete.  
  
2. Evitar interbloqueos: podría haber RPC ocultas en el código que ahora se producen en un subproceso en segundo plano. Debe asegurarse de que, si va a realizar una RPC (por ejemplo, **GetService**), debe (1) cambiar al subproceso principal o (2) usar la versión asincrónica de la API si existe una (por ejemplo, **GetServiceAsync**).  
  
3. No cambie entre subprocesos con demasiada frecuencia. Intente localizar el trabajo que puede producirse en un subproceso en segundo plano. Esto reduce el tiempo de carga.  
  
## <a name="querying-services-from-asyncpackage"></a>Consultar servicios desde AsyncPackage  
 Un **AsyncPackage** puede no cargarse de forma asincrónica dependiendo del llamador. Por ejemplo,  
  
- Si el llamador llama a **GetService** o **QueryService** (ambas API sincrónicas) o  
  
- Si el llamador llamó a **IVsShell:: LoadPackage** (o **IVsShell5:: LoadPackageWithContext**) o  
  
- La carga se desencadena mediante un contexto de la interfaz de usuario, pero no especificó que el mecanismo de contexto de la interfaz de usuario pueda cargarse de forma asincrónica  
  
  después, el paquete se cargará sincrónicamente.  
  
  Tenga en cuenta que el paquete todavía tiene una oportunidad (en su fase de inicialización asincrónica) para trabajar fuera del subproceso de la interfaz de usuario, aunque el subproceso de la interfaz de usuario se bloqueará para la finalización de ese trabajo. Si el autor de la llamada usa **IAsyncServiceProvider** para consultar el servicio de forma asincrónica, la carga y la inicialización se realizarán de forma asincrónica suponiendo que no se bloqueen inmediatamente en el objeto de tarea resultante.  
  
  C#: Cómo consultar el servicio de forma asincrónica:  
  
```csharp  
using Microsoft.VisualStudio.Shell;   
using Microsoft.VisualStudio.Shell.Interop;   
  
IAsyncServiceProvider asyncServiceProvider = Package.GetService(typeof(SAsyncServiceProvider)) as IAsyncServiceProvider;   
IMyTestService testService = await ayncServiceProvider.GetServiceAsync(typeof(SMyTestService)) as IMyTestService;  
```
