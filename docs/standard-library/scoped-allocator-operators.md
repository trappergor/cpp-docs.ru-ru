---
title: Операторы &lt;scoped_allocator&gt;
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 7c9f2c3a2425bf3ac6e62ce7fcecfe9315c3e04e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512467"
---
# <a name="ltscopedallocatorgt-operators"></a>Операторы &lt;scoped_allocator&gt;

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить их неравенство.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Параметры

*left*<br/>
Левый объект `scoped_allocator_adaptor`.

*right*<br/>
Правой объект `scoped_allocator_adaptor`.

### <a name="return-value"></a>Возвращаемое значение

`!(left == right)`

## <a name="op_eq_eq"></a> operator==

Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить, равны ли они.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Параметры

*left*<br/>
Левый объект `scoped_allocator_adaptor`.

*right*<br/>
Правой объект `scoped_allocator_adaptor`.

### <a name="return-value"></a>Возвращаемое значение

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>См. также

[<scoped_allocator>](../standard-library/scoped-allocator.md)<br/>
