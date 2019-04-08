---
title: length_is (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: 1de168606b57c801bc3dc1fb9aee76eb6f3d54c8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039914"
---
# <a name="lengthis"></a>length_is

Указывает количество элементов массива для передачи.

## <a name="syntax"></a>Синтаксис

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>Параметры

*выражение*<br/>
Одно или несколько выражений языка. Допускаются слотов пустой аргумент.

## <a name="remarks"></a>Примечания

**Length_is** атрибут C++ имеет ту же функциональность, что [length_is](/windows/desktop/Midl/length-is) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [first_is](first-is.md) пример указания фрагмент массива.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В поле **структуры** или **объединение**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[last_is](last-is.md)<br/>
[size_is](size-is.md)