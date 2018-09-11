---
title: Класс is_nothrow_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36d078c567f3ca74fb3552cbe728076445dd6690
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110088"
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
