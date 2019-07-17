---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 15d13a3af35cb41950df8aeba0c86d779e701ddb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244450"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

Включает заголовок стандартной библиотеки C, \<stddef.h > и добавляет связанные имена в `std` пространства имен. Включение этого заголовка гарантирует, что имена, объявленные с внешней компоновкой в заголовке стандартной библиотеки C, объявляются в `std` пространства имен.

> [!NOTE]
> \<cstddef > включает тип **байтов** и не включает тип **wchar_t**.

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
Определяемое реализацией целочисленный тип, который может содержать различие двух индексов в объекте массива со знаком.

*size_t*\
Тип определяемого реализацией целое число без знака, достаточное для хранения размер в байтах любого объекта.

*max_align_t*\
Тип POD, требование к выравниванию по крайней мере значительной, как и для каждого скалярного типа, и, требование к выравниванию поддерживается в любом контексте.

*nullptr_t*\
Синоним для типа **nullptr** выражение. Несмотря на то что **nullptr** адрес не может быть выполнено, адресом другого *nullptr_t* объект, который является ссылкой lvalue следует выполнить.

## <a name="byte-class"></a>Класс байтов

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

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
