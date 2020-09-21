---
title: Структура RELOG_CALLBACKS
description: Справочник по структуре RELOG_CALLBACKS из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 55f63b05691e3d729ee42ed21049669b94053559
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041436"
---
# <a name="relog_callbacks-structure"></a>Структура RELOG_CALLBACKS

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `RELOG_CALLBACKS` используется при инициализации объекта [RELOG_DESCRIPTOR](relog-descriptor-struct.md). Она указывает, какие функции следует вызвать во время повторной записи трассировки событий Windows (ETW).

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

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `OnStartActivity` | Вызывается для обработки события запуска действия. |
| `OnStopActivity` | Вызывается для обработки события остановки действия. |
| `OnSimpleEvent` | Вызывается для обработки простого события. |
| `OnTraceInfo` | Вызывается один раз в начале прохода повторной записи после вызова `OnBeginReloggingPass`. |
| `OnBeginRelogging` | Вызывается при запуске сеанса повторной записи до начала прохода повторной записи. |
| `OnEndRelogging` | Вызывается в конце сеанса повторной записи после завершения прохода повторной записи. |
| `OnBeginReloggingPass` | Вызывается в начале прохода анализа повторной записи в журнал перед обработкой события. |
| `OnEndReloggingPass` | Вызывается в конце прохода анализа повторной записи после обработки всех событий. |

## <a name="remarks"></a>Remarks

Все члены структуры `RELOG_CALLBACKS` должны указывать на допустимую функцию. Дополнительные сведения о допустимых сигнатурах функций см. в документации по [OnRelogEventFunc](on-relog-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md) и [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
