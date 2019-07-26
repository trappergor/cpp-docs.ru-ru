---
title: Класс is_trivially_move_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: 324e4a1f1bd3528f09f21c5e485ac814038b7517
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448382"
---
# <a name="istriviallymoveassignable-class"></a>Класс is_trivially_move_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания перемещением.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим тривиальный оператор присваивания перемещения, в противном случае — значение false.

Оператор присваивания перемещения для класса *Ty* является тривиальным, если:

он неявно предоставляется;

у класса *Ty* нет виртуальных функций

класс *Ty* не имеет виртуальных базовых классов

классы всех нестатических элементов данных типа класса имеют тривиальные операторы присваивания перемещением;

классы всех нестатических элементов данных массива типов класса имеют тривиальные операторы присваивания перемещением.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
