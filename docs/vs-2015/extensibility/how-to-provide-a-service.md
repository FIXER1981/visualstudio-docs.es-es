---
title: 'Cómo: proporcionar un servicio | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, providing
ms.assetid: 12bc1f12-47b1-44f6-b8db-862aa88d50d1
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 565a8a91797c826b6419dc5a8488d7d3baf9cddc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "90842719"
---
# <a name="how-to-provide-a-service"></a>Provisión de un servicio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Un VSPackage puede proporcionar servicios que otros VSPackages pueden utilizar. Para proporcionar un servicio, un VSPackage debe registrar el servicio con Visual Studio y agregar el servicio.  
  
 La <xref:Microsoft.VisualStudio.Shell.Package> clase implementa <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> y <xref:System.ComponentModel.Design.IServiceContainer> . <xref:System.ComponentModel.Design.IServiceContainer> contiene métodos de devolución de llamada que proporcionan servicios a petición.  
  
 Para obtener más información acerca de los servicios, consulte [Service Essentials](../extensibility/internals/service-essentials.md) .  
  
> [!NOTE]
> Cuando un VSPackage está a punto de descargarse, Visual Studio espera hasta que se hayan entregado todas las solicitudes de servicios que proporciona un VSPackage. No permite nuevas solicitudes para estos servicios. No debe llamar explícitamente al <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> método para revocar un servicio durante la descarga.  
  
#### <a name="implementing-a-service"></a>Implementación de un servicio  
  
1. Cree un proyecto VSIX (**archivo/nuevo/proyecto/Visual C#/usaría/Proyecto VSIX**).  
  
2. Agregue un VSPackage al proyecto. Seleccione el nodo del proyecto en el **Explorador de soluciones** y haga clic en **Agregar/nuevo elemento/visual C# elementos/extensibilidad/paquete de Visual Studio**.  
  
3. Para implementar un servicio, debe crear tres tipos:  
  
   - Una interfaz que describe el servicio. Muchas de estas interfaces están vacías, es decir, no tienen ningún método.  
  
   - Una interfaz que describe la interfaz de servicio. Esta interfaz incluye los métodos que se van a implementar.  
  
   - Una clase que implementa el servicio y la interfaz de servicio.  
  
     En el ejemplo siguiente se muestra una implementación muy básica de los tres tipos. El constructor de la clase de servicio debe establecer el proveedor de servicios.  
  
   ```csharp  
   public class MyService : SMyService, IMyService  
   {  
       private Microsoft.VisualStudio.OLE.Interop.IServiceProvider serviceProvider;  
       private string myString;  
       public MyService(Microsoft.VisualStudio.OLE.Interop.IServiceProvider sp)  
       {  
           Trace.WriteLine(  
                  "Constructing a new instance of MyService");  
           serviceProvider = sp;  
       }  
       public void Hello()  
       {  
           myString = "hello";  
       }  
       public string Goodbye()  
       {  
          return "goodbye";  
       }  
   }  
   public interface SMyService  
   {  
   }  
   public interface IMyService  
   {  
       void Hello();  
       string Goodbye();  
   }  
  
   ```  
  
### <a name="registering-a-service"></a>Registrar un servicio  
  
1. Para registrar un servicio, agregue el <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> al VSPackage que proporciona el servicio. Este es un ejemplo:  
  
    ```csharp  
    [ProvideService(typeof(SMyService))]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [Guid(VSPackage1.PackageGuidString)]  
    public sealed class VSPackage1 : Package  
    {. . . }  
    ```  
  
     Este atributo se registra `SMyService` con Visual Studio.  
  
    > [!NOTE]
    > Para registrar un servicio que reemplaza a otro servicio con el mismo nombre, use <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute> . Tenga en cuenta que solo se permite una invalidación de un servicio.  
  
### <a name="adding-a-service"></a>Agregar un servicio  
  
1. 1.  En el inicializador de VSPackage, agregue el servicio y agregue un método de devolución de llamada para crear los servicios. Este es el cambio que se realizará en el <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> método:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
    . . .  
    }  
    ```  
  
2. Implemente el método de devolución de llamada, que debe crear y devolver el servicio, o null si no se puede crear.  
  
    ```  
    private object CreateService(IServiceContainer container, Type serviceType)  
    {  
        if (typeof(SMyService) == serviceType)  
            return new SMyService(this);  
        return null;  
    }  
    ```  
  
    > [!NOTE]
    > Visual Studio puede rechazar una solicitud para proporcionar un servicio. Lo hace si otro VSPackage ya proporciona el servicio.  
  
3. Ahora puede obtener el servicio y usar sus métodos. Lo mostraremos en el inicializador, pero puede obtener el servicio en cualquier lugar en el que desee usar el servicio.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
  
        MyService myService = (MyService) this.GetService(typeof(SMyService));  
        myService.Hello();  
        string helloString = myService.myString;  
  
        base.Initialize();  
    }  
    ```  
  
     El valor de `helloString` debe ser "Hello".  
  
## <a name="see-also"></a>Consulte también  
 [Cómo: obtener un servicio](../extensibility/how-to-get-a-service.md)   
 [Uso y suministro de servicios](../extensibility/using-and-providing-services.md)   
 [Conceptos básicos del servicio](../extensibility/internals/service-essentials.md)
