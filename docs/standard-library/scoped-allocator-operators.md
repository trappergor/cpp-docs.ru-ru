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
ms.openlocfilehash: 0dda1415ea875b01c943a0a275122458f399f69c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105884"
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
