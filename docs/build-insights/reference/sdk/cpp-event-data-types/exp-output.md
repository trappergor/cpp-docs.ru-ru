---
title: Класс ExpOutput
description: Ссылка на ss Build Insights SDK ExpOutput.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExpOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4c8c5f2f260596c444df7841c2a3e0c65f5163f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324820"
---
# <a name="expoutput-class"></a>Класс ExpOutput

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `ExpOutput` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [EXP_OUTPUT](../event-table.md#exp-output) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class ExpOutput : public FileOutput
{
public:
    ExpOutput(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `ExpOutput` своего базового класса [FileOutput,](file-output.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ExpOutput](#exp-output)

## <a name="expoutput"></a><a name="exp-output"></a>ExpOutput

```cpp
ExpOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [EXP_OUTPUT.](../event-table.md#exp-output)

::: moniker-end
