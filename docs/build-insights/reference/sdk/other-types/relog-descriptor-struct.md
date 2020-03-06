---
title: Структура RELOG_DESCRIPTOR
description: В C++ пакете SDK для аналитики сборки RELOG_DESCRIPTOR ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f6f20835ed6535dd05def629200c113772e8f077
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333974"
---
# <a name="relog_descriptor-structure"></a>Структура RELOG_DESCRIPTOR

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `RELOG_DESCRIPTOR` используется с функциями [релога](../functions/relog-a.md) и [релогв](../functions/relog-w.md) . В нем описывается, как следует регистрировать трассировку трассировки событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct RELOG_DESCRIPTOR_TAG
{
    unsigned                NumberOfAnalysisPasses;
    ANALYSIS_CALLBACKS      AnalysisCallbacks;
    RELOG_CALLBACKS         RelogCallbacks;
    unsigned long long      SystemEventsRetentionFlags;
    void*                   AnalysisContext;
    void*                   RelogContext;
} RELOG_DESCRIPTOR;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `NumberOfAnalysisPasses` | Количество проходов анализа, которые должны быть выполнены над трассировкой ETW во время фазы анализа сеанса повторного ведения журнала. |
| `AnalysisCallbacks` | Объект [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) , указывающий, какие функции следует вызывать на этапе анализа сеанса перезаписи в журнал. |
| `RelogCallbacks` | Объект [RELOG_CALLBACKS](relog-callbacks-struct.md) , указывающий, какие функции следует вызывать на этапе переведения журнала сеанса перезаписи журнала. |
| `SystemEventsRetentionFlags` | Битовая маска [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) , указывающая системные события ETW, которые должны оставаться в журнале трассировки. |
| `AnalysisContext` | Предоставленный пользователем контекст, который передается в качестве аргумента всем функциям обратного вызова, указанным в `AnalysisCallbacks` |
| `RelogContext` | Предоставленный пользователем контекст, который передается в качестве аргумента всем функциям обратного вызова, указанным в `RelogCallbacks` |

## <a name="remarks"></a>Remarks

Пользователь с помощью функций обратного вызова, указанных в `RelogCallbacks`, управляет перезаписью событий ETW во время сеанса перезаписи в систему. Однако системные события ETW, такие как примеры ЦП, не пересылаются в эти функции обратного вызова. Используйте поле `SystemEventsRetentionFlags` для управления перезаписью системных событий трассировки событий Windows.

Структуры `AnalysisCallbacks` и `RelogCallbacks` принимают указатели только на функции, не являющиеся членами. Это ограничение можно обойти, задав для них указатель на объект. Этот указатель на объект будет передан как аргумент для всех функций обратного вызова, не являющихся членами. Этот указатель используется для вызова функций-членов из функций обратного вызова, не являющихся членами.

Фаза анализа сеанса перезаписи всегда выполняется до этапа перезаписи в журнал.

::: moniker-end
