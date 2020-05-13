---
title: Класс CommandLine
description: Ссылка на класс SDK CommandLine по сборке.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b35d688acf06579cc27f2fee053ef58032e204e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325050"
---
# <a name="commandline-class"></a>Класс CommandLine

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `CommandLine` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для сопоставления [COMMAND_LINE](../event-table.md#command-line) события.

## <a name="syntax"></a>Синтаксис

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `CommandLine` своего базового класса [SimpleEvent,](simple-event.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Командный пункт](#command-line)

### <a name="functions"></a>Функции

[Значение](#value)

## <a name="commandline"></a><a name="command-line"></a>Командный пункт

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [COMMAND_LINE.](../event-table.md#command-line)

## <a name="value"></a><a name="value"></a> Значение

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая командную строку. Значение включает аргументы, которые были получены из файла ответа \_и\_из переменных среды, таких как CL, CL, Link и \_LINK\_.

::: moniker-end
