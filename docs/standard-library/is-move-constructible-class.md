---
title: Класс is_move_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 1b1e450338a123c51b80f40f2369207c8b987cd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383637"
---
# <a name="ismoveconstructible-class"></a>Класс is_move_constructible

Проверяет, имеет ли тип конструктор перемещения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Вычисляемый тип.

## <a name="remarks"></a>Примечания

Тип предиката, результатом которого является значение true, если тип *T* может быть создан с помощью операции перемещения. Этот предикат эквивалентен `is_constructible<T, T&&>`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
