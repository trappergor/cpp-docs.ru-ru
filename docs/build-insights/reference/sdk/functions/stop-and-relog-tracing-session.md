---
title: стопандрелогтраЦингсессион
description: Справочник C++ по функциям SDK для Build Insights стопандрелогтраЦингсессион.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e99568f9b509b89ccd0f0711433dec9d96d904bc
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334202"
---
# <a name="stopandrelogtracingsession"></a>стопандрелогтраЦингсессион

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopAndRelogTracingSession` останавливает текущий сеанс трассировки и сохраняет результирующую трассировку во временном файле. Затем сеанс повторного ведения журнала сразу же запускается с использованием временного файла в качестве входных данных. Окончательная трассировка с регистрацией, созданная сеансом перезаписи, сохраняется в файле, указанном вызывающим объектом. Исполняемые файлы, вызывающие эту функцию, должны иметь права администратора.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const char*                                   sessionName,
    const char*                                   outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const wchar_t*                                sessionName,
    const wchar_t*                                outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, что и переданное в [старттраЦингсессион](start-tracing-session.md), [старттраЦингсессиона](start-tracing-session-a.md)или [старттраЦингсессионв](start-tracing-session-w.md).

*аутпутлогфиле*\
Файл, в который записывается Записанная в журнал трассировка, созданная сеансом повторного ведения журнала.

*статистика*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopAndRelogTracingSession` записывает статистику сбора трассировки в этот объект перед возвратом.

*нумберофаналисиспассес*\
Количество проходов анализа, которые необходимо выполнить для трассировки. Трассировка передается через предоставленную группу анализаторов один раз для каждого этапа анализа.

*системевентсретентионфлагс*\
Битовая маска [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) , указывающая системные события ETW, которые должны оставаться в журнале трассировки.

*анализерграуп*\
Группа анализатора, используемая для фазы анализа сеанса повторного ведения журнала. Вызовите [макестатиканализерграуп](make-static-analyzer-group.md) , чтобы создать группу анализатора. Если вы хотите использовать динамическую группу анализатора, полученную из [макединамиканализерграуп](make-dynamic-analyzer-group.md), сначала необходимо инкапсулировать ее в статическую группу анализатора, передав ее адрес в `MakeStaticAnalyzerGroup`.

*релогжерграуп*\
Группа переведения журнала, которая выполняет перезапись событий в файл трассировки, указанный в *аутпутлогфиле*. Вызовите [макестатикрелогжерграуп](make-static-relogger-group.md) , чтобы создать группу повторного ведения журнала. Если вы хотите использовать динамическую группу переведения журнала, полученную из [макединамикрелогжерграуп](make-dynamic-relogger-group.md), сначала необходимо инкапсулировать ее в группу "статическая регистрация", передав ее адрес в `MakeStaticReloggerGroup`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

### <a name="remarks"></a>Remarks

Входная трассировка передается через группу анализатора *нумберофаналисиспассес* раз. Для проходов перезаписи не существует аналогичного варианта. Трассировка передается траугх только один раз после завершения всех этапов анализа.

Перезапись системных событий, таких как примеры ЦП, из класса, переданного в журнал, не поддерживается. Используйте параметр *системевентсретентионфлагс* , чтобы решить, какие системные события следует отслеживать в выходной трассировке.

::: moniker-end
