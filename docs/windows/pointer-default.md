---
title: "pointer_default | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b55bf95c7abdffe8dd0a0e0071d86f06baad344e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
