---
title: Interfaces del proveedor de símbolos | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, symbol handler
- symbol handler, interfaces
- symbol handler, evaluating variables
ms.assetid: 4201f10e-c9f7-4b38-bb45-40fe0082d5bf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e98d792da99cafb670f64f572a1d6e3e4597f8e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715732"
---
# <a name="symbol-provider-interfaces"></a>Interfaces de proveedor de símbolos
Los siguientes son las Interfaces de control de símbolos para el [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)].

## <a name="discussion"></a>Discusión
 Estas interfaces se usan para evaluar las variables en una pila de llamadas durante el modo de interrupción. Se implementan solo para proveedores de símbolos en tiempo de ejecución de common language (SP).

|Interfaz|Implementado por|Descripción|
|---------------|--------------------|-----------------|
|[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)|SP|Representa la dirección de un elemento.|
|[IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)|SP|Representa la dirección de un elemento, que proporciona acceso al identificador de proceso.|
|[IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)|SP|Representa un símbolo de matriz o tipo de matriz.|
|[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)|SP|Representa un símbolo de la clase o el tipo de clase.|
|[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)|SP|Representa un proveedor de símbolos de COM + con métodos que son específicos de código administrado.|
|[IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)|SP|Representa un proveedor de símbolos de COM + con métodos que son específicos de código administrado y extiende el **IDebugComPlusSymbolProvider**.|
|[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)|SP|Representa un tipo que es un contenedor para otros tipos o los símbolos o símbolos.|
|[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)|SP|Representa un atributo personalizado que se puede conectar a un símbolo.|
|[IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)|SP|Representa una consulta para los atributos personalizados en un tipo o método.|
|[IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)|SP|Proporciona acceso a los atributos personalizados en un símbolo.|
|[IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)|SP|La interfaz base para cualquier tipo que se puede determinar en tiempo de ejecución.|
|[IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)|SP|Representa un campo dinámico para un [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) objeto.|
|[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)|SP|Representa un tipo de enumeración.|
|[IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)|Sp|Amplía los tipos de campos disponibles para admitir tipos genéricos de código administrado.|
|[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)|SP|La clase base para todos los campos; Representa una descripción de un símbolo o el tipo.|
|[IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)|SP|Representa la definición de un campo para un tipo genérico de código administrado.|
|[IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)|SP|Representa una instancia de un campo para un tipo genérico de código administrado.|
|[IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)|SP|Representa un parámetro para un tipo genérico de código administrado.|
|[IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)|SP|Representa un método.|
|[IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)|SP|Representa un modificador opcional de depuración.|
|[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)|SP|Representa un puntero.|
|[IDebugPrimitiveTypeField](../../../extensibility/debugger/reference/idebugprimitivetypefield.md)|SP|Representa un valor de enumeración de tipo primitivo de una [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) interfaz.|
|[IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)|SP|Representa una propiedad de una clase de código administrado que se puede obtener o establecer.|
|[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)|SP|Representa un proveedor de símbolos que proporciona los símbolos y tipos.|
|[IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)|SP|Representa un proveedor de símbolos con acceso directo a las interfaces de símbolos de metadatos y core.|
|[IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)|SP|Representa la capacidad para crear un campo que representa un tipo.|
|[IDebugTypeFieldBuilder2](../../../extensibility/debugger/reference/idebugtypefieldbuilder2.md)|SP|Extiende la **IDebugTypeFieldBuilder** para poder crear tipos de matriz.|
|[IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)|SP|Representa una colección de [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objetos.|
|[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)|SP|Representa una colección de [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) objetos.|
|[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)|SP|Representa una colección de [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objetos.|

## <a name="see-also"></a>Vea también
- [Referencia de API](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)