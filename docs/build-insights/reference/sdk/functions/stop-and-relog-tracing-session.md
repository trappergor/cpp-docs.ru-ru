---
title: StopAndRelogTracingSession
description: Справочник по функции StopAndRelogTracingSession пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d36dee1b16ca467d16b22587abe3ef34ee6ccb29
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919960"
---
# <a name="stopandrelogtracingsession"></a>StopAndRelogTracingSession

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `StopAndRelogTracingSession` останавливает текущий сеанс трассировки и сохраняет итоговую трассировку во временном файле. Затем сеанс повторной записи в журнал сразу же запускается, используя временный файл в качестве входных данных. Окончательные повторно записанные данные трассировки, созданные сеансом повторной записи в журнал, сохраняются в файле, указанном вызывающей стороной. Исполняемые файлы, вызывающие эту функцию, должны иметь привилегии администратора.

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
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, которое было передано в [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md) или [StartTracingSessionW](start-tracing-session-w.md).

*outputLogFile*\
Файл, в который записываются повторно записанные данные трассировки, созданные сеансом повторной записи в журнал.

*statistics*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md). `StopAndRelogTracingSession` записывает статистику сбора трассировки в этот объект перед возвратом.

*numberOfAnalysisPasses*\
Количество проходов анализа, которые необходимо выполнить во время трассировки. Данные трассировки передаются через предоставленную группу анализаторов один раз для каждого прохода анализа.

*systemEventsRetentionFlags*\
Битовая маска [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md), указывающая, какие системные события трассировки событий Windows следует сохранить в повторно записанных трассировках.

*analyzerGroup*\
Группа анализатора, используемая для анализа сеанса повторной записи в журнал. Вызовите [MakeStaticAnalyzerGroup](make-static-analyzer-group.md), чтобы создать группу анализатора. Если нужно использовать группу динамического анализатора, полученную из [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), необходимо сначала инкапсулировать ее в статической группе анализатора, передав ее адрес в `MakeStaticAnalyzerGroup`.

*reloggerGroup*\
Группа повторной записи в журнал, которая выполняет перезапись событий в файл трассировки, указанный в *outputLogFile*. Вызовите [MakeStaticReloggerGroup](make-static-relogger-group.md), чтобы создать группу повторной записи в журнал. Если нужно использовать динамическую группу повторной записи в журнал, полученную из [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md), сначала нужно инкапсулировать ее в статической группе повторной записи в журнал, передав ее адрес в `MakeStaticReloggerGroup`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

### <a name="remarks"></a>Комментарии

Входная трассировка передается через группу анализатора такое количество раз: *numberOfAnalysisPasses*. Для проходов повторной записи в журнал не существует аналогичного параметра. Трассировка передается через группу повторной записи в журнал только один раз после завершения всех этапов анализа.

Повторная запись в журнал системных событий, таких как примеры ЦП, из класса повторной записи в журнал не поддерживается. Используйте параметр *systemEventsRetentionFlags* , чтобы решить, какие системные события следует хранить в выходной трассировке.

::: moniker-end
