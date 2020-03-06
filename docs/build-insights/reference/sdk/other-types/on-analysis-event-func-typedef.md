---
title: Определение типа Онаналисисевентфунк
description: Справочник C++ по ОНАНАЛИСИСЕВЕНТФУНК typedef SDK для Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d260f6060e759f315589abda82e31c2c2b95a65e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334064"
---
# <a name="onanalysiseventfunc-typedef"></a>Определение типа Онаналисисевентфунк

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

`OnAnalysisEventFunc` typedef — одна из сигнатур функций, используемых в структуре [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) .

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*евентстакк*\
Стек событий для текущего события. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

*callbackContext*\
Значение контекста, заданное для этого обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md).

### <a name="return-value"></a>Возвращаемое значение

Значение [CALLBACK_CODE](callback-code-enum.md) , которое определяет, что должно происходить далее.

::: moniker-end
