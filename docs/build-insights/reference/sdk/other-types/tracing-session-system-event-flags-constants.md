---
title: Константы TRACING_SESSION_SYSTEM_EVENT_FLAGS
description: Справочник по константам TRACING_SESSION_SYSTEM_EVENT_FLAGS пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 346c955355ffbc6c062a34bf928f16ccd3940154
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922370"
---
# <a name="tracing_session_system_event_flags-constants"></a>Константы TRACING_SESSION_SYSTEM_EVENT_FLAGS

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Константы `TRACING_SESSION_SYSTEM_EVENT_FLAGS` используются для описания системных событий, которые следует собирать при трассировке. С помощью констант вы можете инициализировать поле `SystemEventFlags` структуры [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md).

## <a name="syntax"></a>Синтаксис

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Члены

| Имя | События, включаемые с помощью этого флага |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | Этот флаг по умолчанию активируется событием пакета SDK для C++ Build Insights, даже если нет явного указания. Это обеспечивает надлежащее функционирование основных системных событий, необходимых для правильной работы C++ Build Insights. События, включенные с помощью этого флага, предоставляют сведения о процессах, потоках и загрузке изображений. Эти события отключить нельзя. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Примеры ЦП |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | Этот флаг позволяет включить все системные события. |

::: moniker-end
