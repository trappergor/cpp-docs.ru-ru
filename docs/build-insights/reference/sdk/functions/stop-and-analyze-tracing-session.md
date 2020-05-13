---
title: StopandAnalyzeTracingSession
description: Ссылка на функцию «Си- Сборка» SDK StopAndAnalyzeTracingSession.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c9bd4a092c22dfcdfb6d463b74207ec11ee6d64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323705"
---
# <a name="stopandanalyzetracingsession"></a>StopandAnalyzeTracingSession

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopAndAnalyzeTracingSession` останавливает текущий сеанс отслеживания и сохраняет полученный след во временном файле. Затем сеанс анализа немедленно начинает использовать временный файл в качестве ввода. Исполнители вызова этой функции должны иметь привилегии администратора.

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
Название сеанса отслеживания, чтобы остановить. Используйте то же имя сеанса, что и имя, которое было передано [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)или [StartTracingSessionW.](start-tracing-session-w.md)

*numberOfAnalysisPasses*\
Количество анализов проходит для запуска на следе. След проходит через предоставленную группу анализаторов один раз за анализ.

*Статистика*\
Указатель на [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) объект. `StopAndAnalyzeTracingSession`записывает статистику сбора следов на этом объекте перед возвращением.

*анализаторГруппа*\
Группа анализаторов, используемая для анализа. Позвоните [MakeStaticAnalyzerGroup,](make-static-analyzer-group.md) чтобы создать группу анализаторов. Если вы хотите использовать динамическую группу анализаторов, полученную от [MakeDynamicAnalyzerGroup,](make-dynamic-analyzer-group.md)сначала инкапсулируйте `MakeStaticAnalyzerGroup`его внутри группы статического анализатора, передав его адрес .

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
