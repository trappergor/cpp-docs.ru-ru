---
title: size_is | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.size_is
dev_langs:
- C++
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8dbb3bfbf61c4ad7303c6cee272e14fc91bc9656
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011859"
---
# <a name="sizeis"></a>size_is
Укажите объем памяти, выделенной для размера указатели, размер указателей на указатели по размеру и одно - или многомерные массивы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ size_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *Выражение*  
 Размер памяти, выделенной для размера указателей.  
  
## <a name="remarks"></a>Примечания  
 **Size_is** атрибут C++ имеет ту же функциональность, что [size_is](http://msdn.microsoft.com/library/windows/desktop/aa367164) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [first_is](../windows/first-is.md) пример указания фрагмент массива.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В поле **структуры** или **объединение**, параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|`max_is`|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [max_is](../windows/max-is.md)   
 [length_is](../windows/length-is.md)   