---
title: Класс is_trivially_copy_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: aa6d6b19ae2bd5d6967c57db61c5697c0c6153e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630520"
---
# <a name="istriviallycopyconstructible-class"></a>Класс is_trivially_copy_constructible

Проверяет, есть ли у типа тривиальный конструктор копии.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является классом, имеющим тривиальный конструктор копии, в противном случае он содержит значение false.

Конструктор копии для класса *T* является тривиальным, если он неявно объявляется, класс *T* не имеет виртуальных функций или виртуальных базовых классов, все прямые базовые классы класса *T* имеют тривиальные конструкторы копирования; классы всех нестатических членов типа класса имеют тривиальные конструкторы копий и классы всех нестатических членов массива типов класса имеют тривиальные конструкторы копирования.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
