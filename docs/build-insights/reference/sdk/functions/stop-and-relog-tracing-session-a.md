---
title: StopAndRelogTracingSessionA
description: Справочник по функции StopAndRelogTracingSessionA пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: de69ca379c6f0ef46e23d2b4a78c72518e997572
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919973"
---
# <a name="stopandrelogtracingsessiona"></a>StopAndRelogTracingSessionA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `StopAndRelogTracingSessionA` останавливает текущий сеанс трассировки и сохраняет итоговую трассировку во временном файле. Затем сразу же запускается сеанс повторной записи в журнал с использованием временного файла в качестве входных данных. Окончательные повторно записанные данные трассировки, созданные сеансом повторной записи в журнал, сохраняются в файле, указанном вызывающей стороной. Исполняемые файлы, вызывающие эту функцию, должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopAndRelogTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, которое было передано в [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md) или [StartTracingSessionW](start-tracing-session-w.md).

*outputLogFile*\
Файл, в который записываются повторно записанные данные трассировки, созданные сеансом повторной записи в журнал.

*statistics*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md). `StopAndRelogTracingSessionA` записывает статистику сбора трассировки в этот объект перед возвратом.

*analysisDescriptor*\
Указатель на объект [RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md). Используйте этот объект для настройки сеанса повторной записи в журнал, запущенного `StopAndRelogTracingSessionA`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
