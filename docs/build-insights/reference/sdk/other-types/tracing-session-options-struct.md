---
title: Структура TRACING_SESSION_OPTIONS
description: Справочник по структуре TRACING_SESSION_OPTIONS из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f7c53abc14c4862ccb73f94acd2e325eb3d4a6fa
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742779"
---
# <a name="tracing_session_options-structure"></a>Структура TRACING_SESSION_OPTIONS

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TRACING_SESSION_OPTIONS` используется при инициализации структуры [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md). Она описывает, какие события следует отслеживать во время сбора данных трассировки.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `SystemEventFlags` | Битовая маска, описывающая системные события для отслеживания. Дополнительные сведения см. в статье о [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md). |
| `MsvcEventFlags` | Битовая маска, описывающая события MSVC для отслеживания. Дополнительные сведения см. в статье о [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md). |

::: moniker-end
