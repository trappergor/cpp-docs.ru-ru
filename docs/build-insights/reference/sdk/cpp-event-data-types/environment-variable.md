---
title: Класс EnvironmentVariable
description: Справочник по классу EnvironmentVariable пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f707ab744aaf6097975ba9e189815df3c9f32266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920767"
---
# <a name="environmentvariable-class"></a>Класс EnvironmentVariable

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `EnvironmentVariable` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable).

## <a name="syntax"></a>Синтаксис

```cpp
class EnvironmentVariable : public SimpleEvent
{
public:
    EnvironmentVariable(const RawEvent& event);

    const wchar_t* Name() const;
    const wchar_t* Value() const;
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [SimpleEvent](simple-event.md) класс `EnvironmentVariable` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>Функции

[имя](#name)
[значение](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a> EnvironmentVariable

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable).

## <a name="name"></a><a name="name"></a> Name

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя переменной среды.

## <a name="value"></a>Значение <a name="value"></a>

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение переменной среды.

::: moniker-end
