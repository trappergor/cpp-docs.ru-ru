---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: f1582a4af1c26e1ef85cf0dce8406a4046a8fe8b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222528"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

Включает заголовок стандартной библиотеки C \<stddef.h> и добавляет связанные имена в `std` пространство имен. Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в `std` пространстве имен.

> [!NOTE]
> \<cstddef>включает тип **Byte** и не включает тип **`wchar_t`** .

## <a name="syntax"></a>Синтаксис

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>Пространство имен и макросы

```cpp
namespace std {
    using ptrdiff_t = see definition;
    using size_t = see definition;
    using max_align_t = see definition;
    using nullptr_t = decltype(nullptr);
}

#define NULL  // an implementation-defined null pointer constant
#define offsetof(type, member-designator)
```

### <a name="parameters"></a>Параметры

*ptrdiff_t*\
Определенный реализацией тип целого числа со знаком, который может содержать разность двух индексов в объекте массива.

*size_t*\
Определяемый реализацией целочисленный тип без знака, достаточно большой для хранения размера в байтах любого объекта.

*max_align_t*\
Тип POD, требование выравнивания которого по крайней мере такой же, как и у каждого скалярного типа, а требования выравнивания поддерживаются в каждом контексте.

*nullptr_t*\
Синоним для типа **`nullptr`** выражения. Хотя **`nullptr`** адрес не может быть получен, можно получить адрес другого *nullptr_t* объекта, который является левосторонним значением.

## <a name="byte-class"></a>Класс Byte

```cpp
enum class byte : unsigned char {};

template <class IntType>
    constexpr byte& operator<<=(byte& b, IntType shift) noexcept;
    constexpr byte operator<<(byte b, IntType shift) noexcept;
    constexpr byte& operator>>=(byte& b, IntType shift) noexcept;
    constexpr byte operator>>(byte b, IntType shift) noexcept;

constexpr byte& operator|=(byte& left, byte right) noexcept;
constexpr byte operator|(byte left, byte right) noexcept;
constexpr byte& operator&=(byte& left, byte right) noexcept;
constexpr byte operator&(byte left, byte right) noexcept;
constexpr byte& operator^=(byte& left, byte right) noexcept;
constexpr byte operator^(byte left, byte right) noexcept;
constexpr byte operator~(byte b) noexcept;

template <class IntType>
    IntType to_integer(byte b) noexcept;
```

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
