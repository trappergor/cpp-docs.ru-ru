---
title: необязательный класс
ms.date: 11/04/2016
f1_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
helpviewer_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
ms.openlocfilehash: d9c4bf5356e6ff163ecdf7e1a80bc55453d59003
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689147"
---
# <a name="optional-class"></a>необязательный класс

Шаблон класса `optional<T>` описывает объект, который может или не может содержать значение типа `T`, известное как *вложенное значение*.

Если экземпляр `optional<T>` содержит значение, вложенное значение выделяется в хранилище объекта `optional` в области, подходящей для типа `T`. При преобразовании `optional<T>` в `bool`результат будет `true`, если объект содержит значение. в противном случае это `false`.

Тип вложенного объекта `T` не должен быть [in_place_t](in-place-t-struct.md) или [nullopt_t](nullopt-t-structure.md). `T` должны быть *можно уничтожить*, то есть его деструктор должен освободить все ресурсы и не может вызывать исключения.

Класс `optional` является новым в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class optional
{
    using value_type = T;
};

template<class T> optional(T) -> optional<T>;
```

## <a name="members"></a>Members

### <a name="constructors"></a>Конструкторы

|||
|-|-|
| **Конструкторы и деструктор** | |
|[optional](#optional) | Создает объект типа `optional`. |
|[~ Необязательный](#optional-destructor) | Уничтожает объект типа `optional`. |
| **Назначение** | |
| [operator=](#op_eq) | Заменяет `optional` копией другого `optional`. |
| [emplace](#op_eq) | Инициализирует содержащееся значение с указанными аргументами. |
| **Swap** | |
| [swap](#swap) | Меняет местами содержащий значение или пустое состояние на другое `optional`. |
| **Наблюдателей** | |
| [has_value](#has_value) | Возвращает, содержит ли объект `optional` значение. |
| [значение](#value) | Возвращает содержащееся значение. |
| [value_or](#value_or) | Возвращает содержащееся значение или альтернативу, если значение отсутствует. |
| [оператор->](#op_as) | Ссылается на содержащееся значение объекта `optional`. |
| [оператор*](#op_mem) | Ссылается на содержащееся значение объекта `optional`. |
| [operator bool](#op_bool) | Возвращает, содержит ли объект `optional` значение. |
| **Модификаторы** | |
| [reset](#reset) | Сбрасывает `optional` путем уничтожения любого содержащегося значения. |

## <a name="has_value"></a>has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional"></a>Необязательный конструктор

Создает объект типа `optional`.

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t nullopt) noexcept;
constexpr optional(const optional& rhs);
constexpr optional(optional&& rhs) noexcept;

template <class... Args>
constexpr explicit optional(in_place_t, Args&&... args);

template <class U, class... Args>
constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);

template <class U = T>
explicit constexpr optional(U&& rhs);

template <class U>
explicit optional(const optional<U>& rhs);

template <class U>
explicit optional(optional<U>&& rhs);
```

### <a name="parameters"></a>Параметры

\ *RHS*
`optional` для копирования или перемещения Создайте значение из.

*i_list*\
Список инициализаторов для создания содержащего значения из.

*args*\
Список аргументов для создания содержащего значения из.

### <a name="remarks"></a>Примечания

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;` эти конструкторы создают `optional`, не содержащий значения.

`constexpr optional(const optional& rhs);` конструктор копий Инициализирует значение, содержащееся в значении аргумента. Он определяется как **Удаленный** , если только `is_copy_constructible_v<T>` не имеет значения true, и это тривиальный, если `is_trivially_copy_constructible_v<T>` имеет значение true.

`constexpr optional(optional&& rhs) noexcept;` конструктор Move инициализирует вложенное значение, перемещая из содержащего его значения аргумента. Он не участвует в разрешении перегрузки, если только `is_move_constructible_v<T>` не имеет значения true, и это тривиальный вариант, если `is_trivially_move_constructible_v<T>` имеет значение true.

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);` Direct инициализирует вложенное значение, как при использовании аргументов `std::forward<Args>(args)`. Этот конструктор `constexpr`, если используется конструктор `T` `constexpr`. Он не участвует в разрешении перегрузки, если только `is_constructible_v<T, Args...>` не имеет значение true.

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);` Direct инициализирует вложенное значение, как при использовании аргументов `i_list, std::forward<Args>(args)`. Этот конструктор `constexpr`, если используется конструктор `T` `constexpr`. Он не участвует в разрешении перегрузки, если только `is_constructible_v<T, initializer_list<U>&, Args&&...>` не имеет значение true.

`template <class U = T> explicit constexpr optional(U&& rhs);` Direct инициализирует вложенное значение как при использовании `std::forward<U>(v)`. Этот конструктор `constexpr`, если используется конструктор `T` `constexpr`. Он не участвует в разрешении перегрузки, если только `is_constructible_v<T, U&&>` не имеет значение true, а `is_same_v<remove_cvref_t<U>, in_place_t>` и `is_same_v<remove_cvref_t<U>, optional>` имеют значение false.

`template <class U> explicit optional(const optional<U>& rhs);` если *RHS* содержит значение, то прямые инициализируют вложенное значение из содержащегося в аргументе значения. Он не участвует в разрешении перегрузки, если только `is_constructible_v<T, const U&>` не имеет значение true, а `is_constructible_v<T, optional<U>&>`, `is_constructible_v<T, optional<U>&&>`, `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`, `is_convertible_v<optional<U>&, T>`, `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`и `is_convertible_v<const optional<U>&&, T>` имеют значение false.

`template <class U> explicit optional(optional<U>&& rhs);` если *RHS* содержит значение, то объект Direct инициализирует содержащееся значение, как при использовании `std::move(*rhs)`. Он не участвует в разрешении перегрузки, если только `is_constructible_v<T, U&&>` не имеет значение true, а `is_constructible_v<T, optional<U>&>`, `is_constructible_v<T, optional<U>&&>`, `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`, `is_convertible_v<optional<U>&, T>`, `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`и `is_convertible_v<const optional<U>&&, T>` имеют значение false.

## <a name="optional-destructor"></a>~ Необязательный деструктор

Уничтожает любое нетривиальное можно уничтожитьное значение, если оно присутствует, путем вызова его деструктора.

```cpp
~optional();
```

### <a name="remarks"></a>Примечания

Если `T` тривиально можно уничтожить, `optional<T>` также тривиальным можно уничтожить.

## <a name="op_eq"></a>Оператор =

Заменяет вложенное значение `optional` копией или перемещением из другого `optional` содержащего значения.

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional& rhs);
optional& operator=(optional&&) noexcept( /* see below */ );

template <class U = T>
    optional& operator=(U&&);

template <class U>
optional& operator=(const optional<U>&);

template <class U>
    optional& operator=(optional<U>&&);

template <class... Args>
T& emplace(Args&&...);

template <class U, class... Args>
T& emplace(initializer_list<U>, Args&&...);
```

## <a name="op_as"></a>Оператор->

Отменяет ссылку на вложенное значение объекта `optional`.

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="op_mem"></a>станции

Отменяет ссылку на вложенное значение объекта `optional`.

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="op_bool"></a>bool, оператор

Сообщает, содержит ли объект `optional` содержащееся значение.

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a>перезапуск

Фактически вызывает деструктор вложенного объекта, если он есть, и задает для него неинициализированное состояние.

```cpp
void reset() noexcept;
```

## <a name="swap"></a>позиции

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a>значений

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a>value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>См. также:

[\<необязательных >](optional.md)
