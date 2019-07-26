---
title: Структура iterator
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 64c9be76cb92d818e40714dd141ded3a8cc17c8a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455623"
---
# <a name="iterator-struct"></a>Структура iterator

Пустая базовая структура, используемая, чтобы гарантировать, что определяемый пользователем класс итератора правильно работает с `iterator_trait`s.

## <a name="syntax"></a>Синтаксис

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Примечания

Данная структура-шаблон используется как базовый тип для всех итераторов. Она определяет типы членов

- `iterator_category` (синоним для параметра-шаблона `Category`).

- `value_type` (синоним для параметра-шаблона `Type`).

- `difference_type` (синоним для параметра-шаблона `Distance`).

- `distance_type` (синоним для параметра-шаблона `Distance`)

- `pointer` (синоним для параметра-шаблона `Pointer`).

- `reference` (синоним для параметра-шаблона `Reference`).

Обратите `value_type` внимание, что не должен быть константным `pointer` типом, даже если точки в объекте **const** `Type` и Reference обозначают объект **const** `Type`.

## <a name="example"></a>Пример

См. раздел [iterator_traits](../standard-library/iterator-traits-struct.md) с примером того, как объявить и использовать типы в базовом классе итератора.

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
