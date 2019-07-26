---
title: Класс is_nothrow_move_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: 7f1ccdba11f62fcbeaf54162f80f0717feaa2fa1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455865"
---
# <a name="isnothrowmoveconstructible-class"></a>Класс is_nothrow_move_constructible

Проверяет, имеет ли тип конструктор перемещения **nothrow**.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* имеет конструктор перемещения "Throw", в противном случае — значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
