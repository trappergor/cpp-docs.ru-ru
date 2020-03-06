---
title: Класс Фронтендфилеграуп
description: Справочник C++ по классу SDK для Build Insights фронтендфилеграуп.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 343a5a0d798d6c719088bd49668e70b10fba6d1a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334832"
---
# <a name="frontendfilegroup-class"></a>Класс Фронтендфилеграуп

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `FrontEndFileGroup` используется с функциями [матчевентстакк](../functions/match-event-stack.md) и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления групп [FRONT_END_FILE](../event-table.md#front-end-file) событий.

## <a name="syntax"></a>Синтаксис

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из его базового класса [EventGroup\<фронтендфиле\>](event-group.md) класс `FrontEndFileGroup` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[фронтендфилеграуп](#front-end-file-group)

## <a name="front-end-file-group"></a>фронтендфилеграуп

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>Параметры

\ *группы*
Группа событий [FRONT_END_FILE](../event-table.md#front-end-file) .

::: moniker-end
