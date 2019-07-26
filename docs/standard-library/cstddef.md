---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 87d268977ee46112fedce517e66a9e68071863db
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457564"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

Включает заголовок \<стандартной библиотеки C STDDEF. h > и добавляет связанные имена `std` в пространство имен. Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C `std` , объявляются в пространстве имен.

> [!NOTE]
> \<кстддеф > включает тип **Byte** и не включает тип **wchar_t**.

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
Синоним для типа выражения **nullptr** . Хотя адрес **nullptr** не может быть взят, можно получить адрес другого объекта *nullptr_t* , который является левосторонним значением.

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

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
