---
title: Класс RawEvent
description: Справочник по классу RawEvent пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1cf96e1b8eadaf1de9fe2cf565a993f3bcafe358
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920467"
---
# <a name="rawevent-class"></a>Класс RawEvent

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `RawEvent` используется для представления общего события в [EventStack](event-stack.md).

## <a name="syntax"></a>Синтаксис

```cpp
class RawEvent
{
public:
    RawEvent(const EVENT_DATA& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             StartTimestamp() const;
    const long long&             StopTimestamp() const;
    const long long&             ExclusiveDurationTicks() const;
    const long long&             CPUTicks() const;
    const long long&             ExclusiveCPUTicks() const;
    const long long&             WallClockTimeResponsibilityTicks() const;
    const long long&             ExclusiveWallClockTimeResponsibilityTicks() const;
    const void*                  Data() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>Remarks

Несколько функций членов в классе `RawEvent` возвращают счетчик тактов. Аналитика сборок C++ использует в качестве источника тактов счетчик производительности Windows. Счетчик тактов необходимо использовать с частотой тактов, чтобы преобразовать их в единицу времени, например в секунды. Чтобы получить частоту тактов, можно вызвать функцию члена `TickFrequency`. Пример преобразования тактов в единицу времени см. на странице [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example).

Если вы не хотите самостоятельно преобразовывать такты, класс `RawEvent` предоставляет функции членов, которые возвращают значения времени в наносекундах. Используйте стандартную библиотеку C++ `chrono` для преобразования наносекунд в другие единицы времени.

## <a name="members"></a>Члены

### <a name="constructor"></a>Конструктор

[RawEvent](#raw-event)

### <a name="functions"></a>Функции

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Данные](#data)\
[Duration](#duration)\
[EventId](#event-id)
[EventInstanceId](#event-instance-id)
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[ProcessId](#process-id)\
[ProcessorIndex](#processor-index)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[ThreadId](#thread-id)\
[TickFrequency](#tick-frequency)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="rawevent"></a><a name="raw-event"></a> RawEvent

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>Параметры

*event*\
Данные события.

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

## <a name="data"></a><a name="data"></a> Data

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дополнительные данные, содержащиеся в этом событии. Сведения об интерпретации этого поля см. в статье [EVENT_DATA](../c-event-data-types/event-data-struct.md).

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах.

## <a name="eventid"></a><a name="event-id"></a> EventId

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер, который указывает на тип события. Список идентификаторов можно узнать в справочнике по [EVENT_ID](../c-event-data-types/event-id-enum.md).

## <a name="eventinstanceid"></a><a name="event-instance-id"></a> EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Это число, которое уникальным образом идентифицирует событие в пределах трассировки. Это значение не изменяется при многократном анализе или повторной записи одной и той же трассировки. Используйте это значение для обнаружения одного и того же события при множественных операциях анализа или повторной записи в журнал, в ходе одной трассировки.

## <a name="eventname"></a><a name="event-name"></a> EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка ANSI, которая содержит название типа события, определяемого по [EventId](#event-id).

## <a name="eventwidename"></a><a name="event-wide-name"></a> EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Широкая строка, которая содержит название типа события, определяемого по [EventId](#event-id).

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

## <a name="processid"></a><a name="process-id"></a> ProcessId

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор процесса, в котором возникло текущее событие.

## <a name="processorindex"></a><a name="processor-index"></a> ProcessorIndex

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс для логического процессора, на котором произошло событие.

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

## <a name="threadid"></a><a name="thread-id"></a> ThreadId

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор потока, в котором возникло текущее событие.

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число тактов в секунду, используемое при вычислении длительности в тактах для этого события.

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
