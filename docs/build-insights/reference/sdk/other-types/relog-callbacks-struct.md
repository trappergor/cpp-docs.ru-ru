---
title: Структура RELOG_CALLBACKS
description: В C++ пакете SDK для аналитики сборки RELOG_CALLBACKS ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c5dbed196e6cafaa301b6e07cd0f5546a0f4d563
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333986"
---
# <a name="relog_callbacks-structure"></a>Структура RELOG_CALLBACKS

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `RELOG_CALLBACKS` используется при инициализации объекта [RELOG_DESCRIPTOR](relog-descriptor-struct.md) . Он указывает, какие функции следует вызывать во время перезаписи трассировки трассировки событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct RELOG_CALLBACKS_TAG
{
    OnRelogEventFunc        OnStartActivity;
    OnRelogEventFunc        OnStopActivity;
    OnRelogEventFunc        OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginRelogging;
    OnBeginEndPassFunc      OnEndRelogging;
    OnBeginEndPassFunc      OnBeginReloggingPass;
    OnBeginEndPassFunc      OnEndReloggingPass;
} RELOG_CALLBACKS;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `OnStartActivity` | Вызывается для обработки события начала действия. |
| `OnStopActivity` | Вызывается для обработки события завершения действия. |
| `OnSimpleEvent` | Вызывается для обработки простого события. |
| `OnTraceInfo` | Вызывается один раз в начале прохода перезаписи после вызова `OnBeginReloggingPass`. |
| `OnBeginRelogging` | Вызывается при запуске сеанса перезаписи в систему до начала передачи журнала. |
| `OnEndRelogging` | Вызывается при завершении сеанса перезаписи после завершения перезаписи. |
| `OnBeginReloggingPass` | Вызывается при начале перезаписи перед обработкой любого события. |
| `OnEndReloggingPass` | Вызывается при завершении прохода перезаписи после обработки всех событий. |

## <a name="remarks"></a>Remarks

Все члены структуры `RELOG_CALLBACKS` должны указывать на допустимую функцию. Дополнительные сведения о допустимых сигнатурах функций см. в разделе [онреложевентфунк](on-relog-event-func-typedef.md), [онтрацеинфофунк](on-trace-info-func-typedef.md)и [онбегинендпассфунк](on-begin-end-pass-func-typedef.md).

::: moniker-end
