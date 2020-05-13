---
title: Pass2 класс
description: Ссылка на класс SDK Pass2.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass2
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 89b775c60b1d136c33dbaf2c4e39f247be7bb0bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324405"
---
# <a name="pass2-class"></a>Pass2 класс

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Pass2` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия событию [PASS2.](../event-table.md#pass2)

## <a name="syntax"></a>Синтаксис

```cpp
class Pass2 : public LinkerPass
{
public:
    Pass2(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `Pass2` своего базового класса [LinkerPass,](linker-pass.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Pass2](#pass2)

## <a name="pass2"></a><a name="pass2"></a>Pass2

```cpp
Pass2(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [PASS2.](../event-table.md#pass2)

::: moniker-end
