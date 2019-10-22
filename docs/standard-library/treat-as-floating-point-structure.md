---
title: Структура treat_as_floating_point
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: add69179b23a953a937458cbfa55254b21c5ea37
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685117"
---
# <a name="treat_as_floating_point-structure"></a>Структура treat_as_floating_point

Указывает, может ли тип `Rep` рассматриваться как тип с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Заметки

`Rep` можно рассматривать как тип с плавающей запятой, только если специализация `treat_as_floating_point<Rep>` является производной от [true_type](../standard-library/type-traits-typedefs.md#true_type). Шаблон класса может быть специализированным для определяемого пользователем типа.

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std::chrono

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
