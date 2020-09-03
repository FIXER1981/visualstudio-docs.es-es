---
title: Introducción con Python | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-python
ms.topic: conceptual
ms.assetid: 33f4f6fb-0ae4-4234-9df2-531f2d3af17f
caps.latest.revision: 13
author: kraigb
ms.author: kraigb
manager: jillfra
ms.openlocfilehash: 97d60fe31f838c4cc497701f4560dc426ebc1cc9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80543974"
---
# <a name="getting-started-with-python"></a>Introducción a Python
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

El Herramientas de Python para Visual Studio (PTVS) es un complemento gratuito de [código abierto](https://github.com/Microsoft/ptvs) para Visual Studio que ofrece una experiencia de desarrollo de Python eficaz.  
  
## <a name="python-the-language"></a>Lenguaje de Python
  
Python es un lenguaje de programación popular que utilizan muchas universidades, científicos, scripts de aplicaciones, programadores ocasionales y desarrolladores profesionales, trabajando en aplicaciones, sitios web y servicios en la nube.

Como lenguaje de programación, Python es:
  
- Confiable.
- Suele ser útil para generar scripts de programas rápidos, scripting de aplicaciones, aplicaciones de escritorio, servidores Web, servicios web y informática científica.
- Fácil de aprender y con un diseño adecuado para promover una codificación correcta (numerosas universidades lo usan para cursos de introducción a la programación).
- Estilos de programación flexibles, funcionales y orientados a objetos.
- De código abierto y gratuito.
- Se ejecuta correctamente en todos los sistemas operativos principales.  
- Compatible con muchas bibliotecas gratuitas, útiles y bien diseñadas.  
- Es compatible con gran cantidad de documentación, ejemplos y una sólida comunidad de desarrolladores.  

Para obtener más información sobre el lenguaje, empiece con [Python para principiantes](https://www.python.org/about/gettingstarted/) en Python.org.

Para instalar Python, visite [https://www.python.org/download/](https://www.python.org/download/) .

## <a name="python-tools-for-visual-studio"></a>Python Tools para Visual Studio
  
El Herramientas de Python para Visual Studio, que puede instalar desde [VisualStudio.com](https://www.visualstudio.com/explore/python-vs), proporciona las siguientes características:  
  
- Compatibilidad con varios intérpretes: distintas versiones de CPython, IronPython e IPython  
- Un sistema de proyectos que selecciona implícitamente una estructura de carpetas de código Python y también permite control explícito para que pueda identificar el código de la aplicación, el de prueba, las páginas web, JavaScript, los scripts de compilación y demás.  
- Plantillas de proyecto de consola, web, Azure, datos científicos y otros tipos de proyectos.    
- El SDK de Azure para Python (consulte a continuación)    
- Características de edición avanzada y comprensión de código, incluyendo usar color de sintaxis, autocompletado en el código y las bibliotecas, ayuda para las firmas, vista de clases, Ir a definición, Buscar todas las referencias, refactorización y mucho más.    
- Una ventana interactiva (REPL)
- IPython con visualizaciones de datos.
- Compatibilidad con IronPython y .NET/WPF.    
- Depuración enriquecida sin un proyecto de Visual Studio, la capacidad de adjuntar a un ejecutable existente, depuración en modo mixto, depuración remota en Windows/Linux/Mac y depuración en la ventana interactiva.   
- Herramientas de generación de perfiles.  
- Herramientas de pruebas.  
  
Los siguientes recursos le ayudarán a empezar:

- [Guía de instalación](https://github.com/Microsoft/PTVS/wiki/PTVS-Installation)    
- [Introducción y vídeos Deep Dive cortos](https://www.youtube.com/playlist?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)  
- Demostración de instalación y características (27 minutos)]( https://www.youtube.com/watch?v=JNNAOypc6Ek)  
- [Documentación](https://github.com/Microsoft/PTVS/wiki)  

Tenga en cuenta que Visual Studio no proporciona en la actualidad los medios para crear un ejecutable independiente mediante Python, lo que básicamente significa que se trata de un programa con un intérprete de Python incrustado. Pero hay varias formas dentro de la comunidad de Python para hacerlo, como se describe en [StackOverflow](https://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency). CPython también se puede insertar en una aplicación nativa, como se describe en la entrada de blog [Using CPython's Embeddable Zip File](https://devblogs.microsoft.com/python/cpython-embeddable-zip-file/) (Uso del archivo Zip insertable de CPython).
  
## <a name="building-ui-with-python"></a>Compilar interfaz de usuario con Python  

La oferta principal para compilar una interfaz de usuario con Python es el [proyecto de Qt](https://www.qt.io/qt-for-application-development/), con enlaces para Python conocido como [PySide (el enlace oficial)](https://wiki.qt.io/PySide) (vea también [descargas de PySide](https://download.qt.io/official_releases/pyside/.)) y [PyQt](https://wiki.python.org/moin/PyQt). En la actualidad, la compatibilidad con Python en Visual Studio no incluye herramientas específicas para el desarrollo de la interfaz de usuario.

## <a name="azure-sdk-for-python"></a>SDK de Azure para Python
  
El SDK de Azure para Python, que es compatible con Windows, Mac y Linux, facilita el uso y la administración de los servicios de Microsoft Azure. Consulte los siguientes recursos para obtener más información: 

- Para instalar el SDK, use el [Índice de paquetes de Python](https://pypi.python.org/pypi/azure) o siga [Instalar Python y el SDK](/azure/developer/python/azure-sdk-install) en la documentación de Azure. 
- [El SDK de Azure SDK para el Centro de desarrolladores de Python](https://azure.microsoft.com/develop/python/) dispone de numerosos recursos de ayuda, desde instalación hasta documentación con tutoriales.  A continuación se indican algunos aspectos destacados:  
- Guías de ayuda y procedimientos:
  - [Storage Blob](https://azure.microsoft.com/develop/python/how-to-guides/blob-service/)  
  - [Cola de almacenamiento](https://azure.microsoft.com/develop/python/how-to-guides/queue-service/)  
  - [Tabla de almacenamiento](https://azure.microsoft.com/develop/python/how-to-guides/table-service/)  
  - [Colas de Service Bus](https://azure.microsoft.com/develop/python/how-to-guides/service-bus-queues/)
  - [Temas y suscripciones de Service Bus](https://azure.microsoft.com/develop/python/how-to-guides/service-bus-topics/) 
  - [Administración de servicios](https://azure.microsoft.com/develop/python/how-to-guides/service-management/)  

## <a name="scientific-computing"></a>Ciencia computacional

Además de todas las bibliotecas de datos científicos de Python, Python Tools para Visual Studio admite IPython y blocs de notas de IPython, que se pueden hospedar en Azure.

Se recomienda obtener IPython y las bibliotecas informáticas científicas (matplotlib, scipy, numpy, etc.) de la [Universidad de California en Irvine](https://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy-stack).  
  
## <a name="see-also"></a>Consulte también  

[Introducción con PTVS: configuración de Visual Studio](../python/getting-started-with-ptvs-setting-up-visual-studio.md) 
 [Introducción con PTVS: Start Coding (Projects)](../python/getting-started-with-ptvs-start-coding-projects.md) 
 [Introducción con PTVS: editar código](../python/getting-started-with-ptvs-editing-code.md) 
 [Introducción con PTVS: depuración](../python/getting-started-with-ptvs-debugging.md) 
 [Introducción con PTVS: Python interactivo](../python/getting-started-with-ptvs-interactive-python.md) 
 [Introducción con PTVS: compilar un sitio web en Azure](../python/getting-started-with-ptvs-building-a-website-in-azure.md)
