---
title: Класс Равевент
description: Справочник C++ по классу SDK для Build Insights равевент.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4088920d6070e14d64ccd046238c1c49b2556ea1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334604"
---
# <a name="rawevent-class"></a>Класс Равевент

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `RawEvent` используется для представления общего события в [евентстакк](event-stack.md).

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

Несколько функций-членов в классе `RawEvent` возвращают счетчик тактов. C++В ходе сборки Insights в качестве источника тактов используется счетчик производительности Windows. Счетчик тактов необходимо использовать с частотой тактов для преобразования его в единицу времени, например в секунды. Чтобы получить частоту тактов, можно вызвать функцию члена `TickFrequency`. Пример преобразования тактов в единицу времени см. на странице [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) .

Если вы не хотите самостоятельно преобразовывать такты, класс `RawEvent` предоставляет функции элементов, которые возвращают значения времени в наносекундах. Используйте стандартную C++ библиотеку `chrono` для преобразования наносекунд в другие единицы времени.

## <a name="members"></a>Члены

### <a name="constructor"></a>Конструктор

[равевент](#raw-event)

### <a name="functions"></a>Функции

[Кпутиккс](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Данные](#data)\
\ [длительности](#duration)
[EventId](#event-id)
[евентинстанцеид](#event-instance-id)
[EventName](#event-name)\
[Евентвиденаме](#event-wide-name)\
[Ексклусивекпутиккс](#exclusive-cpu-ticks)\
[Ексклусивекпутиме](#exclusive-cpu-time)\
[Ексклусиведуратион](#exclusive-duration)\
[Ексклусиведуратионтиккс](#exclusive-duration-ticks)\
[Ексклусивеваллклокктимереспонсибилити](#exclusive-wall-clock-time-responsibility)\
[Ексклусивеваллклокктимереспонсибилититиккс](#exclusive-wall-clock-time-responsibility-ticks)\
Идентификатор [процесса](#process-id)\
[Процессориндекс](#processor-index)\
[Старттиместамп](#start-timestamp)\
[Стоптиместамп](#stop-timestamp)\
[ThreadId](#thread-id)\
[Тиккфрекуенци](#tick-frequency)\
[Валлклокктимереспонсибилити](#wall-clock-time-responsibility)\
[валлклокктимереспонсибилититиккс](#wall-clock-time-responsibility-ticks)

## <a name="raw-event"></a>равевент

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>Параметры

*event*\
Данные, относящиеся к событию.

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

## <a name="data"></a>Data

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дополнительные данные, содержащиеся в этом событии. Дополнительные сведения о том, как интерпретировать это поле, см. в разделе [EVENT_DATA](../c-event-data-types/event-data-struct.md).

## <a name="duration"></a>Длитель

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах.

## <a name="event-id"></a>1008

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число, идентифицирующее тип события. Список идентификаторов событий см. в разделе [EVENT_ID](../c-event-data-types/event-id-enum.md).

## <a name="event-instance-id"></a>евентинстанцеид

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число, однозначно идентифицирующее событие внутри трассировки. Это значение не изменяется при многократном анализе или регистрации одной и той же трассировки несколько раз. Используйте это значение для обнаружения одного и того же события при нескольких анализа или перезаписи в ходе одной трассировки.

## <a name="event-name"></a>EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка ANSI, содержащая имя типа события, идентифицируемого с помощью [EventID](#event-id).

## <a name="event-wide-name"></a>евентвиденаме

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Широкая строка, содержащая имя типа события, идентифицируемого с помощью [EventID](#event-id).

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

## <a name="process-id"></a>Идентификатор

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор процесса, в котором произошло событие.

## <a name="processor-index"></a>процессориндекс

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс логического процессора, на котором произошло событие.

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

## <a name="thread-id"></a>Tидентификатор

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор потока, в котором произошло событие.

## <a name="tick-frequency"></a>тиккфрекуенци

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число тактов в секунду, используемое при вычислении длительности для этого события в тактах.

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
