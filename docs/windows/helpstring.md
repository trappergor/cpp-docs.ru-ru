---
title: HelpString | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e661e911cc0dd583f2ce079f8ac047a354fa596f
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570935"
---
# <a name="helpstring"></a>helpstring
Определяет строку символов, используемую для описания элемента, к которому оно применяется.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ helpstring(  
   "string"  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *string*  
 Текст строки справки.  
  
## <a name="remarks"></a>Примечания  
 **Helpstring** атрибут C++ имеет ту же функциональность, что [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [defaultvalue](../windows/defaultvalue.md) пример демонстрирует использование **helpstring**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**интерфейс**, **typedef**, **класс**, метод, свойство|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpFile](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   