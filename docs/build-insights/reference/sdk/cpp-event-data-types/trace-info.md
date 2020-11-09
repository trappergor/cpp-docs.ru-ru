---
title: Класс TraceInfo
description: Справочник по классу TraceInfo пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b772cc13981720c73238e56a561ca92144775cb4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922926"
---
# <a name="traceinfo-class"></a>Класс TraceInfo

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `TraceInfo` обеспечивает доступ к полезным свойствам анализируемой или повторно регистрируемой трассировки.

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

Вычтите `StartTimestamp` из `StopTimestamp`, чтобы получить число тактов, прошедших во время всей трассировки. Используйте `TickFrequency`, чтобы преобразовать полученное значение в единицу времени. Пример преобразования тактов во время см. в статье об [EVENT_DATA](../c-event-data-types/event-data-struct.md).

Если вы не хотите самостоятельно преобразовывать такты, класс `TraceInfo` предоставляет функции элементов, которые возвращают значение длительности трассировки в наносекундах. Используйте стандартную библиотеку C++ `chrono` для преобразования значения в другие единицы времени.

## <a name="members"></a>Члены

### <a name="constructors"></a>Конструкторы

[TraceInfo](#trace-info)

### <a name="functions"></a>Функции

[Duration](#duration)
[LogicalProcessorCount](#logical-processor-count)
[StartTimestamp](#start-timestamp)
[StopTimestamp](#stop-timestamp)
[TickFrequency](#tick-frequency)

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длительность действия в наносекундах.

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a> LogicalProcessorCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество логических процессоров на компьютере, на котором производилась трассировка.

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение тактов, захваченное в момент запуска действия.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение тактов, захваченное в момент остановки действия.

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тактов в секунду, которое используется при оценке длительности, изменяемой в тактах.

## <a name="traceinfo"></a><a name="trace-info"></a> TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>Параметры

*data*\
Данные, содержащие сведения о трассировке.

::: moniker-end
