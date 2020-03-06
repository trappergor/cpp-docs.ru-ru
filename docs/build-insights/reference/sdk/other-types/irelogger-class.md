---
title: Класс Ирелогжер
description: Справочник C++ по классу SDK для Build Insights ирелогжер.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d0796cec3fe4ac6183279e8d8013a9550f18b61c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334076"
---
# <a name="irelogger-class"></a>Класс Ирелогжер

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `IRelogger` предоставляет интерфейс для перезаписи трассировки трассировки событий Windows (ETW). Он используется с функциями [макединамикрелогжерграуп](../functions/make-dynamic-relogger-group.md) и [макестатикрелогжерграуп](../functions/make-static-analyzer-group.md) . Используйте `IRelogger` в качестве базового класса, чтобы создать собственное средство ведения журнала, которое может входить в группу повторного ведения журнала.

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

Возвращаемое по умолчанию значение для всех функций, которые не переопределяются, — `AnalysisControl::CONTINUE`. Дополнительные сведения см. в разделе [аналисисконтрол](analysis-control-enum-class.md).

## <a name="members"></a>Члены

### <a name="destructor"></a>Деструктор

[~ Ирелогжер](#irelogger-destructor)

### <a name="functions"></a>Функции

[Онбегинрелоггинг](#on-begin-relogging)\
[Онбегинрелоггингпасс](#on-begin-relogging-pass)\
[Онендрелоггинг](#on-end-relogging)\
[Онендрелоггингпасс](#on-end-relogging-pass)\
[Онсимпливент](#on-simple-event)\
[Онстартактивити](#on-start-activity)\
[Онстопактивити](#on-stop-activity)\
[онтрацеинфо](#on-trace-info)

## <a name="irelogger-destructor"></a>~ Ирелогжер

Уничтожает класс Ирелогжер.

```cpp
virtual ~IRelogger();
```

## <a name="on-begin-relogging"></a>онбегинрелоггинг

Эта функция вызывается до начала прохода по переведению журнала.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-begin-relogging-pass"></a>онбегинрелоггингпасс

Эта функция вызывается в начале прохода перезаписи.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-end-relogging"></a>онендрелоггинг

Эта функция вызывается после завершения этапа перезаписи в журнал.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-end-relogging-pass"></a>онендрелоггингпасс

Эта функция вызывается в конце прохода перезаписи.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-simple-event"></a>онсимпливент

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

Эта функция вызывается при обработке простого события.

### <a name="parameters"></a>Параметры

*евентстакк*\
Стек событий для этого простого события. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-start-activity"></a>онстартактивити

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

Эта функция вызывается при обработке события начала действия.

### <a name="parameters"></a>Параметры

*евентстакк*\
Стек событий для события начала этого действия. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-stop-activity"></a>онстопактивити

Эта функция вызывается при обработке события завершения действия.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>Параметры

*евентстакк*\
Стек событий для этого события завершения действия. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-trace-info"></a>онтрацеинфо

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

Эта функция вызывается один раз в начале каждого анализа или прохода перезаписи.

### <a name="parameters"></a>Параметры

*traceInfo*\
Объект [TraceInfo](../cpp-event-data-types/trace-info.md) , содержащий полезные свойства используемой трассировки.

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

::: moniker-end
