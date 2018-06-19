---
title: Операторы &lt;scoped_allocator&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
dev_langs:
- C++
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 66cf60dd3d70719fe42645215b1190c9fb752ff3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854682"
---
# <a name="ltscopedallocatorgt-operators"></a>Операторы &lt;scoped_allocator&gt;

|||
|-|-|
|[оператор!=](#op_neq)|[оператор==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить их неравенство.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Параметры

`left` Слева `scoped_allocator_adaptor` объекта.

`right` Право `scoped_allocator_adaptor` объекта.

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

`left` Слева `scoped_allocator_adaptor` объекта.

`right` Право `scoped_allocator_adaptor` объекта.

### <a name="return-value"></a>Возвращаемое значение

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>См. также

[<scoped_allocator>](../standard-library/scoped-allocator.md)<br/>
