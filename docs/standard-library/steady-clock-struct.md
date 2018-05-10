---
title: Структура steady_clock | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1dbfac1eb8c67c5306bded6e6fd9ee8dacf54b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="steadyclock-struct"></a>Структура steady_clock

Представляет часы `steady`.

## <a name="syntax"></a>Синтаксис

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Примечания

В Windows объект steady_clock создает оболочку для функции QueryPerformanceCounter.

Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда не больше значений, возвращаемых при последующих вызовах `now()`.

Часы считаются *постоянными*, если они *монотонны* и если интервал времени между соседними тактами является постоянной величиной.

High_resolution_clock является определением типа для steady_clock.

## <a name="public-functions"></a>Открытые функции

|Функция|Описание|
|--------------|-----------------|
|now|Возвращает текущее время как значение time_point.|

## <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|`system_clock::is_steady`|Содержит `true`. Объект `steady_clock` — *постоянный*.|

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std::chrono

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
[Структура system_clock](../standard-library/system-clock-structure.md)<br/>
