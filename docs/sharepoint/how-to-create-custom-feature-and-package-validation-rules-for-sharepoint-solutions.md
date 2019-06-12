---
title: 'Soluciones de SharePoint: Crear características personalizadas, las reglas de validación de paquetes'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a10118a0c83f9e17e32efd293a9a824e38a0942a
ms.sourcegitcommit: cc5fd59e5dc99181601b7db8b28d7f8a83a36bab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66835936"
---
# <a name="how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions"></a>Procedimiento Crear paquetes y características personalizado reglas de validación para las soluciones de SharePoint
  Puede crear reglas de validación personalizadas para comprobar el paquete de solución generado por Visual Studio. Puede realizar la validación completa en una característica completa o el paquete seleccionando **validar** en el menú contextual de un paquete o una característica en el **PackagingExplorer**. Al agregar nuevas características o elementos de proyecto de SharePoint al proyecto para determinar si el paquete o la característica sería un estado válido, se realiza una validación parcial.

### <a name="to-create-a-custom-package-validation-rule"></a>Para crear una regla de validación de paquete personalizado

1. Cree un proyecto de biblioteca de clases.

2. Agregue referencias a los siguientes ensamblados:

    - Microsoft.VisualStudio.SharePoint

    - System.ComponentModel.Composition

3. Cree una clase que implementa una de las interfaces siguientes:

    - Para crear una regla de validación del paquete, implemente el <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> interfaz.

    - Para crear una regla de validación de características, implemente el <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> interfaz.

4. Agregue el <xref:System.ComponentModel.Composition.ExportAttribute> a la clase. Este atributo permite que Visual Studio detecte y cargue su regla de validación. Pase el <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> o <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> tipo al constructor del atributo.

## <a name="example"></a>Ejemplo
 En el ejemplo de código siguiente se muestra cómo crear una regla de validación de característica personalizada.

 [!code-vb[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/VisualBasic/featurevalidation/extension/customvalidationrule.vb#1)]
 [!code-csharp[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/CSharp/featurevalidation/extension/customfeaturevalidationrule.cs#1)]

## <a name="compile-the-code"></a>Compilar el código
 Este ejemplo requiere referencias a los ensamblados siguientes:

- Microsoft.VisualStudio.SharePoint.

- System.ComponentModel.Composition.

## <a name="deploy-the-extension"></a>Implementar la extensión
 Para implementar la extensión, cree un [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] paquete de extensión (VSIX) para el ensamblado y otros archivos que desea distribuir con la extensión. Para obtener más información, consulte [herramientas de implementación de extensiones de SharePoint en Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Vea también
- [Ampliar la implementación y empaquetado de SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
