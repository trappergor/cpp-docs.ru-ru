---
title: Определение типа Онреложевентфунк
description: Справочник C++ по ОНРЕЛОЖЕВЕНТФУНК typedef SDK для Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 619f9a142ad19a7809b867eda93f2db634825a8f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334028"
---
# <a name="onrelogeventfunc-typedef"></a>Определение типа Онреложевентфунк

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

`OnRelogEventFunc` typedef — одна из сигнатур функций, используемых в структуре [RELOG_CALLBACKS](relog-callbacks-struct.md) .

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*евентстакк*\
Стек событий для текущего события. Дополнительные сведения о стеках событий см. в разделе [события](../event-table.md).

*релогсессион*\
Указатель сеанса перезаписи, используемый при вызове [инжектевент](../functions/inject-event.md).

*callbackContext*\
Значение контекста, заданное для этого обратного вызова в [RELOG_DESCRIPTOR](analysis-descriptor-struct.md).

### <a name="return-value"></a>Возвращаемое значение

Значение [CALLBACK_CODE](callback-code-enum.md) , которое определяет, что должно происходить далее.

::: moniker-end
