---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS константы
description: Ссылка на констант SDK Build Insights sDK TRACING_SESSION_SYSTEM_EVENT_FLAGS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 264d697cc905eb6b44c8ec7de835a552976f0eb8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323275"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS константы

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Константы `TRACING_SESSION_SYSTEM_EVENT_FLAGS` используются для описания событий системы для сбора во время трассы. Используйте их для [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) инициализации `SystemEventFlags` поля TRACING_SESSION_OPTIONS структуры.

## <a name="syntax"></a>Синтаксис

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Участники

| Имя | События, включенные этим флагом |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | Этот флаг активируется по умолчанию SDK Build Insights, даже если он не указан явно. Это позволяет основным системным событиям, которые требуются от исследования сот., функционировать должным образом. События, включенные этим флагом, предоставляют информацию о процессах, потоках и загрузке изображений. Вы не можете отключить эти события. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Образцы процессора |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | Этот флаг включает все системные события. |

::: moniker-end
