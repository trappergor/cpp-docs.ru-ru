---
title: Ключевое слово typedef для OnRelogEventFunc
description: Справочник ключевому слову typedef для OnRelogEventFunc пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ed639ab59b900f97d29dc69240e45b2f52f2f3b3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919752"
---
# <a name="onrelogeventfunc-typedef"></a>Ключевое слово typedef для OnRelogEventFunc

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Ключевое слово typedef `OnRelogEventFunc` — это одна из сигнатур функций, используемых в структуре [RELOG_CALLBACKS](relog-callbacks-struct.md).

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*eventStack*\
Стек событий для текущего события. Дополнительные сведения о стеках событий см. в [этой статье](../event-table.md).

*relogSession*\
Указатель сеанса повторной записи в журнал для использования при вызове [InjectEvent](../functions/inject-event.md).

*callbackContext*\
Значение контекста, заданное для этого обратного вызова в [RELOG_DESCRIPTOR](analysis-descriptor-struct.md).

### <a name="return-value"></a>Возвращаемое значение

Значение [CALLBACK_CODE](callback-code-enum.md), определяющее следующее действие.

::: moniker-end
