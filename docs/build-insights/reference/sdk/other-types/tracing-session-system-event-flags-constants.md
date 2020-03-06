---
title: Константы TRACING_SESSION_SYSTEM_EVENT_FLAGS
description: В C++ пакете SDK для аналитики сборки TRACING_SESSION_SYSTEM_EVENT_FLAGS ссылки на константы.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce0b0ea373ec53f0d5bcf228269299d69b49bb95
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333998"
---
# <a name="tracing_session_system_event_flags-constants"></a>Константы TRACING_SESSION_SYSTEM_EVENT_FLAGS

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Константы `TRACING_SESSION_SYSTEM_EVENT_FLAGS` используются для описания системных событий, которые должны быть собраны во время трассировки. Используйте их для инициализации поля `SystemEventFlags` структуры [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) .

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

| Имя | События, включенные этим флагом |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | Этот флаг активируется по умолчанию пакетом SDK для аналитики C++ сборки, даже если он не указан явным образом. Она обеспечивает правильную работу основных системных событий, C++ необходимых для правильной работы функции построения аналитики. События, включенные этим флагом, предоставляют сведения о процессах, потоках и загрузке изображений. Эти события отключить нельзя. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Примеры использования ЦП |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | Этот флаг включает все системные события. |

::: moniker-end
