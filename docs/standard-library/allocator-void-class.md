---
title: Класс allocator&lt;void&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: 7ac7fbaa8c50eb13457271cf96ddc3412733c833
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245870"
---
# <a name="allocatorltvoidgt-class"></a>Класс allocator&lt;void&gt;

Специализация класса шаблона allocator для ввода **void**, определение типов, которые имеют смысл в данном контексте.

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

Этот класс явно специализирует класс шаблона [распределителя](../standard-library/allocator-class.md) для типа **void**. Его конструкторы и оператор присваивания ведут себя так же, как для класса шаблона, но он определяет только следующие типы:

- [const_pointer](../standard-library/allocator-class.md#const_pointer);

- [pointer](../standard-library/allocator-class.md#pointer);

- [value_type](../standard-library/allocator-class.md#value_type);

- [rebind](../standard-library/allocator-class.md#rebind), вложенный класс шаблона.
