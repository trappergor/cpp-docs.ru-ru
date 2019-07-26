---
title: Класс is_nothrow_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: 9ee8b5f97c92b6eb378db40f93696e5e6c554205
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456020"
---
# <a name="isnothrowassignable-class"></a>Класс is_nothrow_assignable

Проверяет, может ли значение *из* типа быть присвоено *типу,* и известно, что присваивание не вызывается.

## <a name="syntax"></a>Синтаксис

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Параметры

*Кому*\
Тип объекта, который получает назначение.

*От*\
Тип объекта, который предоставляет значение.

## <a name="remarks"></a>Примечания

Выражение `declval<To>() = declval<From>()` должно иметь правильный формат и быть известно компилятору как не вызывающее исключений. И *от* , и *до* должны быть полными типами, **void**или массивами неизвестной привязки.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
