---
title: Análisis de los resultados de pruebas de carga
ms.date: 10/19/2016
ms.topic: how-to
helpviewer_keywords:
- results, load test
- load test results, accessing
- Load Test Viewer
- load tests, accessing
- load tests, analyzing
- load tests, results
- Load Test Viewer, viewing
ms.assetid: b0a3e694-2894-479b-b270-7e61e9fafacd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b72db87014304dc2b9baf57e05015e53a630c431
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85288538"
---
# <a name="how-to-access-load-test-results-for-analysis"></a>Procedimiento para acceder a los resultados de pruebas de carga para el análisis

Al ejecutar una prueba de carga desde el Editor de pruebas de carga, los resultados de pruebas de carga se abren automáticamente y la prueba de carga en ejecución se muestra en el **Analizador de pruebas de carga**. Al ejecutar una prueba de carga desde la línea de comandos, debe obtener acceso a los resultados de pruebas de carga manualmente.

El resultado de la prueba de carga completada contiene ejemplos de contadores de rendimiento e información de errores que se recopilaron periódicamente de los equipos sometidos a prueba. Se puede recopilar un gran número de muestras de contadores de rendimiento durante la ejecución de pruebas de carga. La cantidad de datos de rendimiento recopilados depende de la duración de la ejecución de pruebas, el intervalo de muestreo, el número de equipos sometidos a prueba, el número de contadores que se recopilan, los recolectores de datos configurados y los niveles de registro. En el caso de una prueba de carga grande, la cantidad de datos de rendimiento recopilados puede ascender fácilmente a varios gigabytes. Para obtener más información, vea [Controladores y agentes de prueba](configure-test-agents-and-controllers-for-load-tests.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-access-a-load-test-result"></a>Para tener acceso al resultado de una prueba de carga

1. En un proyecto de prueba de carga y rendimiento web, abra una prueba de carga.

2. En la barra de herramientas del Editor de pruebas de carga, elija el botón **Abrir y administrar resultados**.

     Aparecerá el cuadro de diálogo **Abrir y administrar resultados**.

3. En **Escriba un nombre de controlador para buscar resultados de pruebas de carga**, seleccione un controlador. Seleccione **\<local> - No controller** para tener acceso a los resultados almacenados localmente.

4. En **Mostrar resultados para la siguiente prueba de carga**, seleccione la prueba de carga cuyos resultados quiere ver. Seleccione **\<Show results for all tests>** para ver todos los resultados de todas las pruebas.

     Si hay resultados de pruebas de carga disponibles, aparecen en la lista **Resultados de pruebas de carga**. Las columnas son **Hora**, **Duración**, **Usuario**, **Resultado**, **Prueba** y **Descripción**. **Prueba** contiene el nombre de la prueba y **Descripción** incluye la descripción opcional que se ha agregado antes de ejecutar la prueba.

    > [!NOTE]
    > Los resultados más recientes aparecen en la parte superior de la lista.

5. En la lista **Resultados de pruebas de carga**, seleccione los resultados de la prueba de carga que desee analizar y elija **Abrir**.

6. Aparecerá el **Analizador de pruebas de carga**. El resultado de prueba de carga seleccionado se mostrará en la vista Resumen. Para más información, consulte [Información general de resumen de resultados de pruebas de carga](../test/load-test-results-summary-overview.md).

     Puede administrar otros aspectos de los resultados de pruebas de carga en el cuadro de diálogo **Abrir y administrar resultados**, que incluye importar, exportar y quitar resultados de pruebas de carga. Para más información, consulte [Administrar resultados de pruebas de carga en el repositorio de resultados de pruebas de carga](../test/manage-load-test-results-in-the-load-test-results-repository.md).

## <a name="see-also"></a>Vea también

- [Analizar los resultados de pruebas de carga](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
