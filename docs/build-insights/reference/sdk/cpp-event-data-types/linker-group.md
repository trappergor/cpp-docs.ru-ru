---
title: Класс LinkerGroup
description: Ссылка на исследования в отношении SDK LinkerGroup.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c59d62938e5bd7b839ad12a321a03510e708e0fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324651"
---
# <a name="linkergroup-class"></a>Класс LinkerGroup

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `LinkerGroup` используется с функциями [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для сопоставления групп событий [LINKER.](../event-table.md#linker)

## <a name="syntax"></a>Синтаксис

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из своего `LinkerGroup` класса базы [EventGroup\<Linker,\> ](event-group.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ЛинкерГрупп](#linker-group)

## <a name="linkergroup"></a><a name="linker-group"></a>ЛинкерГрупп

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>Параметры

*Группы*\
Группа мероприятий [LINKER.](../event-table.md#linker)

::: moniker-end
