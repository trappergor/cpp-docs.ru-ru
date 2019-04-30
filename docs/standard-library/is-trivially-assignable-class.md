---
title: Класс is_trivially_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_assignable
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
ms.openlocfilehash: eeef85a0b26c25eb745258c7e0e35394f0cab979
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413500"
---
# <a name="istriviallyassignable-class"></a>Класс is_trivially_assignable

Проверяет, можно ли значение типа `From` назначить типу `To`

## <a name="syntax"></a>Синтаксис

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Параметры

*Задача*<br/>
Тип объекта, который получает назначение.

*From*<br/>
Тип объекта, который предоставляет значение.

## <a name="remarks"></a>Примечания

Выражение `declval<To>() = declval<From>()` должно иметь правильный формат и должно быть известно компилятору как не требующее нетривиальных операций. Оба `From` и `To` должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
