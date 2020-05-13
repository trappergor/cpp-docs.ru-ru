---
title: Класс LibOutput
description: Ссылка на класс SDK LibOutput.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fda7b471759a9c49937214bb2176473226668776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324626"
---
# <a name="liboutput-class"></a>Класс LibOutput

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `LibOutput` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для сопоставления [LIB_OUTPUT](../event-table.md#lib-output) события.

## <a name="syntax"></a>Синтаксис

```cpp
class LibOutput : public FileOutput
{
public:
    LibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `LibOutput` своего базового класса [FileOutput,](file-output.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[LibOutput](#lib-output)

## <a name="liboutput"></a><a name="lib-output"></a>LibOutput

```cpp
LibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [LIB_OUTPUT.](../event-table.md#lib-output)

::: moniker-end
