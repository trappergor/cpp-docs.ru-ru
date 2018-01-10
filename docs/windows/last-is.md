---
title: "last_is | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.last_is
dev_langs: C++
helpviewer_keywords: last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d7a230299a94ba33a142ca44ebc34981f7201ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="lastis"></a>last_is
Определяет индекс последнего элемента массива для передачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ last_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *выражение*  
 Одно или несколько выражений языка C. Допускаются слоты пустой аргумент.  
  
## <a name="remarks"></a>Примечания  
 **Last_is** языка C++ имеет ту же функциональность, что [last_is](http://msdn.microsoft.com/library/windows/desktop/aa367066) языка MIDL.  
  
## <a name="example"></a>Пример  
 В разделе [first_is](../windows/first-is.md) пример указания фрагмент массива.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Поле в `struct` или **объединение**, интерфейс параметр, метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
