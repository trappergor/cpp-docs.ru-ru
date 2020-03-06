---
title: Класс событий
description: Справочник C++ по классу событий Build Insights SDK.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 205a4e0ca9dd9449933f38f02d4ceafd5df8ead2
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334892"
---
# <a name="event-class"></a>Класс событий

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Event` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с любым событием.

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

\
[данных](#data) [EventID](#event-id)
[Евентинстанцеид](#event-instance-id)\
[EventName](#event-name)\
[Евентвиденаме](#event-wide-name)\
Идентификатор [процесса](#process-id)\
[Процессориндекс](#processor-index)\
[ThreadId](#thread-id)\
[Тиккфрекуенци](#tick-frequency)\
[Timestamp](#timestamp)

## <a name="entity"></a>Журнале

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Любое событие.

## <a name="data"></a>Data

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дополнительные данные, содержащиеся в этом событии. Дополнительные сведения о том, как интерпретировать это поле, см. в разделе [EVENT_DATA](../c-event-data-types/event-data-struct.md).

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

Широкая строка, содержащая имя события, определяемое [EventID](#event-id).

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

## <a name="timestamp"></a>Timestamp

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если событие является действием, эта функция возвращает значение Tick, захваченное на момент запуска действия. Для простого события эта функция возвращает значение Tick, захваченное на момент возникновения события.

::: moniker-end
