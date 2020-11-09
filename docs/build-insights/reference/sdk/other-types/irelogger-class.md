---
title: Класс IRelogger
description: Справочник по классу IRelogger пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e504ece95529f7279650062145f3ac0914449c98
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922521"
---
# <a name="irelogger-class"></a>Класс IRelogger

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `IRelogger` предоставляет интерфейс для перезаписи трассировки событий для трассировки событий Windows (ETW). Его следует использовать с функциями [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md) и [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md). Используйте `IRelogger` как базовый класс, чтобы создать собственное средство перезаписи, которое будет входить в группу средств перезаписи.

## <a name="syntax"></a>Синтаксис

```cpp
class IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
    virtual AnalysisControl OnBeginRelogging();
    virtual AnalysisControl OnEndRelogging();
    virtual AnalysisControl OnBeginReloggingPass();
    virtual AnalysisControl OnEndReloggingPass() ;

    virtual ~IRelogger();
};
```

## <a name="remarks"></a>Remarks

`AnalysisControl::CONTINUE` — это возвращаемое значение по умолчанию для всех функций, которые не переопределяются. Дополнительные сведения см. в статье [AnalysisControl](analysis-control-enum-class.md).

## <a name="members"></a>Члены

### <a name="destructor"></a>Деструктор

[~IRelogger](#irelogger-destructor)

### <a name="functions"></a>Функции

[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)\
[OnTraceInfo](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a> ~IRelogger

Уничтожает класс IRelogger.

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

Эта функция вызывается до начала передачи перезаписи.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

Эта функция вызывается в начале передачи перезаписи.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

Эта функция вызывается после завершения передачи перезаписи.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

Эта функция вызывается в конце передачи перезаписи.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

Эта функция вызывается при обработке простого события.

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для этого простого события. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

Эта функция вызывается при обработке событий запуска действия.

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для этого события запуска действия. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

Эта функция вызывается при обработке события остановки действия.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для этого события остановки действия. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

## <a name="ontraceinfo"></a><a name="on-trace-info"></a>OnTraceInfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

Эта функция вызывается один раз в начале каждого анализа или передачи перезаписи.

### <a name="parameters"></a>Параметры

*traceInfo*\
Объект [TraceInfo](../cpp-event-data-types/trace-info.md), который содержит полезные параметры используемой трассировки.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает, что должно произойти далее.

::: moniker-end
