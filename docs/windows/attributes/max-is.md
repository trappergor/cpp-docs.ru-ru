---
title: max_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: f2e6db997891817620c1b2c1f70cb310818dd346
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514429"
---
# <a name="max_is"></a>max_is

Задает максимальное значение для допустимого индекса массива.

## <a name="syntax"></a>Синтаксис

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Одно или несколько выражений языка C. Пустые слоты аргументов разрешены.

## <a name="remarks"></a>Примечания

Атрибут **max_is** C++ имеет те же функциональные возможности, что и атрибут [max_is](/windows/win32/Midl/max-is) MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Поле в **структуре** или **объединении**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|**size_is**|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Пример

Пример указания раздела массива см. в разделе [first_is](first-is.md) .

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)