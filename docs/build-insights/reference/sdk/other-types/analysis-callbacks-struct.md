---
title: Структура ANALYSIS_CALLBACKS
description: В C++ пакете SDK для аналитики сборки ANALYSIS_CALLBACKS ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8c35e740d97488969a6b69467d54412297e49227
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334148"
---
# <a name="analysis_callbacks-structure"></a>Структура ANALYSIS_CALLBACKS

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `ANALYSIS_CALLBACKS` используется при инициализации объекта [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) . Он указывает, какие функции должны вызываться во время анализа или при переведении трассировки трассировки событий Windows (ETW).

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

## <a name="members"></a>Члены

|  |  |
|--|--|
| `OnStartActivity` | Вызывается для обработки события начала действия. |
| `OnStopActivity` | Вызывается для обработки события завершения действия. |
| `OnSimpleEvent` | Вызывается для обработки простого события. |
| `OnTraceInfo` | Для сеансов анализа, вызываемых в начале каждого прохода анализа. Для сеансов повторного ведения журнала, которые вызываются в начале каждого прохода анализа, и снова в начале прохода перезаписи. Эта функция вызывается только после вызова Онбегинаналисиспасс. |
| `OnBeginAnalysis` | Для сеансов анализа, вызванных до начала любого этапа анализа. Для сеансов повторного ведения журнала, которые вызываются дважды до начала фазы анализа: один раз, чтобы объявить начало сеанса повторного ведения журнала, и еще один раз, чтобы объявить начало фазы анализа. |
| `OnEndAnalysis` | Для сеансов анализа эта функция вызывается после завершения всех этапов анализа. Для сеансов перезаписи в журнал Эта функция вызывается после завершения всех этапов анализа этапа анализа. Затем он вызывается снова после завершения этапа повторного ведения журнала. |
| `OnBeginAnalysisPass` | Вызывается при начале прохода анализа или перезаписи перед обработкой любого события. |
| `OnEndAnalysisPass` | Вызывается при завершении прохода анализа или перезаписи после обработки всех событий. |

## <a name="remarks"></a>Remarks

Фаза анализа сеанса перезаписи журнала рассматривается как часть сеанса перезаписи в журнал и может содержать несколько этапов анализа. По этой причине `OnBeginAnalysis` вызывается дважды в строке в начале сеанса повторного ведения журнала. `OnEndAnalysis` вызывается в конце фазы анализа до начала этапа повторного ведения журнала и еще раз в конце фазы перезаписи журнала. Этап переведения журнала всегда содержит один проход перезаписи.

Анализаторы могут быть частью анализа и этапа перезаписи сеанса перезаписи в журнал. Эти анализаторы могут определить, какой этап в настоящее время выполняется, отслеживая пары вызовов Онбегинаналисис и `OnEndAnalysis`. Два `OnBeginAnalysis`ных вызова без вызова `OnEndAnalysis` означает, что этап анализа выполняется. Два `OnBeginAnalysis`ных вызова и один вызов `OnEndAnalysis` означает, что этап переведения журнала выполняется непрерывно. Два Онбегинаналисис и два вызова `OnEndAnalysis` означают, что оба этапа завершены.

Все члены структуры `ANALYSIS_CALLBACKS` должны указывать на допустимую функцию. Дополнительные сведения о допустимых сигнатурах функций см. в разделе [онаналисисевентфунк](on-analysis-event-func-typedef.md), [онтрацеинфофунк](on-trace-info-func-typedef.md)и [онбегинендпассфунк](on-begin-end-pass-func-typedef.md).

::: moniker-end
