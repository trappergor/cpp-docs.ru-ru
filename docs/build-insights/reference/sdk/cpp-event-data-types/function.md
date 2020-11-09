---
title: Класс Function
description: Справочник по классу Function пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Function
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 874477b9ca31095bfcf4ba3c7a6fd220dc073415
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920649"
---
# <a name="function-class"></a>Класс Function

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Function` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [FUNCTION](../event-table.md#function).

## <a name="syntax"></a>Синтаксис

```cpp
class Function : public Activity
{
public:
    Function(const RawEvent& event);

    const char* Name() const;
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `Function` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[Function](#function)

### <a name="functions"></a>Функции

[имя](#name);

## <a name="function"></a><a name="function"></a> Function

```cpp
Function(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [FUNCTION](../event-table.md#function).

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя функции в кодировке UTF-8.

::: moniker-end
