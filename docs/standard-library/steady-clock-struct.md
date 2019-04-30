---
title: Структура steady_clock
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 19e9f5c4dcfc7306b989605894e9a0787e0920ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412401"
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

`high_resolution_clock` является определением типа для `steady_clock`.

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`steady_clock::duration`|Синоним для `nanoseconds`, определенный в \<chrono >.|
|`steady_clock::period`|Синоним для `nano`, определенный в \<соотношение >.|
|`steady_clock::rep`|Синоним для **long** **long**, тип, который используется для представления числа тактов часов при автономном создании экземпляра `duration`.|
|`steady_clock::time_point`|Синоним для `chrono::time_point<steady_clock>`.|

## <a name="public-functions"></a>Открытые функции

|Функция|Описание|
|--------------|-----------------|
|`now`|Возвращает текущее время как `time_point` значение.|

## <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|`steady_clock::is_steady`|Содержит **true**. Объект `steady_clock` — *постоянный*.|

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std::chrono

## <a name="see-also"></a>См. также

- [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [Структура system_clock](../standard-library/system-clock-structure.md)
