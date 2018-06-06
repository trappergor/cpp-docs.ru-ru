---
title: Структура steady_clock | Документы Майкрософт
ms.custom: ''
ms.date: 05/22/2018
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
ms.openlocfilehash: 5445379597c4fefcd657303a05c33b6509d54d2e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569902"
---
# <a name="steadyclock-struct"></a>Структура steady_clock

Представляет *постоянной* часов.

## <a name="syntax"></a>Синтаксис

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Примечания

В Windows `steady_clock` заключает в оболочку `QueryPerformanceCounter` функции.

Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now`, всегда меньше значения, возвращаемого при последующих вызовах `now`, или равно ему. Часы считаются *постоянными*, если они *монотонны* и интервал времени между соседними тактами является постоянной величиной.

`high_resolution_clock` TypeDef для `steady_clock`.

### <a name="public-typedefs"></a>Открытые определения типов

|name|Описание:|
|----------|-----------------|
|`steady_clock::duration`|Синоним для `nanoseconds`, определенного в \<chrono >.|
|`steady_clock::period`|Синоним для `nano`, определенного в \<отношение >.|
|`steady_clock::rep`|Синоним для **длинные** **длинные**, тип, который используется для представления числа тактов часов при автономном создании экземпляра `duration`.|
|`steady_clock::time_point`|Синоним для `chrono::time_point<steady_clock>`.|

## <a name="public-functions"></a>Открытые функции

|Функция|Описание:|
|--------------|-----------------|
|`now`|Возвращает текущее время как `time_point` значение.|

## <a name="public-constants"></a>Открытые константы

|name|Описание:|
|----------|-----------------|
|`steady_clock::is_steady`|Содержит `true`. Объект `steady_clock` — *постоянный*.|

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std::chrono

## <a name="see-also"></a>См. также

- [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [Структура system_clock](../standard-library/system-clock-structure.md)
