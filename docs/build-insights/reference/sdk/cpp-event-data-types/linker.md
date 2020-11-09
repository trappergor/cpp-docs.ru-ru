---
title: Класс Linker
description: Справочник по классу Linker пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf5544d725c12db8962d888944d4a281387207fa
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923091"
---
# <a name="linker-class"></a>Класс Linker

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Linker` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [LINKER](../event-table.md#linker).

## <a name="syntax"></a>Синтаксис

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [Invocation](invocation.md) класс `Linker` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[Компоновщик](#linker)

## <a name="linker"></a><a name="linker"></a> Linker

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [LINKER](../event-table.md#linker).

::: moniker-end
