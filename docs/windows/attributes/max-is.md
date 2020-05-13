---
title: max_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: b4931962febb1e68701aa3fe271e08f3aa8d9238
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166761"
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

## <a name="remarks"></a>Remarks

Атрибут **max_is** C++ имеет те же функциональные возможности, что и атрибут [max_is](/windows/win32/Midl/max-is) MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Поле в **структуре** или **объединении**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|**size_is**|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Пример

Пример указания раздела массива см. в разделе [first_is](first-is.md) .

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)
