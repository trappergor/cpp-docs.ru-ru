---
title: is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r классы
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_invocable
- type_traits/std::is_invocable_r
- type_traits/std::is_nothrow_invocable
- type_traits/std::is_nothrow_invocable_r
helpviewer_keywords:
- is_invocable class
- is_invocable
- is_invocable_r class
- is_invocable_r
- is_nothrow_invocable class
- is_nothrow_invocable
- is_nothrow_invocable_r class
- is_nothrow_invocable_r
ms.openlocfilehash: bb5e75a897029ded2e00e491d93d2df41a3e115b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336235"
---
# <a name="isinvocable-isinvocabler-isnothrowinvocable-isnothrowinvocabler-classes"></a>is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r классы

Эти шаблоны определяют, если тип может быть вызван с указанным типам аргументов. `is_invocable_r` и `is_nothrow_invocable_r` также определить, является ли результат вызова можно преобразовать в определенный тип. `is_nothrow_invocable` и `is_nothrow_invocable_r` также определить, если вызов известен не могут вызывать исключения. Добавлен в C ++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Callable, class... Args>
struct is_invocable;

template <class Convertible, class Callable, class... Args>
struct is_invocable_r;

template <class Callable, class... Args>
struct is_nothrow_invocable;

template <class Convertible, class Callable, class... Args>
struct is_nothrow_invocable_r;

// Helper templates
template <class Callable, class... Args>
inline constexpr bool is_invocable_v =
    std::is_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_invocable_r_v =
    std::is_invocable_r<Convertible, Callable, Args...>::value;

template <class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_v =
    std::is_nothrow_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_r_v =
    std::is_nothrow_invocable_r<Convertible, Callable, Args...>::value;
```

### <a name="parameters"></a>Параметры

*Вызываемый*<br/>
Вызываемый тип для запроса.

*Args*<br/>
Типы аргументов для запроса.

*Можно преобразовать*<br/>
Тип результата из *Callable* должно быть преобразуемым в.

## <a name="remarks"></a>Примечания

`is_invocable` Предиката типа содержит значение true, если вызываемый тип *Callable* можно вызывать, используя аргументы *Args* в невычисляемом контексте.

`is_invocable_r` Предиката типа содержит значение true, если вызываемый тип *Callable* можно вызывать, используя аргументы *Args* в невычисляемом контексте для создания результата типом, приводимым к  *Можно преобразовать*.

`is_nothrow_invocable` Предиката типа содержит значение true, если вызываемый тип *Callable* можно вызывать, используя аргументы *Args* в невычисляемом контексте и что такой вызов известно, не к возникновению исключения.

`is_nothrow_invocable_r` Предиката типа содержит значение true, если вызываемый тип *Callable* можно вызывать, используя аргументы *Args* в невычисляемом контексте для создания результата типом, приводимым к  *Можно преобразовать*, и что такой вызов будет известен не исключение.

Каждый из типов *преобразуемыми*, *Callable*и типы в пакете параметров *Args* должно быть полным типом, массив неизвестной границей или ,возможноcvполное**void**. В противном случае поведение предиката не определено.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_invocable.cpp
// compile using: cl /EHsc /std:c++17 std__type_traits__is_invocable.cpp
#include <type_traits>

auto test1(int) noexcept -> int (*)()
{
    return nullptr;
}

auto test2(int) -> int (*)()
{
    return nullptr;
}

int main()
{
    static_assert( std::is_invocable<decltype(test1), short>::value );

    static_assert( std::is_invocable_r<int(*)(), decltype(test1), int>::value ); 
    static_assert( std::is_invocable_r<long(*)(), decltype(test1), int>::value ); // fails

    static_assert( std::is_nothrow_invocable<decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable<decltype(test2), int>::value ); // fails

    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test2), int>::value ); // fails
}
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Вызвать](functional-functions.md#invoke)<br/>
