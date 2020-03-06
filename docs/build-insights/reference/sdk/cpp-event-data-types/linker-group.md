---
title: Класс Линкерграуп
description: Справочник C++ по классу SDK для Build Insights линкерграуп.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 95b0dcc3a771ec07ee60185a79a5ddbc29434b5d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334730"
---
# <a name="linkergroup-class"></a>Класс Линкерграуп

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `LinkerGroup` используется с функциями [матчевентстакк](../functions/match-event-stack.md) и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления групп событий [компоновщика](../event-table.md#linker) .

## <a name="syntax"></a>Синтаксис

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего [EventGroup\<компоновщика\>](event-group.md) базовом классе класс `LinkerGroup` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[линкерграуп](#linker-group)

## <a name="linker-group"></a>линкерграуп

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>Параметры

\ *группы*
Группа событий [компоновщика](../event-table.md#linker) .

::: moniker-end
