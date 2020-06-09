---
title: Класс allocator&lt;void&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: af29c70dca56b1e68eef3614357269c587a77ec9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623681"
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

## <a name="remarks"></a>Примечания

Класс явно специализирует [механизм распределения](allocator-class.md) шаблонов классов для типа **void**. Его конструкторы и оператор присваивания ведут себя так же, как и для шаблона класса, но он определяет только следующие типы:

- [const_pointer](allocator-class.md#const_pointer);

- [указатель](allocator-class.md#pointer).

- [value_type](allocator-class.md#value_type).

- [Повторная привязка](allocator-class.md#rebind), шаблон вложенного класса.
