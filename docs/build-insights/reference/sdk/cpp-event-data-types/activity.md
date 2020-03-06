---
title: Класс Activity
description: Справочник C++ по классу действий SDK для Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6de411c375b42e4acfb44bf0fac9d28ad57f1ca7
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335030"
---
# <a name="activity-class"></a>Класс Activity

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Activity` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления любого события действия. Чтобы просмотреть все события, которые могут быть сопоставлены с классом `Activity`, см. [таблицу событий](../event-table.md) .

## <a name="syntax"></a>Синтаксис

```cpp
class Activity : public Event
{
public:
    Activity(const RawEvent& event);

    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;
    const long long& ExclusiveDurationTicks() const;
    const long long& CPUTicks() const;
    const long long& ExclusiveCPUTicks() const;
    const long long& WallClockTimeResponsibilityTicks() const;
    const long long& ExclusiveWallClockTimeResponsibilityTicks() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>Remarks

Несколько функций-членов в классе `Activity` возвращают счетчик тактов. C++В ходе сборки Insights в качестве источника тактов используется счетчик производительности Windows. Счетчик тактов необходимо использовать с частотой тактов для преобразования его в единицу времени, например в секунды. Функция члена `TickFrequency`, доступная в базовом классе [события](event.md) , может быть вызвана для получения частоты тактов. На странице [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) показан пример преобразования тактов в единицу времени.

Если вы не хотите самостоятельно преобразовывать такты в единицы времени, класс `Activity` предоставляет функции элементов, которые возвращают значения времени в наносекундах. Используйте стандартную C++ библиотеку `chrono` для преобразования их в другие единицы времени.

## <a name="members"></a>Члены

Вместе с его членами, унаследованными от базового класса [событий](event.md) , класс `Activity` содержит следующие члены:

### <a name="constructor"></a>Конструктор

[Действие](#activity)

### <a name="functions"></a>Функции

[Кпутиккс](#cpu-ticks)\
[CPUTime](#cpu-time)\
\ [длительности](#duration)
[Ексклусивекпутиккс](#exclusive-cpu-ticks)\
[Ексклусивекпутиме](#exclusive-cpu-time)\
[Ексклусиведуратион](#exclusive-duration)\
[Ексклусиведуратионтиккс](#exclusive-duration-ticks)\
[Ексклусивеваллклокктимереспонсибилити](#exclusive-wall-clock-time-responsibility)\
[Ексклусивеваллклокктимереспонсибилититиккс](#exclusive-wall-clock-time-responsibility-ticks)\
[Старттиместамп](#start-timestamp)\
[Стоптиместамп](#stop-timestamp)\
[Валлклокктимереспонсибилити](#wall-clock-time-responsibility)\
[валлклокктимереспонсибилититиккс](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a>Оборот

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Любое событие действия.

## <a name="cpu-ticks"></a>кпутиккс

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число тактов ЦП, произошедших во время этого действия. Такт ЦП отличается от обычного такта. Такты ЦП учитываются только тогда, когда ЦП исполняет код в действии. Такты ЦП не учитываются, если поток, связанный с действием, находится в спящем режиме.

## <a name="cpu-time"></a>CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Возвращаемое значение

Время, в течение которого ЦП выполнял код в рамках этого действия. Это значение может быть выше, чем длительность действия, если дочерние действия выполняются в отдельных потоках. Значение возвращается в наносекундах.

## <a name="duration"></a>Длитель

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах.

## <a name="exclusive-cpu-ticks"></a>ексклусивекпутиккс

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же, что и [кпутиккс](#cpu-ticks), но не включая такты ЦП, которые произошли в дочерних действиях.

## <a name="exclusive-cpu-time"></a>ексклусивекпутиме

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же, что и [CPUTime](#cpu-time), за исключением того, что время ЦП дочерних действий не включается.

## <a name="exclusive-duration"></a>ексклусиведуратион

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах, не включая время, которое было затрачено на выполнение дочерних действий.

## <a name="exclusive-duration-ticks"></a>ексклусиведуратионтиккс

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число тактов, произошедших в этом действии, за исключением количества тактов, произошедших в дочерних действиях.

## <a name="exclusive-wall-clock-time-responsibility"></a>ексклусивеваллклокктимереспонсибилити

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же, что и [валлклокктимереспонсибилити](#wall-clock-time-responsibility), но не включает в себя ответственность за время работы дочерних действий.

## <a name="exclusive-wall-clock-time-responsibility-ticks"></a>ексклусивеваллклокктимереспонсибилититиккс

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же, что и [валлклокктимереспонсибилититиккс](#wall-clock-time-responsibility-ticks), но не включая такты ответственности для дочерних действий.

## <a name="start-timestamp"></a>старттиместамп

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение Tick, захваченное во время запуска действия.

## <a name="stop-timestamp"></a>стоптиместамп

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение Tick, захваченное на момент остановки действия.

## <a name="wall-clock-time-responsibility"></a>валлклокктимереспонсибилити

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Возвращаемое значение

Это действие отвечает за время выполнения этой операции в наносекундах. Дополнительные сведения о том, что означают обязанности повременных часов, см. в разделе [валлклокктимереспонсибилититиккс](#wall-clock-time-responsibility-ticks).

## <a name="wall-clock-time-responsibility-ticks"></a>валлклокктимереспонсибилититиккс

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Счетчик тактов, который представляет вклад этого действия в общее время стены. Тактовая частота на стене-часах отличается от обычной тактовой разницы. Такты ответственности за простенки времени принимают во внимание параллелизм между действиями. Два параллельных действия могут иметь длительность 50 тактов и одно и то же время начала и окончания. В этом случае обоим присвоено значение времени, равное 25 тактам.

::: moniker-end
