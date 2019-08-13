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
ms.openlocfilehash: f664df6493a7ee20361d49531a930aeb810d3d2a
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957148"
---
# <a name="optional-class"></a>необязательный класс

Класс `optional<T>` шаблона описывает объект, который может или не может содержать значение типа `T`, известное как *содержащее значение*.

Если экземпляр `optional<T>` содержит значение, вложенное значение выделяется в пределах хранилища `optional` объекта в области, подходящей по отношению к типу `T`. При преобразовании в `bool`результат принимает `true` значение, если объект `false`содержит значения; в противном случае —. `optional<T>`

Тип `T` вложенного объекта не должен быть [in_place_t](in-place-t-struct.md) или [nullopt_t](nullopt-t-structure.md). `T`должен быть *можно уничтожить*, то есть его деструктор должен освободить все собственные ресурсы и не может вызывать исключения.

`optional` Класс является новым в c++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class optional
{
    using value_type = T;
};

template<class T> optional(T) -> optional<T>;
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
| **Конструкторы и деструктор** | |
|[optional](#optional) | Создает объект типа `optional`. |
|[~ Необязательный](#optional-destructor) | Уничтожает объект типа `optional`. |
| **Присваивание** | |
| [оператор=](#op_eq) | Заменяет экземпляр на копию другого `optional`объекта. `optional` |
| [emplace](#op_eq) | Инициализирует содержащееся значение с указанными аргументами. |
| **Swap** | |
| [swap](#swap) | Меняет местами вложенное значение или пустое состояние на `optional`другое. |
| **Наблюдателей** | |
| [has_value](#has_value) | Возвращает, содержит `optional` ли объект значение. |
| [value](#value) | Возвращает содержащееся значение. |
| [value_or](#value_or) | Возвращает содержащееся значение или альтернативу, если значение отсутствует. |
| [оператор>](#op_as) | Ссылается на значение `optional` , содержащееся в объекте. |
| [оператор*](#op_mem) | Ссылается на значение `optional` , содержащееся в объекте. |
| [operator bool](#op_bool) | Возвращает, содержит `optional` ли объект значение. |
| **Модификаторы** | |
| [reset](#reset) | Сбрасывает объект `optional` , уничтожая любое из содержащихся в нем значений. |

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

*RHS*\
Объект `optional` для копирования или перемещения, создающий содержимое, из которого строится значение.

*i_list*\
Список инициализаторов для создания содержащего значения из.

*args*\
Список аргументов для создания содержащего значения из.

### <a name="remarks"></a>Примечания

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;`Эти конструкторы создают объект `optional` , который не содержит значения.

`constexpr optional(const optional& rhs);`Конструктор копий инициализирует содержащееся значение из содержащегося в аргументе значения. Она определяется как удаленная, `is_copy_constructible_v<T>` если не имеет значения true и является тривиальной, если `is_trivially_copy_constructible_v<T>` имеет значение true.

`constexpr optional(optional&& rhs) noexcept;`Конструктор перемещения инициализирует вложенное значение, перемещая из содержащего его значения аргумента. Он не участвует в разрешении перегрузки, если `is_move_constructible_v<T>` не имеет значение true и является тривиальным, если `is_trivially_move_constructible_v<T>` имеет значение true.

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);`Direct инициализирует вложенное значение как при использовании аргументов `std::forward<Args>(args)`. Этот конструктор имеет `constexpr` значение, `T` если используется `constexpr`конструктор. Он не участвует в разрешении перегрузки, если `is_constructible_v<T, Args...>` не имеет значение true.

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);`Direct инициализирует вложенное значение как при использовании аргументов `i_list, std::forward<Args>(args)`. Этот конструктор имеет `constexpr` значение, `T` если используется `constexpr`конструктор. Он не участвует в разрешении перегрузки, если `is_constructible_v<T, initializer_list<U>&, Args&&...>` не имеет значение true.

`template <class U = T> explicit constexpr optional(U&& rhs);`Direct инициализирует вложенное значение, как при `std::forward<U>(v)`использовании. Этот конструктор имеет `constexpr` значение, `T` если используется `constexpr`конструктор. Он не участвует в разрешении перегрузки, если `is_constructible_v<T, U&&>` не `is_same_v<remove_cvref_t<U>, optional>` имеет значение true, а `is_same_v<remove_cvref_t<U>, in_place_t>` и и имеет значение false.

`template <class U> explicit optional(const optional<U>& rhs);`Если *RHS* содержит значение, то прямые инициализируют содержащееся значение из содержащегося в аргументе значения. Он не `is_constructible_v<T, const U&>` участвует в разрешении перегрузки, если только не имеет `is_constructible_v<T, const optional<U>&&>`значение `is_convertible_v<optional<U>&, T>`true `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`а `is_constructible_v<T, optional<U>&>`, `is_convertible_v<const optional<U>&&, T>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>`,,,,, и все равно false.

`template <class U> explicit optional(optional<U>&& rhs);`Если *RHS* содержит значение, то при использовании функции `std::move(*rhs)`Direct инициализирует содержащееся значение. Он не `is_constructible_v<T, U&&>` участвует в разрешении перегрузки, если только не имеет `is_constructible_v<T, const optional<U>&&>`значение `is_convertible_v<optional<U>&, T>`true `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`а `is_constructible_v<T, optional<U>&>`, `is_convertible_v<const optional<U>&&, T>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>`,,,,, и все равно false.

## <a name="optional-destructor"></a>~ Необязательный деструктор

Уничтожает любое нетривиальное можно уничтожитьное значение, если оно присутствует, путем вызова его деструктора.

```cpp
~optional();
```

### <a name="remarks"></a>Примечания

Если `T` является тривиальным можно уничтожить, то `optional<T>` он также тривиальным можно уничтожить.

## <a name="op_eq"></a>Оператор =

Заменяет вложенное значение `optional` объекта на копию или перемещение из другого `optional` содержащего значения.

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

Разыменование вложенного значения `optional` объекта.

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="op_mem"></a>станции

Разыменование вложенного значения `optional` объекта.

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="op_bool"></a>bool, оператор

Сообщает, `optional` содержит ли объект содержащееся значение.

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

## <a name="see-also"></a>См. также

[\<Необязательный >](optional.md)
