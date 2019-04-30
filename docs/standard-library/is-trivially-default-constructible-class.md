---
title: Класс is_trivially_default_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: b35458ca280285eb699c9b12b15b705660299ef2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413415"
---
# <a name="istriviallydefaultconstructible-class"></a>Класс is_trivially_default_constructible

Проверяет, есть ли у типа тривиальный конструктор по умолчанию.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим тривиальный конструктор, в противном случае он содержит значение false.

Конструктор по умолчанию для класса *Ty* является тривиальным если:

- он является конструктором по умолчанию, объявленным неявно;

- Класс *Ty* не имеет виртуальных функций

- Класс *Ty* не имеет виртуальных баз

- все прямые базы класса *Ty* имеют тривиальные конструкторы

- классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы;

- классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
