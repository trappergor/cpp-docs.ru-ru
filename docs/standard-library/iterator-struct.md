---
title: Структура iterator | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9cd414e2e6f23cb2fe44e6de4b5f53b33ef3555
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857887"
---
# <a name="iterator-struct"></a>Структура iterator

Пустая базовая структура, используемая для обеспечения правильной работы определяемого пользователем класса итератора с **iterator_trait**.

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

- `value_type` (синоним для параметра-шаблона **Type**).

- `difference_type` (синоним для параметра-шаблона `Distance`).

- `distance_type` (синоним для параметра-шаблона `Distance`)

- `pointer` (синоним для параметра-шаблона `Pointer`).

- `reference` (синоним для параметра-шаблона `Reference`).

Обратите внимание, что `value_type` не должен быть типом константы, даже если **указатель** указывает на объект **типа** const и ссылка обозначает объект **типа** const.

## <a name="example"></a>Пример

См. раздел [iterator_traits](../standard-library/iterator-traits-struct.md) с примером того, как объявить и использовать типы в базовом классе итератора.

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
