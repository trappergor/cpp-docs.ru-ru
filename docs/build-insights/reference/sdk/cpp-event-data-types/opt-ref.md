---
title: Класс OptRef
description: Ссылка на исследования в отношении СДК OptRef.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dca8cc62eed4b7136f88ed5ba6a1a168b2de56c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324448"
---
# <a name="optref-class"></a>Класс OptRef

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `OptRef` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [OPT_REF](../event-table.md#opt-ref) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class OptRef : public Activity
{
public:
    OptRef(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены `OptRef` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[OptRef](#opt-ref)

## <a name="optref"></a><a name="opt-ref"></a>OptRef

```cpp
OptRef(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие OPT_REF.](../event-table.md#opt-ref)

::: moniker-end
