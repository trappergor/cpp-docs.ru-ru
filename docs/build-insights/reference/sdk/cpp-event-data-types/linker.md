---
title: Класс Линкера
description: Ссылка на класс SDK Linker.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e5d4c0c3841377fc2e029c23d5cbbd076c8029cc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324599"
---
# <a name="linker-class"></a>Класс Линкера

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Linker` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его, чтобы соответствовать событию [LINKER.](../event-table.md#linker)

## <a name="syntax"></a>Синтаксис

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `Linker` своего базового класса [Призыв,](invocation.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Компоновщик](#linker)

## <a name="linker"></a><a name="linker"></a>Компоновщик

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [LINKER.](../event-table.md#linker)

::: moniker-end
