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
ms.openlocfilehash: 7135c49bdf95ef5ba39db090c95ad46d266d8f65
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919661"
---
# <a name="tracing_session_statistics-structure"></a>Структура TRACING_SESSION_STATISTICS

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

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
