---
title: Класс is_nothrow_move_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: f1f98a6172e37bd72182ccc043ca4612b71675d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447194"
---
# <a name="isnothrowmoveconstructible-class"></a>Класс is_nothrow_move_constructible

Проверяет, имеет ли тип конструктор перемещения **nothrow**.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* имеет nothrow конструктор перемещения, в противном случае он содержит значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
