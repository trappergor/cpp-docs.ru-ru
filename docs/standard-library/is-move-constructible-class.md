---
title: Класс is_move_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: c83ed4365fd0e73a7daa8b9894c5e85f20387a79
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456106"
---
# <a name="ismoveconstructible-class"></a>Класс is_move_constructible

Проверяет, имеет ли тип конструктор перемещения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Параметры

*T*\
Вычисляемый тип.

## <a name="remarks"></a>Примечания

Предикат типа, который возвращает значение true, если тип *T* может быть создан с помощью операции перемещения. Этот предикат эквивалентен `is_constructible<T, T&&>`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
