---
title: Класс is_trivially_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47fabb7120cc13eeca38bc9d06428f686fc9f1b9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955570"
---
# <a name="istriviallyassignable-class"></a>Класс is_trivially_assignable

Проверяет, можно ли значение типа `From` назначить типу `To`

## <a name="syntax"></a>Синтаксис

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Параметры

Тип объекта, который получает назначение.

От типа объекта, который предоставляет значение.

## <a name="remarks"></a>Примечания

Выражение `declval<To>() = declval<From>()` должно иметь правильный формат и должно быть известно компилятору как не требующее нетривиальных операций. Оба `From` и `To` должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
