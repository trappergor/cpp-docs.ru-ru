---
title: Тип OnTraceInfoFunc
description: Ссылка на шрифт SDK OnTraceInfoFunc в т.д.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b987d4db9852c2e52c148bb91015ad414c04d41b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329023"
---
# <a name="ontraceinfofunc-typedef"></a>Тип OnTraceInfoFunc

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Typedef `OnTraceInfoFunc` является одной из подписей функций, используемых в [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) и [RELOG_CALLBACKS](relog-callbacks-struct.md) структурах.

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*traceInfo*\
Объект [TRACE_INFO_DATA,](../c-event-data-types/trace-info-data-struct.md) содержащий информацию о отслеживаемом или перелогированном в настоящее время следе.

*обратный вызовКонтекст*\
Значение контекста, которое было установлено для этого обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR.](relog-descriptor-struct.md)

### <a name="return-value"></a>Возвращаемое значение

[Значение CALLBACK_CODE,](callback-code-enum.md) которое контролирует, что должно произойти дальше.

::: moniker-end
