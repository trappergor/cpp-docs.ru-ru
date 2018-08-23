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
ms.openlocfilehash: 6d282731320ba52299cb0b6f2813f5f42a229b46
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583752"
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
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[Атрибуты параметра](../windows/parameter-attributes.md)  
[first_is](../windows/first-is.md)  
[last_is](../windows/last-is.md)  
[max_is](../windows/max-is.md)  
[length_is](../windows/length-is.md)  