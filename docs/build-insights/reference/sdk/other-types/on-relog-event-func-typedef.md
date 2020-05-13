---
title: OnRelogEventFunc typedef
description: Ссылка на шрифт SDK OnRelogEventFunc.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2df8646d530c089b1239978d716b2b619a5b4b61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329070"
---
# <a name="onrelogeventfunc-typedef"></a>OnRelogEventFunc typedef

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Typedef `OnRelogEventFunc` является одной из подписей функций, используемых в [структуре RELOG_CALLBACKS.](relog-callbacks-struct.md)

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для текущего события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

*relogСессия*\
Указатель сеанса для использования при вызове [In-Event.](../functions/inject-event.md)

*обратный вызовКонтекст*\
Значение контекста, которое было установлено для этого обратного вызова [в RELOG_DESCRIPTOR.](analysis-descriptor-struct.md)

### <a name="return-value"></a>Возвращаемое значение

[Значение CALLBACK_CODE,](callback-code-enum.md) которое контролирует, что должно произойти дальше.

::: moniker-end
