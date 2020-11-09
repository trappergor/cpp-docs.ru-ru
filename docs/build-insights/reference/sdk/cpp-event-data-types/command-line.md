---
title: Класс CommandLine
description: Справочник по классу CommandLine пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5214f2970329510088184dc3092db66607f4d67e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923342"
---
# <a name="commandline-class"></a>Класс CommandLine

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `CommandLine` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [COMMAND_LINE](../event-table.md#command-line).

## <a name="syntax"></a>Синтаксис

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [SimpleEvent](simple-event.md) класс `CommandLine` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[CommandLine](#command-line)

### <a name="functions"></a>Функции

[Значение](#value)

## <a name="commandline"></a><a name="command-line"></a> CommandLine

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [COMMAND_LINE](../event-table.md#command-line).

## <a name="value"></a>Значение <a name="value"></a>

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая командную строку. Значение включает аргументы, полученные из файла ответов и из переменных среды, таких как CL, \_CL\_, Link и \_LINK\_.

::: moniker-end
