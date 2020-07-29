---
title: '&lt;&gt;функции span'
ms.date: 05/28/2020
f1_keywords:
- span/std::span::as_bytes
- span/std::as_writable_bytes
helpviewer_keywords:
- std::span [C++], as_writable_bytes
- std::as_bytes [C++]
ms.openlocfilehash: f51c99d2f2a051a07cefcb985fdb46340fefb3ee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217445"
---
# <a name="ltspangt-functions"></a>&lt;&gt;функции span

\<span>Заголовок содержит следующие функции, не являющиеся членами, которые работают с объектами **span** .

| **Функции, не являющиеся членами** | **Описание** |
|-|-|
|[as_bytes](#as_bytes) | Возвращает доступное только для чтения представление объектного представления элементов в диапазоне. |
|[as_writable_bytes](#as_writable_bytes) | Возвращает представление объектного представления элементов в диапазоне, доступное для чтения и записи. |

## <a name="as_bytes"></a>`as_bytes`

Возвращает доступное только для чтения представление объектного представления элементов в диапазоне.

```cpp
template <class T, size_t Extent>
auto as_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>Параметры

*T*\
Тип элементов в диапазоне.

*Экстент*\
Количество элементов в диапазоне (если известно во время компиляции), в противном случае `dynamic_extent` указывающее, что число элементов неизвестно до времени выполнения.

*#d0*\
Диапазон, для которого необходимо получить необработанное представление.

### <a name="return-value"></a>Возвращаемое значение

Объект в `span<const byte, S>` первый элемент, хранящийся в диапазоне, где `S` —`{reinterpret_cast<const std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = std::as_bytes(mySpan);
}
```

## <a name="as_writable_bytes"></a>`as_writable_bytes`

Если `T` нет **`const`** , получает представление для чтения и записи представления необработанного байта элементов в диапазоне.

```cpp
template <class T, size_t Extent>
auto as_writable_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>Параметры

*T*\
Тип элементов в диапазоне.

*Экстент*\
Количество элементов в диапазоне (если известно во время компиляции), в противном случае `dynamic_extent` указывающее, что число элементов неизвестно до времени выполнения.

*#d0*\
Диапазон, для которого необходимо получить необработанное представление.

### <a name="return-value"></a>Возвращаемое значение

Объект в `span<byte, S>` первый элемент, хранящийся в диапазоне, где `S` —`{reinterpret_cast<std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = as_writable_bytes(mySpan);
}
```

## <a name="see-also"></a>См. также раздел

[\<span>](span.md)
