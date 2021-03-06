---
title: Referencia de esquemas del archivo del proyecto MSBuild | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, file schema
ms.assetid: d9a68146-1f43-4621-ac78-2c8c3f400936
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 824a6f562638edb04854431c437289f2741c46d9
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "78263112"
---
# <a name="msbuild-project-file-schema-reference"></a>Referencia de esquemas del archivo del proyecto MSBuild

Proporciona una tabla de todos los elementos de esquema XML de MSBuild con los atributos y elementos secundarios disponibles.

 MSBuild utiliza archivos del proyecto para indicar al motor de compilación qué debe compilar y cómo. Los archivos del proyecto de MSBuild son archivos XML que cumplen el esquema XML de MSBuild. En esta sección se documenta el archivo de definición de esquema XML ( *.xsd*) para MSBuild.

El vínculo de esquema de un archivo de proyecto de MSBuild no es necesario en Visual Studio 2017 y versiones posteriores. Si está presente, debe ser ` http://schemas.microsoft.com/developer/msbuild/2003` independientemente de la versión de Visual Studio.

## <a name="msbuild-xml-schema-elements"></a>Elementos de esquema XML de MSBuild

 En la tabla siguiente se enumeran todos los elementos de esquema XML de MSBuild junto con sus elementos secundarios y atributos.

|Elemento|Elementos secundarios|Atributos|
|-------------|--------------------|----------------|
|[Elemento Choose (MSBuild)](../msbuild/choose-element-msbuild.md)|Otherwise<br /><br /> Cuando|--|
|[Elemento Import (MSBuild)](../msbuild/import-element-msbuild.md)|--|Condición<br /><br /> Proyecto|
|[ImportGroup (Elemento)](../msbuild/importgroup-element.md)|Importar|Condición|
|[Elemento Item (MSBuild)](../msbuild/item-element-msbuild.md)|*ItemMetaData*|Condición<br /><br /> Excluir<br /><br /> Incluir<br /><br /> Quitar|
|[Elemento ItemDefinitionGroup (MSBuild)](../msbuild/itemdefinitiongroup-element-msbuild.md)|*Item*|Condición|
|[Elemento ItemGroup (MSBuild)](../msbuild/itemgroup-element-msbuild.md)|*Item*|Condición|
|[Elemento ItemMetadata (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)|*Item*|Condición|
|[Elemento OnError (MSBuild)](../msbuild/onerror-element-msbuild.md)|--|Condición<br /><br /> ExecuteTargets|
|[Elemento Otherwise (MSBuild)](../msbuild/otherwise-element-msbuild.md)|Elegir<br /><br /> ItemGroup<br /><br /> PropertyGroup|--|
|[Elemento Output (MSBuild)](../msbuild/output-element-msbuild.md)|--|Condición<br /><br /> ItemName<br /><br /> PropertyName<br /><br /> TaskParameter|
|[Parameter (Elemento)](../msbuild/parameter-element.md)|--|Salida<br /><br /> ParameterType<br /><br /> Obligatorio|
|[ParameterGroup (Elemento)](../msbuild/parametergroup-element.md)|*Parameter*|--|
|[Elemento Project (MSBuild)](../msbuild/project-element-msbuild.md)|Elegir<br /><br /> Importar<br /><br /> ItemGroup<br /><br /> ProjectExtensions<br /><br /> PropertyGroup<br /><br /> Destino<br /><br /> UsingTask|DefaultTargets<br /><br /> InitialTargets<br /><br /> ToolsVersion<br /><br /> TreatAsLocalProperty<br /><br /> xmlns|
|[Elemento ProjectExtensions (MSBuild)](../msbuild/projectextensions-element-msbuild.md)|--|--|
|[Elemento Property (MSBuild)](../msbuild/property-element-msbuild.md)|--|Condición|
|[Elemento PropertyGroup (MSBuild)](../msbuild/propertygroup-element-msbuild.md)|*Property*|Condición|
|[Elemento Sdk (MSBuild)](../msbuild/sdk-element-msbuild.md)|--|NOMBRE<br /><br /> Versión|
|[Elemento Target (MSBuild)](../msbuild/target-element-msbuild.md)|OnError<br /><br /> *Task*|AfterTargets<br /><br /> BeforeTargets<br /><br /> Condición<br /><br /> DependsOnTargets<br /><br /> Entradas<br /><br /> KeepDuplicateOutputs<br /><br /> NOMBRE<br /><br /> Salidas<br /><br /> Valores devueltos|
|[Elemento Task de Target (MSBuild)](../msbuild/task-element-msbuild.md)|Salida|Condición<br /><br /> ContinueOnError<br /><br /> *Parameter*|
|[Elemento Task de UsingTask (MSBuild)](../msbuild/taskbody-element-msbuild.md)|*Data*|Evaluate|
|[Elemento UsingTask (MSBuild)](../msbuild/usingtask-element-msbuild.md)|ParameterGroup<br /><br /> Tarea|AssemblyFile<br /><br /> AssemblyName<br /><br /> Condición<br /><br /> TaskFactory<br /><br /> TaskName|
|[Elemento When (MSBuild)](../msbuild/when-element-msbuild.md)|Elegir<br /><br /> ItemGroup<br /><br /> PropertyGroup|Condición|

## <a name="see-also"></a>Vea también

- [Referencia de tareas](../msbuild/msbuild-task-reference.md)
- [Condiciones](../msbuild/msbuild-conditions.md)
- [Referencia de MSBuild](../msbuild/msbuild-reference.md)
- [MSBuild](../msbuild/msbuild.md)
