---
title: Класс allocator&lt;void&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0585396d2cacc2bb41abf364e3d01ca81629146f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953558"
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
