---
title: default_delete структуры
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: e9e1fcc68539e55486f4ea27e6dd5c49bed11fdf
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269266"
---
# <a name="defaultdelete-struct"></a>default_delete структуры

Стандартный объект функции, выполняет операцию деления (`operator/`) к своим аргументам.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>Требования

**Заголовок:** \<memory>

**Пространство имен:** std

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[default_delete](#default_delete)|Конструктор для объектов типа `default_delete`.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator()](#op_paren)|Оператор ссылки для доступа к `default_delete`.|

## <a name="default_delete"></a> default_delete

Конструктор для объектов типа `default_delete`.

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="op_paren"></a> Operator()

Оператор ссылки для доступа к `default_delete`.

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>См. также

[\<memory>](../standard-library/memory.md)
