---
title: Константы RELOG_RETENTION_SYSTEM_EVENT_FLAGS
description: В C++ пакете SDK для аналитики сборки RELOG_RETENTION_SYSTEM_EVENT_FLAGS ссылки на константы.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 74afc10faa26ba39a669a05aa3e3cabd1a211293
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333968"
---
# <a name="relog_retention_system_event_flags-constants"></a>Константы RELOG_RETENTION_SYSTEM_EVENT_FLAGS

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Константы `RELOG_RETENTION_SYSTEM_EVENT_FLAGS` используются для описания системных событий, которые должны оставаться в журнале трассировки. Используйте их для инициализации поля `SystemEventsRetentionFlags` структуры [RELOG_DESCRIPTOR](relog-descriptor-struct.md) .

## <a name="syntax"></a>Синтаксис

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Сохраняет системные события выборки ЦП в трассировке с повторным протоколированием. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | Все системные события следует записывать в журнал трассировки. |

## <a name="remarks"></a>Remarks

::: moniker-end
