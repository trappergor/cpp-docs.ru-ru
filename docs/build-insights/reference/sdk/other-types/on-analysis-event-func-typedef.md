---
title: OnAnalysisEventFunc typedef
description: Ссылка на шрифт SDK OnAnalysisFunc.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eacd174279caff0db22586d5e40d3a866afc4459
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329127"
---
# <a name="onanalysiseventfunc-typedef"></a>OnAnalysisEventFunc typedef

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Typedef `OnAnalysisEventFunc` является одной из подписей функций, используемых в [структуре ANALYSIS_CALLBACKS.](analysis-callbacks-struct.md)

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для текущего события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

*обратный вызовКонтекст*\
Значение контекста, которое было установлено для этого обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR.](relog-descriptor-struct.md)

### <a name="return-value"></a>Возвращаемое значение

[Значение CALLBACK_CODE,](callback-code-enum.md) которое контролирует, что должно произойти дальше.

::: moniker-end
