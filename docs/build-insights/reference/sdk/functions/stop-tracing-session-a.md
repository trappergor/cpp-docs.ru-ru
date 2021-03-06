---
title: StopTracingSessionA
description: Справочник по функции StopTracingSessionA пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 211538c1756d41b91dab6d43f33f4b4a41ceb70c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922647"
---
# <a name="stoptracingsessiona"></a>StopTracingSessionA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `StopTracingSessionA` останавливает текущий сеанс трассировки и создает необработанный файл трассировки. Необработанные файлы трассировки можно передать в функции [Analyze](analyze.md), [AnalzeA](analyze-a.md) и [AnalyzeW](analyze-w.md) для запуска сеанса анализа. Кроме того, необработанные файлы трассировки можно передать в функции [Relog](relog.md), [RelogA](relog-a.md) и [RelogW](relog-w.md) для запуска сеанса повторной записи в журнал. Исполняемые файлы, вызывающие `StopTracingSessionA`, должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, которое было передано в [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md) или [StartTracingSessionW](start-tracing-session-w.md).

*outputLogFile*\
Путь к окончательному выходному файлу журнала, в котором должны быть сохранены необработанные данные трассировки.

*statistics*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md). `StopTracingSessionA` записывает статистику сбора трассировки в этот объект перед возвратом.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
