---
title: Filtrar para importar los resultados de pruebas de carga en un repositorio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load test results, importing
- Load Test Results Repository
- load tests, importing results
ms.assetid: a955b3d2-c8ad-40dd-8ea3-9f1a271e1eed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: efbd13bf7ada237dc21bc5b2b6a186b13a52fd06
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55932423"
---
# <a name="how-to-import-load-test-results-into-a-repository"></a>Filtrar para importar los resultados de pruebas de carga en un repositorio

Cuando se ejecutan pruebas de carga, cualquier información recolectada durante una ejecución se almacena en el repositorio de resultados de pruebas de carga. El repositorio de resultados de pruebas de carga contiene datos de los contadores de rendimiento e información acerca de los errores que se hayan producido. Para obtener más información, vea [Administrar resultados de pruebas de carga en el repositorio de resultados de pruebas de carga](../test/manage-load-test-results-in-the-load-test-results-repository.md).

Puede administrar los resultados de pruebas de carga desde el Editor de pruebas de carga con el cuadro de diálogo **Abrir y administrar resultados de pruebas de carga**. Puede abrir, importar, exportar y quitar los resultados de pruebas de carga.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-import-results-into-a-repository"></a>Para importar resultados en un repositorio

1.  En un proyecto de prueba de carga y rendimiento web, abra una prueba de carga.

2.  En la barra de herramientas insertada, elija **Abrir y administrar resultados**.

     Se muestra el cuadro de diálogo **Abrir y administrar resultados de pruebas de carga**.

3.  En **Escriba un nombre de controlador para buscar resultados de pruebas de carga**, seleccione un controlador. Seleccione **\<local>** para acceder a los resultados almacenados en local.

     Si hay resultados de pruebas de carga disponibles, aparecen en la lista **Resultados de pruebas de carga**. Las columnas son **Hora**, **Duración**, **Usuario**, **Resultado**, **Prueba** y **Descripción**. **Prueba** contiene el nombre de la prueba y **Descripción** incluye la descripción opcional que se ha agregado antes de ejecutar la prueba.

4.  Elija **Importar**.

     Aparecerá el cuadro de diálogo **Importar resultados de la prueba de carga**.

5.  En el cuadro **Nombre de archivo**, escriba el nombre de un archivo de resultados de pruebas almacenado y, luego, elija **Abrir**.

     \- o -

     Busque el archivo y elija **Abrir**.

    > [!NOTE]
    > El archivo de resultados de pruebas almacenado que especifique en este paso deberá haberse creado ejecutando la operación de exportación.

     Los resultados se importan y aparecen en la lista **Resultados de pruebas de carga**.

## <a name="see-also"></a>Vea también

- [Administrar resultados de pruebas de carga en el repositorio de resultados de pruebas de carga](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Analizar los resultados de pruebas de carga](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Cómo: Exportar los resultados de pruebas de carga desde un repositorio](../test/how-to-export-load-test-results-from-a-repository.md)