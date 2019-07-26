---
title: Класс is_trivially_copy_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: c0019257a032d3becc268513336ed59e58a2e1d5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448001"
---
# <a name="istriviallycopyassignable-class"></a>Класс is_trivially_copy_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания копии.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является классом, имеющим тривиальный оператор присваивания копии, в противном случае — значение false.

Конструктор присваивания для класса *t* является тривиальным, если он неявно предоставляется, но у класса *t* нет виртуальных функций, но у класса *t* нет виртуальных базовых классов, а классы всех нестатических элементов данных типа класса имеют тривиальный оператор присваивания операторы и классы всех нестатических элементов данных массива типов класса имеют тривиальные операторы присваивания.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
