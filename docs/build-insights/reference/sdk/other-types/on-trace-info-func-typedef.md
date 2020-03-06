---
title: Определение типа Онтрацеинфофунк
description: Справочник C++ по ОНТРАЦЕИНФОФУНК typedef SDK для Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b168d6783b31454f6a2837bcad1fc81199ce9054
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333992"
---
# <a name="ontraceinfofunc-typedef"></a>Определение типа Онтрацеинфофунк

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

`OnTraceInfoFunc` typedef — одна из сигнатур функций, используемых в структурах [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) и [RELOG_CALLBACKS](relog-callbacks-struct.md) .

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*traceInfo*\
Объект [TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md) , содержащий сведения о трассировке, которая в данный момент анализируется или переписывается в журнал.

*callbackContext*\
Значение контекста, заданное для этого обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md).

### <a name="return-value"></a>Возвращаемое значение

Значение [CALLBACK_CODE](callback-code-enum.md) , которое определяет, что должно происходить далее.

::: moniker-end
