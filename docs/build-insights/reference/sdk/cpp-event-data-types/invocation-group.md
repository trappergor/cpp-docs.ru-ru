---
title: Класс Группы вызова
description: Ссылка на класс SDK InvocationGroup.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ff5a73d5304a21c314c0fc5ce442e0ffc23b28fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324693"
---
# <a name="invocationgroup-class"></a>Класс Группы вызова

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `InvocationGroup` используется с функциями [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для сопоставления групп, содержащих сочетание событий [COMPILER](../event-table.md#compiler) и [LINKER.](../event-table.md#linker)

## <a name="syntax"></a>Синтаксис

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены из `InvocationGroup` своего [класса EventGroup\<Вызов\> ](event-group.md) базы, класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Призывгруппа](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a>Призывгруппа

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>Параметры

*Группы*\
Группа, содержащая смесь мероприятий [COMPILER](../event-table.md#compiler) и [LINKER.](../event-table.md#linker)

::: moniker-end
