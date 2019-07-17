---
title: любой класс
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: 050276da665ab6ed3eb53d9e65bfea06b88bcbea
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268756"
---
# <a name="any-class"></a>любой класс

Магазины, экземпляр любого типа, удовлетворяющий требованиям конструктор, или он не имеет значения, который является именем состояние класса любого объекта.

Сохраненный экземпляр называется содержащееся значение. Два состояния считаются одинаковыми, если они не должны иметь значения, или оба имеют значение и для автономной значения совпадают.

## <a name="syntax"></a>Синтаксис

```cpp
class any
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[any](#any)|Создает объект типа `any`.|

### <a name="functions"></a>Функции

|||
|-|-|
|[emplace](#emplace)|Задает любое значение.|
|[has_value](#has_value)|Возвращает **true** Если какой-либо имеет значение.|
|[reset](#reset)|Сбрасывает запроса any.|
|[swap](#swap)|Меняет местами два любых объектов.|
|[type](#type)|Возвращает тип any.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор=](#op_eq)|Приводит к замене всех с копией другого любое.|

## <a name="any"></a> Любой

Создает объект типа `any`. Также содержит деструктор.

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a> emplace-

Задает любое значение.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a> has_value

Возвращает **true** Если какой-либо имеет значение.

```cpp
bool has_value() const noexcept;
```

## <a name="op_eq"></a> оператор =

Приводит к замене всех с копией другого любое.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Все, копируемый в каких-либо.

## <a name="reset"></a> Сброс

Сбрасывает запроса any.

```cpp
void reset() noexcept;
```

## <a name="swap"></a> Swap

Меняет местами два любых объектов.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a> Тип

Возвращает тип any.

```cpp
const type_info& type() const noexcept;
```
