---
title: Класс C2DLL
description: Ссылка на исследования sDK C2DLL в СЗ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- C2DLL
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7711acf800999d4e97c3ae56fa2100a632a245b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325080"
---
# <a name="c2dll-class"></a>Класс C2DLL

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `C2DLL` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [C2_DLL](../event-table.md#c2-dll) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class C2DLL : public Activity
{
public:
    C2DLL(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены `C2DLL` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[C2DLL](#c2-dll)

## <a name="c2dll"></a><a name="c2-dll"></a>C2DLL

```cpp
C2DLL(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие C2_DLL.](../event-table.md#c2-dll)

::: moniker-end
