---
title: Окружающая средаПеременный класс
description: Ссылка на класс SDK Build Insights SDK EnvironmentVariable.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 963c52e0ea9e048448c6f2b3ac62d9938817467e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325020"
---
# <a name="environmentvariable-class"></a>Окружающая средаПеременный класс

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `EnvironmentVariable` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) событию.

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

## <a name="members"></a>Участники

Наряду с унаследованных членов из `EnvironmentVariable` своего базового класса [SimpleEvent,](simple-event.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>Функции

[Name](#name)
[Значение](#value) имени

## <a name="environmentvariable"></a><a name="environment-variable"></a>Окружающая средаПеременная

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие ENVIRONMENT_VARIABLE.](../event-table.md#environment-variable)

## <a name="name"></a><a name="name"></a>Имя

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя переменной среды.

## <a name="value"></a><a name="value"></a> Значение

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение переменной среды.

::: moniker-end
