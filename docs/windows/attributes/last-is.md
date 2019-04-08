---
title: last_is (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.last_is
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
ms.openlocfilehash: 39b35b218f3402839d956c4da0a00f290fe5d595
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033291"
---
# <a name="lastis"></a>last_is

Указывает индекс последнего элемента массива для передачи.

## <a name="syntax"></a>Синтаксис

```cpp
[ last_is("expression") ]
```

### <a name="parameters"></a>Параметры

*выражение*<br/>
Одно или несколько выражений языка. Допускаются слотов пустой аргумент.

## <a name="remarks"></a>Примечания

**Last_is** атрибут C++ имеет ту же функциональность, что [last_is](/windows/desktop/Midl/last-is) описании атрибута MIDL.

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
[length_is](length-is.md)<br/>
[size_is](size-is.md)