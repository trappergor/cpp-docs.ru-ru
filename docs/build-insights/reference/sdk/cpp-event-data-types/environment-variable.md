---
title: Класс EnvironmentVariable
description: Справочник C++ по классу SDK для Build Insights EnvironmentVariable.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 19e9278e76fb2116dac30a0e790fba86c6c56484
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334928"
---
# <a name="environmentvariable-class"></a>Класс EnvironmentVariable

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `EnvironmentVariable` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) .

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

Вместе с наследуемыми членами из своего базового класса [симпливент](simple-event.md) класс `EnvironmentVariable` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>Функции

[имя](#name)
[значение](#value)

## <a name="environment-variable"></a>EnvironmentVariable

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) .

## <a name="name"></a> Name

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя переменной среды.

## <a name="value"></a>Значений

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение переменной среды.

::: moniker-end
