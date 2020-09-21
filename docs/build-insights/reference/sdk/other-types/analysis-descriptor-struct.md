---
title: Структура ANALYSIS_DESCRIPTOR
description: Справочник по структуре ANALYSIS_DESCRIPTOR из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 325910f747f75f1f8d2904c248f8de69566464c7
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042008"
---
# <a name="analysis_descriptor-structure"></a>Структура ANALYSIS_DESCRIPTOR

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `ANALYSIS_DESCRIPTOR` используется с функциями [AnalyzeA](../functions/analyze-a.md) и [AnalyzeW](../functions/analyze-w.md). В ней описывается, как следует анализировать трассировку событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `NumberOfPasses` | Количество этапов анализа, которые следует выполнить во время трассировки событий Windows. |
| `Callbacks` | Объект [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md), указывающий, какие функции следует вызывать во время сеанса анализа. |
| `Context` | Пользовательский контекст, передаваемый в качестве аргумента всем функциям обратного вызова, указанным в `Callbacks`. |

## <a name="remarks"></a>Remarks

Структура `Callbacks` принимает указатели только на функции, не являющиеся членами. Это ограничение можно обойти, установив для указателя объекта значение `Context`. Этот указатель объекта будет передан в качестве аргумента для всех функций обратного вызова, не являющихся членами. Используйте этот указатель для вызова функций-членов из функций обратного вызова, не являющихся членами.

::: moniker-end
