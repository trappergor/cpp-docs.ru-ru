---
title: last_is | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.last_is
dev_langs:
- C++
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98527958ba9fdf2c2b53e8b18348cb93d3aed6ad
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016461"
---
# <a name="lastis"></a>last_is
Указывает индекс последнего элемента массива для передачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ last_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *Выражение*  
 Одно или несколько выражений языка. Допускаются слотов пустой аргумент.  
  
## <a name="remarks"></a>Примечания  
 **Last_is** атрибут C++ имеет ту же функциональность, что [last_is](http://msdn.microsoft.com/library/windows/desktop/aa367066) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в разделе [first_is](../windows/first-is.md) пример указания фрагмент массива.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В поле **структуры** или **объединение**, параметр интерфейса, метод интерфейса|  
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