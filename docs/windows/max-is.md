---
title: max_is | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.max_is
dev_langs:
- C++
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3fae7ee95255d72d2799a5913821606f770e2b3b
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608434"
---
# <a name="maxis"></a>max_is
Определяет максимальное значение для индекса допустимым массивом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ max_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *Выражение*  
 Одно или несколько выражений языка. Допускаются слотов пустой аргумент.  
  
## <a name="remarks"></a>Примечания  
 **Max_is** атрибут C++ имеет ту же функциональность, что [max_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) описании атрибута MIDL.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В поле **структуры** или **объединение**, параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**size_is**|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Пример  
 См. в разделе [first_is](../windows/first-is.md) пример указания фрагмент массива.  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   