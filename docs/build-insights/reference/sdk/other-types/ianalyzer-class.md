---
title: Класс Ианализер
description: Справочник C++ по классу SDK для Build Insights ианализер.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 53f7b36695bb24d96ccfe88afbb56ff717c94dc9
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334082"
---
# <a name="ianalyzer-class"></a>Класс Ианализер

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `IAnalyzer` предоставляет интерфейс для анализа трассировки трассировки событий Windows (ETW). Он используется с функциями [макединамиканализерграуп](../functions/make-dynamic-analyzer-group.md), [макединамикрелогжерграуп](../functions/make-dynamic-relogger-group.md), [макестатиканализерграуп](../functions/make-dynamic-analyzer-group.md)и [макестатикрелогжерграуп](../functions/make-static-analyzer-group.md) . Используйте `IAnalyzer` в качестве базового класса, чтобы создать собственный анализатор, который может входить в анализатор или группу повторного ведения журнала.

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

Классы, производные от `IAnalyzer`, можно использовать как анализаторы, так и средства регистрации. При использовании в качестве регистраторов функции, зависящие от средства ведения журнала, перенаправляются в свой эквивалент анализатора. Обратная неверность: класс, производный от `IRelogger`, не может использоваться в качестве анализатора. Использование анализатора в группе повторного ведения журнала — это общий шаблон. При размещении в ранней позиции группы повторного ведения журнала анализатор может предварительно вычислить информацию и сделать ее доступной для повторного ведения журнала в последующих позициях.

Возвращаемое по умолчанию значение для всех функций, которые не переопределяются, — `AnalysisControl::CONTINUE`. Дополнительные сведения см. в разделе [аналисисконтрол](analysis-control-enum-class.md).

## <a name="members"></a>Члены

В дополнение к элементу [онтрацеинфо](irelogger-class.md#on-trace-info) из интерфейса `IRelogger` класс `IAnalyzer` содержит следующие члены:

### <a name="destructor"></a>Деструктор

[~ Ианализер](#ianalyzer-destructor)

### <a name="functions"></a>Функции

[Онбегинаналисис](#on-begin-analysis)\
[Онбегинаналисиспасс](#on-begin-analysis-pass)\
[Онбегинрелоггинг](#on-begin-relogging)\
[Онбегинрелоггингпасс](#on-begin-relogging-pass)\
[Оненданалисис](#on-end-analysis)\
[Оненданалисиспасс](#on-end-analysis-pass)\
[Онендрелоггинг](#on-end-relogging)\
[Онендрелоггингпасс](#on-end-relogging-pass)\
[Онсимпливент](#on-simple-event)\
[Онстартактивити](#on-start-activity)\
[онстопактивити](#on-stop-activity)

## <a name="ianalyzer-destructor"></a>~ Ианализер

Уничтожает класс Ианализер.

```cpp
virtual ~IAnalyzer();
```

## <a name="on-begin-analysis"></a>онбегинаналисис

Для анализаторов, входящих в группу анализаторов, эта функция вызывается до начала первого прохода по анализу. Для анализаторов, входящих в группу переведения журнала, эта функция вызывается до начала прохода по перезаписи. Для анализаторов, входящих в один и тот же сеанс повторного ведения журнала, и как анализатор, и в группу повторного ведения журнала, эта функция вызывается дважды перед началом первого прохода по анализу.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-begin-analysis-pass"></a>онбегинаналисиспасс

Для анализаторов, входящих в группу анализаторов, эта функция вызывается в начале каждого этапа анализа. Для анализаторов, входящих в группу переведения журнала, эта функция вызывается в начале этого прохода. Для анализаторов, входящих в состав одного и того же сеанса перезаписи в систему, используется анализатор и группа переведения журнала. Эта функция вызывается в начале каждого прохода анализа и в начале этого прохода.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-begin-relogging"></a>онбегинрелоггинг

```cpp
AnalysisControl OnBeginRelogging() final;
```

Эта функция не может быть переопределена. Он вызывается пакетом C++ SDK для Build Insights, когда анализатор входит в группу переведения журнала. Эта функция перенаправляет вызов в [онбегинаналисис](#on-begin-analysis).

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [онбегинаналисис](#on-begin-analysis) .

## <a name="on-begin-relogging-pass"></a>онбегинрелоггингпасс

Эта функция не может быть переопределена. Он вызывается пакетом C++ SDK для Build Insights, когда анализатор входит в группу переведения журнала. Эта функция перенаправляет вызов в [онбегинаналисиспасс](#on-begin-analysis-pass).

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [онбегинаналисиспасс](#on-begin-analysis-pass) .

## <a name="on-end-analysis"></a>оненданалисис

Для анализаторов, которые являются частью группы анализатора, эта функция вызывается после завершения последнего этапа анализа. Для анализаторов, которые являются частью группы переведения журнала, эта функция вызывается после завершения этапа перезаписи в журнал. Для анализаторов, которые являются частью анализатора и группы повторного ведения журнала одного и того же сеанса повторного ведения журнала, эта функция вызывается дважды:

1. После завершения всех этапов анализа и до начала прохода по перезаписи.
1. После завершения этапа перезаписи журнала.

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-end-analysis-pass"></a>оненданалисиспасс

Для анализаторов, входящих в группу анализаторов, эта функция вызывается в конце каждого прохода анализа. Для анализаторов, входящих в группу переведения журнала, эта функция вызывается в конце прохода переведения журнала. Для анализаторов, входящих в состав одного и того же сеанса перезаписи в систему, используется анализатор и группа переведения журнала. Эта функция вызывается в конце каждого прохода анализа и в конце прохода переведения журнала.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-end-relogging"></a>онендрелоггинг

Эта функция не может быть переопределена. Он вызывается пакетом C++ SDK для Build Insights, когда анализатор входит в группу переведения журнала. Эта функция перенаправляет вызов в [оненданалисис](#on-end-analysis).

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [оненданалисис](#on-end-analysis) .

## <a name="on-end-relogging-pass"></a>онендрелоггингпасс

Эта функция не может быть переопределена. Он вызывается пакетом C++ SDK для Build Insights, когда анализатор входит в группу переведения журнала. Эта функция перенаправляет вызов в [оненданалисиспасс](#on-end-analysis-pass).

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [оненданалисиспасс](#on-end-analysis-pass) .

## <a name="on-simple-event"></a>онсимпливент

Эта функция вызывается при обработке простого события. Вторую версию этой функции нельзя переопределить. Он вызывается пакетом C++ SDK для Build Insights, когда анализатор входит в группу переведения журнала. Все вызовы версии 2 перенаправляются на версию 1.

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

*евентстакк*\
Стек событий для этого простого события. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

*релогсессион*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-start-activity"></a>онстартактивити

Эта функция вызывается при обработке события начала действия. Вторую версию этой функции нельзя переопределить. Он вызывается пакетом C++ SDK для Build Insights, когда анализатор входит в группу переведения журнала. Все вызовы версии 2 перенаправляются на версию 1.

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

*евентстакк*\
Стек событий для события начала этого действия. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

*релогсессион*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

## <a name="on-stop-activity"></a>онстопактивити

Эта функция вызывается при обработке события завершения действия. Вторую версию этой функции нельзя переопределить. Он вызывается пакетом C++ SDK для Build Insights, когда анализатор входит в группу переведения журнала. Все вызовы версии 2 перенаправляются на версию 1.

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

*евентстакк*\
Стек событий для этого события завершения действия. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

*релогсессион*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

[Аналисисконтрол](analysis-control-enum-class.md) код, который описывает, что должно произойти далее.

::: moniker-end
