---
title: Ключевое слово typedef для OnAnalysisEventFunc
description: Справочник по ключевому слову typedef для OnAnalysisEventFunc пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 069c89a01fa466e86986a821e5dd9d0b09f5c81a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919792"
---
# <a name="onanalysiseventfunc-typedef"></a>Ключевое слово typedef для OnAnalysisEventFunc

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Ключевое слово typedef `OnAnalysisEventFunc` — это одна из сигнатур функций, используемых в структуре [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md).

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для текущего события. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

*callbackContext*\
Значение контекста, заданное для этого обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md).

### <a name="return-value"></a>Возвращаемое значение

Значение [CALLBACK_CODE](callback-code-enum.md), определяющее следующее действие.

::: moniker-end
