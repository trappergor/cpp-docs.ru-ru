---
title: Структура treat_as_floating_point
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 4cf3ac5be972d8636f1d3dbda3b195f4012517be
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459885"
---
# <a name="treatasfloatingpoint-structure"></a>Структура treat_as_floating_point

Указывает, может ли тип `Rep` рассматриваться как тип с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Примечания

`Rep` можно рассматривать как тип с плавающей запятой, только если специализация `treat_as_floating_point<Rep>` является производной от [true_type](../standard-library/type-traits-typedefs.md#true_type). Класс шаблона можно сделать специализированным для определяемого пользователем типа.

## <a name="requirements"></a>Требования

**Заголовок:** \<Chrono >

**Пространство имен:** std::chrono

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
