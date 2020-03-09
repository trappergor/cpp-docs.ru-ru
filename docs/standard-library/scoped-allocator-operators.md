---
title: Операторы &lt;scoped_allocator&gt;
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 071fc3b73cd3378b110d6d412bb7575e35a77478
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876339"
---
# <a name="ltscoped_allocatorgt-operators"></a>Операторы &lt;scoped_allocator&gt;

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить их неравенство.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Параметры

*left*\
Левый объект `scoped_allocator_adaptor`.

*справа*\
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

*left*\
Левый объект `scoped_allocator_adaptor`.

*справа*\
Правой объект `scoped_allocator_adaptor`.

### <a name="return-value"></a>Возвращаемое значение

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>См. также раздел

[<scoped_allocator>](../standard-library/scoped-allocator.md)
