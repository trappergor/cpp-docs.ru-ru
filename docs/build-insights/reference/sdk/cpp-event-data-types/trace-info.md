---
title: Класс TraceInfo
description: Справочник C++ по классу SDK для Build Insights TraceInfo.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5cf32c8dc954a803a11888231d35b1050ac81cc3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334502"
---
# <a name="traceinfo-class"></a>Класс TraceInfo

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `TraceInfo` используется для доступа к полезным свойствам анализируемой или регистрируемой трассировки.

## <a name="syntax"></a>Синтаксис

```cpp
class TraceInfo
{
public:
    TraceInfo(const TRACE_INFO_DATA& data);

    const unsigned long& LogicalProcessorCount() const;

    const long long& TickFrequency() const;
    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;

    std::chrono::nanoseconds Duration() const;
};
```

## <a name="remarks"></a>Remarks

Вычтите `StartTimestamp` из `StopTimestamp`, чтобы получить количество тактов, прошедших во время всей трассировки. Используйте `TickFrequency`, чтобы преобразовать полученное значение в единицу времени. Пример преобразования тактов в время см. в разделе [EVENT_DATA](../c-event-data-types/event-data-struct.md).

Если вы не хотите самостоятельно преобразовывать такты, класс `TraceInfo` предоставляет функцию-член, которая возвращает длительность трассировки в наносекундах. Используйте стандартную C++ библиотеку `chrono` для преобразования этого значения в другие единицы времени.

## <a name="members"></a>Члены

### <a name="constructors"></a>Конструкторы

[TraceInfo](#trace-info)

### <a name="functions"></a>Функции

[Duration](#duration)
[логикалпроцессоркаунт](#logical-processor-count)
[старттиместамп](#start-timestamp)
[стоптиместамп](#stop-timestamp)
[тиккфрекуенци](#tick-frequency)

## <a name="duration"></a>Длитель

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах.

## <a name="logical-processor-count"></a>логикалпроцессоркаунт

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число логических процессоров на компьютере, на котором была собрана трассировка.

## <a name="start-timestamp"></a>старттиместамп

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение Tick, захваченное во время запуска трассировки.

## <a name="stop-timestamp"></a>стоптиместамп

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение Tick, захваченное на момент остановки трассировки.

## <a name="tick-frequency"></a>тиккфрекуенци

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число тактов в секунду, используемое при вычислении длительности, измеряемой в тактах.

## <a name="trace-info"></a>TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>Параметры

\ *данных*
Данные, содержащие сведения о трассировке.

::: moniker-end
