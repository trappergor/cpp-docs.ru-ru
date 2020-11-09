---
title: Ключевое слово typedef для OnTraceInfoFunc
description: Справочник ключевому слову typedef для OnTraceInfoFunc пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4aaa865fd0f907a67179e7ee967f23a9827b0026
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922468"
---
# <a name="ontraceinfofunc-typedef"></a>Ключевое слово typedef для OnTraceInfoFunc

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

`OnTraceInfoFunc` typedef — одна из сигнатур функций, используемых в структурах [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) и [RELOG_CALLBACKS](relog-callbacks-struct.md).

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*traceInfo*\
Объект [TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md), содержащий сведения о трассировке, которая сейчас анализируется или повторно записывается.

*callbackContext*\
Значение контекста, заданное для этого обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md).

### <a name="return-value"></a>Возвращаемое значение

Значение [CALLBACK_CODE](callback-code-enum.md), определяющее следующее действие.

::: moniker-end
