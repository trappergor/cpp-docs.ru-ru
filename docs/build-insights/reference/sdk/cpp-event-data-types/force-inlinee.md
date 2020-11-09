---
title: Класс ForceInlinee
description: Справочник по классу ForceInlinee пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 53fff7b6cfd37ba3e3211dd072c1ce3386d00fda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920675"
---
# <a name="forceinlinee-class"></a>Класс ForceInlinee

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `ForceInlinee` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления событий [FORCE_INLINEE](../event-table.md#force-inlinee).

## <a name="syntax"></a>Синтаксис

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [SimpleEvent](simple-event.md) класс `ForceInlinee` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>Функции

[Name](#name)
[Size](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a> ForceInlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [FORCE_INLINEE](../event-table.md#force-inlinee).

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя принудительно встраиваемой функции в кодировке UTF-8.

## <a name="size"></a><a name="size"></a> Размер

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер принудительно встраиваемой функции в виде числа инструкций промежуточного языка.

::: moniker-end
