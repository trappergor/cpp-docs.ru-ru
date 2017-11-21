---
title: "max_is | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.max_is
dev_langs: C++
helpviewer_keywords: max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 74b5badf3b65ecbc9842202bdc5bcfc31b5b189f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="maxis"></a>max_is
Задает максимальное значение для индекса массива допустимым.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ max_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *выражение*  
 Одно или несколько выражений языка C. Допускаются слоты пустой аргумент.  
  
## <a name="remarks"></a>Примечания  
 **Max_is** языка C++ имеет ту же функциональность, что [max_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) языка MIDL.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Поле в `struct` или **объединение**, интерфейс параметр, метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**size_is**|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Пример  
 В разделе [first_is](../windows/first-is.md) пример указания фрагмент массива.  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
