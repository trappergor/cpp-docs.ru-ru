---
title: Класс is_trivially_move_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_constructible
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
ms.openlocfilehash: 279da956eaff21c39c6e5ca563f26989105f7e74
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448362"
---
# <a name="istriviallymoveconstructible-class"></a>Класс is_trivially_move_constructible

Проверяет, есть ли у типа тривиальный конструктор перемещения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом с тривиальным конструктором перемещения, в противном случае — значение false.

Конструктор перемещения для класса *Ty* является тривиальным, если:

он неявно объявлен;

его типы параметров эквивалентны типам неявного объявления;

у класса *Ty* нет виртуальных функций

класс *Ty* не имеет виртуальных базовых классов

класс не содержит изменчивых нестатических элементов данных;

все прямые базовые классы класса *Ty* имеют тривиальные конструкторы перемещения

классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы перемещения;

классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы перемещения.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
