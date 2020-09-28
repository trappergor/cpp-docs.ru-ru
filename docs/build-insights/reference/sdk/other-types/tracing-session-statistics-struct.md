---
title: Структура TRACING_SESSION_STATISTICS
description: Справочник по структуре TRACING_SESSION_STATISTICS из пакета SDK для Аналитики сборок C++ Build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c1db302d9e816591624f0fc63633351d32684097
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742766"
---
# <a name="tracing_session_statistics-structure"></a>Структура TRACING_SESSION_STATISTICS

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В структуре `TRACING_SESSION_STATISTICS` описана статистика собранных данных трассировки. Значения полей задаются после остановки сеанса трассировки.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TRACING_SESSION_STATISTICS_TAG
{
    unsigned long MSVCEventsLost;
    unsigned long MSVCBuffersLost;
    unsigned long SystemEventsLost;
    unsigned long SystemBuffersLost;

} TRACING_SESSION_STATISTICS;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `MSVCEventsLost` | Количество удаленных событий MSVC. |
| `MSVCBuffersLost` | Количество удаленных буферов событий MSVC. |
| `SystemEventsLost` | Количество удаленных системных событий. |
| `SystemBuffersLost` | Количество удаленных буферов системных событий. |

## <a name="remarks"></a>Remarks

Эта структура заполняется при вызове следующих функций:

- [StopTracingSession](../functions/stop-tracing-session.md)
- [StopTracingSessionA](../functions/stop-tracing-session-a.md)
- [StopTracingSessionW](../functions/stop-tracing-session-w.md)
- [StopAndAnalyzeTracingSession](../functions/stop-and-analyze-tracing-session.md)
- [StopAndAnalyzeTracingSessionA](../functions/stop-and-analyze-tracing-session-a.md)
- [StopAndAnalyzeTracingSessionW](../functions/stop-and-analyze-tracing-session-w.md)
- [StopAndRelogTracingSession](../functions/stop-and-relog-tracing-session.md)
- [StopAndRelogTracingSessionA](../functions/stop-and-relog-tracing-session-a.md)
- [StopAndRelogTracingSessionW](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
