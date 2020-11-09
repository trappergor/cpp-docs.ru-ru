---
title: Класс IAnalyzer
description: Справочник по классу IAnalyzer пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2514dd305a186d1153e9f9d1711bb774ea70cdf9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919817"
---
# <a name="ianalyzer-class"></a>Класс IAnalyzer

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `IAnalyzer` предоставляет интерфейс для анализа трассировки событий Windows (ETW). Он используется с функциями [MakeDynamicAnalyzerGroup](../functions/make-dynamic-analyzer-group.md), [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md), [MakeStaticAnalyzerGroup](../functions/make-dynamic-analyzer-group.md) и [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md). Используйте `IAnalyzer` в качестве базового класса, чтобы создать собственный анализатор, который может быть частью анализатора или группы повторной записи в журнал.

## <a name="syntax"></a>Синтаксис

```cpp
class IAnalyzer : public IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
    virtual AnalysisControl OnStopActivity(const EventStack& eventStack)
    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
    virtual AnalysisControl OnBeginAnalysis();
    virtual AnalysisControl OnEndAnalysis();
    virtual AnalysisControl OnBeginAnalysisPass();
    virtual AnalysisControl OnEndAnalysisPass();

    AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnBeginRelogging() final;
    AnalysisControl OnEndRelogging() final;
    AnalysisControl OnBeginReloggingPass() final;
    AnalysisControl OnEndReloggingPass() final;

    virtual ~IAnalyzer();
};
```

## <a name="remarks"></a>Remarks

Классы, производные от `IAnalyzer`, можно использовать как анализаторы и как средства повторной записи в журнал. При использовании классов в качестве средств повторной записи в журнал функции данного средства перенаправляются в свой аналог анализатора. Обратная совместимость не возможна: класс, производный от `IRelogger`, не может использоваться в качестве анализатора. Использование анализатора в группе повторной записи в журнал является распространенной практикой. При размещении в ранней позиции группы повторной записи в журнал анализатор может предварительно вычислить информацию и предоставить ее для средств повторной записи в журнал в последующих позициях.

`AnalysisControl::CONTINUE` — это возвращаемое значение по умолчанию для всех функций, которые не переопределяются. Дополнительные сведения см. в статье [AnalysisControl](analysis-control-enum-class.md).

## <a name="members"></a>Члены

Помимо элемента [OnTraceInfo](irelogger-class.md#on-trace-info) из интерфейса `IRelogger`, класс `IAnalyzer` содержит следующие элементы:

### <a name="destructor"></a>Деструктор

[~IAnalyzer](#ianalyzer-destructor)

### <a name="functions"></a>Функции

[OnBeginAnalysis](#on-begin-analysis)\
[OnBeginAnalysisPass](#on-begin-analysis-pass)\
[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndAnalysis](#on-end-analysis)\
[OnEndAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a> ~IAnalyzer

Уничтожает класс IAnalyzer.

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a> OnBeginAnalysis

Для анализаторов, входящих в группу анализаторов, эта функция вызывается до начала первого прохода анализа. Для анализаторов, входящих в группу повторной записи в журнал, эта функция вызывается до начала прохода повторной записи в журнал. Для анализаторов, входящих и в группу анализаторов, и в группу повторной записи в журнал в одном и том же сеансе повторной записи в журнал, эта функция вызывается до начала первого прохода анализа.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает дальнейшие действия.

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a> OnBeginAnalysisPass

Для анализаторов, входящих в группу анализаторов, эта функция вызывается в начале каждого прохода анализа. Для анализаторов, входящих в группу повторной записи в журнал, эта функция вызывается в начале прохода повторной записи в журнал. Для анализаторов, входящих и в группу анализаторов, и в группу повторной записи в журнал в одном и том же сеансе повторной записи в журнал, эта функция вызывается в начале каждого прохода анализа и в начале прохода повторной записи в журнал.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает дальнейшие действия.

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

Эта функция не может быть переопределена. Она вызывается пакетом SDK Аналитики сборок С++, если анализатор входит в группу повторной записи в журнал. Эта функция перенаправляет вызов [OnBeginAnalysis](#on-begin-analysis).

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnBeginAnalysis](#on-begin-analysis).

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

Эта функция не может быть переопределена. Она вызывается пакетом SDK Аналитики сборок С++, если анализатор входит в группу повторной записи в журнал. Эта функция перенаправляет вызов [OnBeginAnalysisPass](#on-begin-analysis-pass).

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnBeginAnalysisPass](#on-begin-analysis-pass).

## <a name="onendanalysis"></a><a name="on-end-analysis"></a> OnEndAnalysis

Для анализаторов, входящих в группу анализаторов, эта функция вызывается после завершения последнего прохода анализа. Для анализаторов, входящих в группу повторной записи в журнал, эта функция вызывается после завершения прохода повторной записи в журнал. Для анализаторов, входящих и в группу анализаторов, и в группу повторной записи в журнал в одном и том же сеансе повторной записи в журнал, эта функция вызывается дважды:

1. после завершения всех проходов анализа и до начала прохода повторной записи в журнал;
1. после завершения прохода повторной записи в журнал.

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает дальнейшие действия.

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a> OnEndAnalysisPass

Для анализаторов, входящих в группу анализаторов, эта функция вызывается в конце каждого прохода анализа. Для анализаторов, входящих в группу повторной записи в журнал, эта функция вызывается в конце прохода повторной записи в журнал. Для анализаторов, входящих и в группу анализаторов, и в группу повторной записи в журнал в одном и том же сеансе повторной записи в журнал, эта функция вызывается в конце каждого прохода анализа и в конце прохода повторной записи в журнал.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает дальнейшие действия.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

Эта функция не может быть переопределена. Она вызывается пакетом SDK Аналитики сборок С++, если анализатор входит в группу повторной записи в журнал. Эта функция перенаправляет вызов [OnEndAnalysis](#on-end-analysis).

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnEndAnalysis](#on-end-analysis).

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

Эта функция не может быть переопределена. Она вызывается пакетом SDK Аналитики сборок С++, если анализатор входит в группу повторной записи в журнал. Эта функция перенаправляет вызов [OnEndAnalysisPass](#on-end-analysis-pass).

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnEndAnalysisPass](#on-end-analysis-pass).

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

Эта функция вызывается при обработке простого события. Вторая версия этой функции не может быть переопределена. Она вызывается пакетом SDK Аналитики сборок С++, если анализатор входит в группу повторной записи в журнал. Все вызовы версии 2 перенаправляются на версию 1.

### <a name="version-1"></a>версия 1

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

### <a name="version-2"></a>версия 2

```cpp
AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для этого простого события. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

*relogSession*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает дальнейшие действия.

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

Эта функция вызывается при обработке событий запуска действия. Вторая версия этой функции не может быть переопределена. Она вызывается пакетом SDK Аналитики сборок С++, если анализатор входит в группу повторной записи в журнал. Все вызовы версии 2 перенаправляются на версию 1.

### <a name="version-1"></a>версия 1

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>версия 2

```cpp
AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для этого события запуска действия. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

*relogSession*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает дальнейшие действия.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

Эта функция вызывается при обработке события остановки действия. Вторая версия этой функции не может быть переопределена. Она вызывается пакетом SDK Аналитики сборок С++, если анализатор входит в группу повторной записи в журнал. Все вызовы версии 2 перенаправляются на версию 1.

### <a name="version-1"></a>версия 1

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>версия 2

```cpp
AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для этого события остановки действия. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

*relogSession*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl](analysis-control-enum-class.md) описывает дальнейшие действия.

::: moniker-end
