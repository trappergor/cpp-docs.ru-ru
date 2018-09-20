---
title: length_is | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.length_is
dev_langs:
- C++
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aff0c2e2600f7f0c300d1043c9844104fd70c4e4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415340"
---
# <a name="lengthis"></a>length_is

Указывает количество элементов массива для передачи.

## <a name="syntax"></a>Синтаксис

```cpp
[ length_is(
   "expression"
) ]
```

### <a name="parameters"></a>Параметры

*Выражение*<br/>
Одно или несколько выражений языка. Допускаются слотов пустой аргумент.

## <a name="remarks"></a>Примечания

**Length_is** атрибут C++ имеет ту же функциональность, что [length_is](/windows/desktop/Midl/length-is) описании атрибута MIDL.

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

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](../windows/parameter-attributes.md)<br/>
[first_is](../windows/first-is.md)<br/>
[max_is](../windows/max-is.md)<br/>
[last_is](../windows/last-is.md)<br/>
[size_is](../windows/size-is.md)  