---
title: last_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.last_is
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
ms.openlocfilehash: 4745d4eb59fd2adb79937b34184081dbbd0814fb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514521"
---
# <a name="last_is"></a>last_is

Задает индекс последнего передаваемого элемента массива.

## <a name="syntax"></a>Синтаксис

```cpp
[ last_is("expression") ]
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Одно или несколько выражений языка C. Пустые слоты аргументов разрешены.

## <a name="remarks"></a>Примечания

Атрибут **last_is** C++ имеет те же функциональные возможности, что и атрибут [last_is](/windows/win32/Midl/last-is) MIDL.

## <a name="example"></a>Пример

Пример указания раздела массива см. в разделе [first_is](first-is.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Поле в **структуре** или **объединении**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)