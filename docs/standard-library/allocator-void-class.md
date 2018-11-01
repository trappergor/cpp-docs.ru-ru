---
title: Класс allocator&lt;void&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: 5591570527946895d1e0456b23327d7fabc4bef5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646119"
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

## <a name="requirements"></a>Требования

**Заголовок:** \<memory>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
