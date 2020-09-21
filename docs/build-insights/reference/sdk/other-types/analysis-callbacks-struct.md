---
title: Структура ANALYSIS_CALLBACKS
description: Справочник по структуре ANALYSIS_CALLBACKS из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a24755befdd446051ae376b49d3dca06c7bc3320
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041046"
---
# <a name="analysis_callbacks-structure"></a>Структура ANALYSIS_CALLBACKS

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `ANALYSIS_CALLBACKS` используется при инициализации объекта [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md). Она указывает, какие функции следует вызвать во время анализа или повторной записи трассировки событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct ANALYSIS_CALLBACKS_TAG
{
    OnAnalysisEventFunc     OnStartActivity;
    OnAnalysisEventFunc     OnStopActivity;
    OnAnalysisEventFunc     OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginAnalysis;
    OnBeginEndPassFunc      OnEndAnalysis;
    OnBeginEndPassFunc      OnBeginAnalysisPass;
    OnBeginEndPassFunc      OnEndAnalysisPass;
} ANALYSIS_CALLBACKS;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `OnStartActivity` | Вызывается для обработки события запуска действия. |
| `OnStopActivity` | Вызывается для обработки события остановки действия. |
| `OnSimpleEvent` | Вызывается для обработки простого события. |
| `OnTraceInfo` | Используется для сеансов анализа, вызываемых в начале каждого прохода анализа. Используется для сеансов повторной записи в журнал, которые вызываются в начале каждого прохода анализа, а также в начале прохода повторной записи. Эта функция вызывается только после вызова OnBeginAnalysisPass. |
| `OnBeginAnalysis` | Используется для сеансов анализа, вызванных до начала любого прохода анализа. Используется для сеансов повторной записи в журнал, которые дважды вызываются до начала фазы анализа. Один раз, чтобы сообщить о начале сеанса повторной записи в журнал, а второй, — чтобы сообщить о начале прохода анализа. |
| `OnEndAnalysis` | Для сеансов анализа эта функция вызывается после завершения всех проходов анализа. Для сеансов повторной записи в журнал эта функция вызывается после завершения всех проходов анализа фазы анализа. Затем она вызывается снова после завершения прохода повторной записи в журнал. |
| `OnBeginAnalysisPass` | Вызывается в начале прохода анализа или прохода повторной записи в журнал перед обработкой события. |
| `OnEndAnalysisPass` | Вызывается в конце прохода анализа или прохода повторной записи в журнал после обработки всех событий. |

## <a name="remarks"></a>Remarks

Фаза анализа сеанса повторной записи в журнал является частью прохода повторной записи в журнал и может содержать несколько проходов анализа. По этой причине `OnBeginAnalysis` дважды вызывается в строке в начале сеанса повторной записи в журнал. `OnEndAnalysis` вызывается в конце фазы анализа до начала фазы повторной записи в журнал и еще раз в конце этой фазы. Фаза повторной записи в журнал всегда имеет один проход повторной записи в журнал.

Анализаторы могут быть частью анализа и фазы повторной записи в журнал сеанса повторной записи в журнал. Эти анализаторы могут определять, какая фаза в настоящее время выполняется, отслеживая пары вызовов OnBeginAnalysis и `OnEndAnalysis`. Если `OnBeginAnalysis` вызывается дважды без вызова `OnEndAnalysis`, это означает, что выполняется фаза анализа. Если `OnBeginAnalysis` вызывается дважды, а `OnEndAnalysis` — один раз, это означает, что выполняется фаза повторной записи в журнал. Если OnBeginAnalysis и `OnEndAnalysis` вызываются дважды, это означает, что обе фазы закончились.

Все члены структуры `ANALYSIS_CALLBACKS` должны указывать на допустимую функцию. Дополнительные сведения о допустимых сигнатурах функций см. в документации по [OnAnalysisEventFunc](on-analysis-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md) и [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
