---
title: Класс is_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5666aca2d6a855b64af26d38a1ae834fecec5d6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958469"
---
# <a name="isassignable-class"></a>Класс is_assignable

Проверяет, можно ли назначить значение типа `From` типу `To`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Параметры

Тип объекта, который получает назначение.

От типа объекта, который предоставляет значение.

## <a name="remarks"></a>Примечания

Невычисленное выражение `declval<To>() = declval<From>()` должно иметь правильный формат. Оба `From` и `To` должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
