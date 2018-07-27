---
title: pointer_default | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee904f9243cf642d3a942d4bc323f5ec381b0480
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877466"
---
# <a name="pointerdefault"></a>pointer_default
Указывает атрибут указатель по умолчанию для всех указателей, за исключением указателей верхнего уровня, которые отображаются в списках параметров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *значение*  
 Значение, которое описывает тип указателя: **ptr**, `ref`, или **уникальный**.  
  
## <a name="remarks"></a>Примечания  
 **Pointer_default** языка C++ имеет ту же функциональность, что [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) языка MIDL.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [defaultvalue](../windows/defaultvalue.md) для приведен пример использования **pointer_default**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
