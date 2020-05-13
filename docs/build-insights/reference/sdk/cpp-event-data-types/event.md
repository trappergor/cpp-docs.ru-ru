---
title: Класс событий
description: Ссылка на класс событий SDK Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 25d58f642a1c314e48ddff62553394bcc65e4717
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324967"
---
# <a name="event-class"></a>Класс событий

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Event` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его, чтобы соответствовать любому событию.

## <a name="syntax"></a>Синтаксис

```cpp
class Event
{
public:
    Event(const RawEvent& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             Timestamp() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;
};
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

[Событие](#entity)

### <a name="functions"></a>Функции

[Данные](#data)
[EventId](#event-id)\
[EventInstanceId](#event-instance-id)\
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ProcessId](#process-id)\
[ПроцессорИндекс](#processor-index)\
[ThreadId](#thread-id)\
[ТикЧастота](#tick-frequency)\
[Timestamp](#timestamp)

## <a name="event"></a>Событие<a name="entity"></a>

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Любое событие.

## <a name="data"></a><a name="data"></a>Данных

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дополнительные данные, содержащиеся в этом событии. Для получения дополнительной информации о том, как интерпретировать это поле, см [EVENT_DATA.](../c-event-data-types/event-data-struct.md)

## <a name="eventid"></a><a name="event-id"></a>Eventid

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер, идентифицирующие тип события. Список идентификаторов событий можно узнать [EVENT_ID.](../c-event-data-types/event-id-enum.md)

## <a name="eventinstanceid"></a><a name="event-instance-id"></a>EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер, который однозначно идентифицирует событие внутри следа. Это значение не изменяется при анализе или повторном прослеживании одного и того же следа несколько раз. Используйте это значение для определения одного и того же события в нескольких анализа или перезаписи проходов по тому же следу.

## <a name="eventname"></a><a name="event-name"></a>EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка ANSI, содержащая имя типа события, идентифицированного [EventId.](#event-id)

## <a name="eventwidename"></a><a name="event-wide-name"></a>EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Широкая строка, содержащая название события, идентифицированного [EventId](#event-id).

## <a name="processid"></a><a name="process-id"></a>ProcessId

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор процесса, в котором произошло событие.

## <a name="processorindex"></a><a name="processor-index"></a>ПроцессорИндекс

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс с нулевым уровнем для логического процессора, на котором произошло событие.

## <a name="threadid"></a><a name="thread-id"></a>ThreadId

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор для потока, в котором произошло событие.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>ТикЧастота

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тиков в секунду для использования при оценке продолжительности, измеренной в тиках для этого события.

## <a name="timestamp"></a><a name="timestamp"></a>Timestamp

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если событие является действием, эта функция возвращает значение тика, захваченное во время начала действия. Для простого события эта функция возвращает значение тика, захваченное во время события.

::: moniker-end
