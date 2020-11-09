---
title: Класс Activity
description: Справочник по классу Activity пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce7e4083411f1654064ca4628d10a767c7be1b7f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923397"
---
# <a name="activity-class"></a>Класс Activity

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Activity` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте его для сопоставления любого события действия. Чтобы просмотреть все события, которые можно сопоставить с помощью класса `Activity`, см. [таблицу событий](../event-table.md).

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

Несколько функций членов в классе `Activity` возвращают счетчик тактов. Аналитика сборок C++ использует в качестве источника тактов счетчик производительности Windows. Счетчик тактов необходимо использовать с частотой тактов, чтобы преобразовать их в единицу времени, например в секунды. Чтобы получить частоту тактов, можно вызвать функцию члена `TickFrequency`, доступную в базовом классе [Event](event.md). На странице [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) показан пример преобразования тактов в единицу времени.

Если вы не хотите самостоятельно преобразовывать такты в единицы времени, класс `Activity` предоставляет функции членов, которые возвращают значения времени в наносекундах. Используйте стандартную библиотеку C++ `chrono` для преобразования тактов в другие единицы времени.

## <a name="members"></a>Члены

Наряду с членами, унаследованными от базового класса [Event](event.md), класс `Activity` содержит следующие члены:

### <a name="constructor"></a>Конструктор

[Действие](#activity)

### <a name="functions"></a>Функции

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Duration](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> Действие

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Любое событие действия.

## <a name="cputicks"></a><a name="cpu-ticks"></a> CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число тактов ЦП, произошедших во время этого действия. Такт ЦП отличается от обычного такта. Такты ЦП учитываются только тогда, когда ЦП исполняет код в этом действии. Такты ЦП не учитываются, пока связанный с действием поток находится в спящем режиме.

## <a name="cputime"></a><a name="cpu-time"></a> CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Возвращаемое значение

Время, в течение которого ЦП выполнял код в рамках этого действия. Это значение может превышать длительность действия, если дочерние действия выполняются в отдельных потоках. Значение возвращается в наносекундах.

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах.

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a> ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Аналогичное значению [CPUTicks](#cpu-ticks), однако не содержит такты ЦП, которые произошли в дочерних действиях.

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a> ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Возвращаемое значение

Аналогичное значению [CPUTime](#cpu-time), за исключением того, что в нем не содержится время ЦП дочерних действий.

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a> ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах, за исключением времени, затраченного на выполнение дочерних действий.

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a> ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тактов, произошедших в этом действии, за исключением количества тактов, произошедших в дочерних действиях.

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a> ExclusiveWallClockTimeResponsibility

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Возвращаемое значение

Аналогичное значению [WallClockTimeResponsibility](#wall-clock-time-responsibility), однако не содержит физическое время выполнения дочерних действий.

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a> ExclusiveWallClockTimeResponsibilityTicks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Аналогичное значению [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks), однако не содержит такты физического времени выполнения дочерних действий.

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение такта, зафиксированное во время начала действия.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение такта, зафиксированное во время остановки действия.

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a> WallClockTimeResponsibility

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Возвращаемое значение

Физическое время выполнения для этой операции в наносекундах. Дополнительные сведения о том, что означает физическое время выполнения, см. в разделе [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks).

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a> WallClockTimeResponsibilityTicks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Счетчик тактов, который представляет вклад этого действия в общее физическое время выполнения. Такт реального времени выполнения часах отличается от обычного такта. В тактах реального времени выполнения учитывается параллелизм при выполнении действий. Два действия, которые выполняются параллельно, могут иметь длительность 50 тактов, а также идентичное время начала и завершения. В этом случае обоим процессам будет присвоено значение 25 тактов физического времени.

::: moniker-end
