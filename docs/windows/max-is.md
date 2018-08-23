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
ms.openlocfilehash: fc4d8486fe48841ae37ad0ceb41f0da7cfd62c5e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596258"
---
# <a name="maxis"></a>max_is

Определяет максимальное значение для индекса допустимым массивом.

## <a name="syntax"></a>Синтаксис

```cpp
[ max_is(
   "expression"
) ]
```

### <a name="parameters"></a>Параметры

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
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[Атрибуты параметра](../windows/parameter-attributes.md)  
[first_is](../windows/first-is.md)  
[last_is](../windows/last-is.md)  
[length_is](../windows/length-is.md)  
[size_is](../windows/size-is.md)  