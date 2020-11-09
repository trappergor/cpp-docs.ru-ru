---
title: StopAndAnalyzeTracingSessionW
description: Справочник по функции StopAndAnalyzeTracingSessionW пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e353e9d0038fcd764a9c4d03170f0a3c949bc43d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919986"
---
# <a name="stopandanalyzetracingsessionw"></a>StopAndAnalyzeTracingSessionW

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `StopAndAnalyzeTracingSessionW` останавливает текущий сеанс трассировки и сохраняет итоговую трассировку во временном файле. Затем сразу же запускается сеанс анализа с использованием временного файла в качестве входных данных. Исполняемые файлы, вызывающие эту функцию, должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionW(
    const wchar_t*              sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, которое было передано в [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md) или [StartTracingSessionW](start-tracing-session-w.md).

*statistics*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md). `StopAndAnalyzeTracingSessionW` записывает статистику сбора трассировки в этот объект перед возвратом.

*analysisDescriptor*\
Указатель на объект [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md). Используйте этот объект для настройки сеанса анализа в журнал, запущенного `StopAndAnalyzeTracingSessionW`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
