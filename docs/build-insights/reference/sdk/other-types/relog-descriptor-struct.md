---
title: Структура RELOG_DESCRIPTOR
description: Справочник по структуре RELOG_DESCRIPTOR из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 802e51ec4246f5ee95e3d204290743ffbd03be69
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041397"
---
# <a name="relog_descriptor-structure"></a>Структура RELOG_DESCRIPTOR

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `RELOG_DESCRIPTOR` используется с функциями [RelogA](../functions/relog-a.md) и [RelogW](../functions/relog-w.md). В ней описывается, как следует повторно записывать трассировку событий Windows (ETW).

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

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `NumberOfAnalysisPasses` | Количество проходов анализа, которые следует выполнить во время трассировки событий Windows на этапе анализа сеанса повторной записи в журнал. |
| `AnalysisCallbacks` | Объект [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md), указывающий, какие функции следует вызывать во время этапа анализа сеанса повторной записи в журнал. |
| `RelogCallbacks` | Объект [RELOG_CALLBACKS](relog-callbacks-struct.md), указывающий, какие функции следует вызывать во время этапа повторной записи в журнал сеанса повторной записи в журнал. |
| `SystemEventsRetentionFlags` | Битовая маска [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md), указывающая, какие системные события трассировки событий Windows следует сохранить в повторно записанных трассировках. |
| `AnalysisContext` | Пользовательский контекст, передаваемый в качестве аргумента всем функциям обратного вызова, указанным в `AnalysisCallbacks`. |
| `RelogContext` | Пользовательский контекст, передаваемый в качестве аргумента всем функциям обратного вызова, указанным в `RelogCallbacks`. |

## <a name="remarks"></a>Remarks

Повторная запись трассировки событий Windows во время сеанса повторной записи управляется пользователем с помощью функций обратного вызова, указанных в `RelogCallbacks`. Однако системные события трассировки событий Windows, такие как примеры ЦП, не передаются в эти функции обратного вызова. Используйте поле `SystemEventsRetentionFlags` для управления повторной записью системных событий трассировки событий Windows.

Структуры `AnalysisCallbacks` и `RelogCallbacks` принимают только указатели на функции, не являющиеся членами. Это ограничение можно обойти, установив для них указатель объекта. Этот указатель объекта будет передан в качестве аргумента для всех функций обратного вызова, не являющихся членами. Используйте этот указатель для вызова функций-членов из функций обратного вызова, не являющихся членами.

Этап анализа сеанса повторной записи всегда выполняется перед этапом повторной записи.

::: moniker-end
