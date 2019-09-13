---
title: length_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: 4f4bfe233e3228c50aee734de4ad979c38a55fda
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514524"
---
# <a name="length_is"></a>length_is

Указывает число передаваемых элементов массива.

## <a name="syntax"></a>Синтаксис

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Одно или несколько выражений языка C. Пустые слоты аргументов разрешены.

## <a name="remarks"></a>Примечания

Атрибут **length_is** C++ имеет те же функциональные возможности, что и атрибут [length_is](/windows/win32/Midl/length-is) MIDL.

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
[last_is](last-is.md)<br/>
[size_is](size-is.md)