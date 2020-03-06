---
title: Структура TRACING_SESSION_STATISTICS
description: В C++ пакете SDK для аналитики сборки TRACING_SESSION_OPTIONS ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9aa7c0a861d80fd3ebff85eb7ecb17dd05ae869e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333866"
---
# <a name="tracing_session_statistics-structure"></a>Структура TRACING_SESSION_STATISTICS

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TRACING_SESSION_STATISTICS` описывает статистику трассировки, которая была собрана. Его поля задаются при остановке сеанса трассировки.

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

## <a name="members"></a>Члены

|  |  |
|--|--|
| `MSVCEventsLost` | Число удаленных событий КОМПИЛЯТОРОМ MSVC. |
| `MSVCBuffersLost` | Число отброшенных буферов событий КОМПИЛЯТОРОМ MSVC. |
| `SystemEventsLost` | Количество системных событий, которые были удалены. |
| `SystemBuffersLost` | Количество буферов системных событий, которые были удалены. |

## <a name="remarks"></a>Remarks

Эта структура заполняется при вызове следующих функций:

- [стоптраЦингсессион](../functions/stop-tracing-session.md)
- [стоптраЦингсессиона](../functions/stop-tracing-session-a.md)
- [стоптраЦингсессионв](../functions/stop-tracing-session-w.md)
- [стопанданализетраЦингсессион](../functions/stop-and-analyze-tracing-session.md)
- [стопанданализетраЦингсессиона](../functions/stop-and-analyze-tracing-session-a.md)
- [стопанданализетраЦингсессионв](../functions/stop-and-analyze-tracing-session-w.md)
- [стопандрелогтраЦингсессион](../functions/stop-and-relog-tracing-session.md)
- [стопандрелогтраЦингсессиона](../functions/stop-and-relog-tracing-session-a.md)
- [стопандрелогтраЦингсессионв](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
