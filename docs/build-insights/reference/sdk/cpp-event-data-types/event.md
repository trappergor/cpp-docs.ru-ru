---
title: Класс событий
description: Справочник по классу Event пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7dd96ffa3518c58e1b18312bb4fe2c36df26bd67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923295"
---
# <a name="event-class"></a>Класс событий

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Event` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте его для сопоставления любого события.

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

## <a name="members"></a>Члены

### <a name="constructors"></a>Конструкторы

[Событие](#entity)

### <a name="functions"></a>Функции

[Data](#data)
[EventId](#event-id)\
[EventInstanceId](#event-instance-id)\
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ProcessId](#process-id)\
[ProcessorIndex](#processor-index)\
[ThreadId](#thread-id)\
[TickFrequency](#tick-frequency)\
[Timestamp](#timestamp)

## <a name="event"></a>Событие<a name="entity"></a>

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Любое событие.

## <a name="data"></a><a name="data"></a> Data

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дополнительные данные, содержащиеся в этом событии. Сведения об интерпретации этого поля см. в статье [EVENT_DATA](../c-event-data-types/event-data-struct.md).

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

Строка содержит название события, идентифицируемого [EventId](#event-id).

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

## <a name="timestamp"></a><a name="timestamp"></a> Timestamp

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если событие имеет тип "действие", эта функция возвращает значение тактов, захваченное в момент запуска действия. Для простого события эта функция возвращает значение тактов, захваченное в момент создания этого события.

::: moniker-end
