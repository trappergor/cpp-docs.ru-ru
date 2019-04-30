---
title: Класс is_nothrow_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: c59c3623f9c9548a7b7e59d0c56a2acd4d3883a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383624"
---
# <a name="isnothrowassignable-class"></a>Класс is_nothrow_assignable

Проверяет, является ли значение *из* типа могут быть назначены *для* не будет выдавать известен тип и назначения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Параметры

*Задача*<br/>
Тип объекта, который получает назначение.

*From*<br/>
Тип объекта, который предоставляет значение.

## <a name="remarks"></a>Примечания

Выражение `declval<To>() = declval<From>()` должно иметь правильный формат и быть известно компилятору как не вызывающее исключений. Оба *из* и *для* должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
