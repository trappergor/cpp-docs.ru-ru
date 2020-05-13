---
title: структура TRACING_SESSION_OPTIONS
description: Ссылка на структуру СЗ Build Insights SDK TRACING_SESSION_OPTIONS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5aeb6299aea8dc0661b9469ee524e7aa4d010aca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323426"
---
# <a name="tracing_session_options-structure"></a>структура TRACING_SESSION_OPTIONS

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TRACING_SESSION_OPTIONS` используется при инициализации [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) структуры. В нем описывается, какие события следует запечатлеть во время сбора следа.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `SystemEventFlags` | Битовая маска, описывающая события системы для захвата. Для получения дополнительной информации [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md)см. |
| `MsvcEventFlags` | Битовая маска, описывающая события MSVC для захвата. Для получения дополнительной информации, смотрите [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md). |

::: moniker-end
