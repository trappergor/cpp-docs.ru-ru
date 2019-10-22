---
title: Класс allocator&lt;void&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: c8d787fe03dfe6f67fb8e228308ec74b6e7f620a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688528"
---
# <a name="allocatorltvoidgt-class"></a>Класс allocator&lt;void&gt;

Специализация распределителя шаблонов класса для типа **void**, определяющая типы, имеющие смысл в этом контексте.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>Заметки

Класс явно специализирует [механизм распределения](../standard-library/allocator-class.md) шаблонов классов для типа **void**. Его конструкторы и оператор присваивания ведут себя так же, как и для шаблона класса, но он определяет только следующие типы:

- [const_pointer](../standard-library/allocator-class.md#const_pointer);

- [pointer](../standard-library/allocator-class.md#pointer);

- [value_type](../standard-library/allocator-class.md#value_type);

- [Повторная привязка](../standard-library/allocator-class.md#rebind), шаблон вложенного класса.
