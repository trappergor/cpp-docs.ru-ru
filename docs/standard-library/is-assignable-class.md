---
title: Класс is_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: b1357bf8c5ad4dfd5035855e34a8fd6a7ed73d15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391014"
---
# <a name="isassignable-class"></a>Класс is_assignable

Проверяет, можно ли назначить значение типа `From` типу `To`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Параметры

*Задача*<br/>
Тип объекта, который получает назначение.

*From*<br/>
Тип объекта, который предоставляет значение.

## <a name="remarks"></a>Примечания

Невычисленное выражение `declval<To>() = declval<From>()` должно иметь правильный формат. Оба `From` и `To` должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
