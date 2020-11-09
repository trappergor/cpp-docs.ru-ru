---
title: StopAndAnalyzeTracingSession
description: Справочник по функции StopAndAnalyzeTracingSession пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81a8ce43ecedfa51874508193637969411ae52d6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922708"
---
# <a name="stopandanalyzetracingsession"></a>StopAndAnalyzeTracingSession

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `StopAndAnalyzeTracingSession` останавливает текущий сеанс трассировки и сохраняет итоговую трассировку во временном файле. Затем сразу же запускается сеанс анализа с использованием временного файла в качестве входных данных. Исполняемые файлы, вызывающие эту функцию, должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const char*                                   sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const wchar_t*                                sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, которое было передано в [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md) или [StartTracingSessionW](start-tracing-session-w.md).

*numberOfAnalysisPasses*\
Количество проходов анализа для выполнения в трассировке. Трассировка передается через предоставленную группу анализатора один раз для каждого выполнения анализа.

*statistics*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md). `StopAndAnalyzeTracingSession` записывает статистику сбора трассировки в этот объект перед возвратом.

*analyzerGroup*\
Группа анализатора, используемая для анализа. Вызовите [MakeStaticAnalyzerGroup](make-static-analyzer-group.md), чтобы создать группу анализатора. Чтобы использовать динамическую группу анализаторов, полученную из [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), сначала инкапсулируйте ее в статической группе анализаторов, передав ее адрес в `MakeStaticAnalyzerGroup`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
