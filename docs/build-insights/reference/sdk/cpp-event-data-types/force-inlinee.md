---
title: Класс ForceInlinee
description: Ссылка на класс SDK ForceInlinee.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c6a1af0384197a0a3b6062ad9ef30537c348190d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324783"
---
# <a name="forceinlinee-class"></a>Класс ForceInlinee

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `ForceInlinee` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для сопоставления [FORCE_INLINEE](../event-table.md#force-inlinee) события.

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

## <a name="members"></a>Участники

Наряду с унаследованных членов из `ForceInlinee` своего базового класса [SimpleEvent,](simple-event.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>Функции

[Name](#name)
[Размер](#size) имени

## <a name="forceinlinee"></a><a name="force-inlinee"></a>ForceInlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [FORCE_INLINEE.](../event-table.md#force-inlinee)

## <a name="name"></a><a name="name"></a>Имя

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название функции, закрепленной за силой, закодировано в UTF-8.

## <a name="size"></a><a name="size"></a> Размер

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер функции, подстеженной силой, как промежуточный подсчет инструкций.

::: moniker-end
