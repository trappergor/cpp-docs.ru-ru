---
title: Константы RELOG_RETENTION_SYSTEM_EVENT_FLAGS
description: Справочник по константам RELOG_RETENTION_SYSTEM_EVENT_FLAGS из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e0144835568dab12c8593fe8fbfa820f6cde7647
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919738"
---
# <a name="relog_retention_system_event_flags-constants"></a>Константы RELOG_RETENTION_SYSTEM_EVENT_FLAGS

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Константы `RELOG_RETENTION_SYSTEM_EVENT_FLAGS` используются для описания системных событий, которые следует сохранять в повторно записанных данных трассировки. Используйте их для инициализации поля `SystemEventsRetentionFlags` структуры [RELOG_DESCRIPTOR](relog-descriptor-struct.md).

## <a name="syntax"></a>Синтаксис

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Сохраняет системные события примера ЦП в повторно записанных данных трассировки. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | Сохраняет все системные события ЦП в повторно записанных данных трассировки. |

## <a name="remarks"></a>Комментарии

::: moniker-end
