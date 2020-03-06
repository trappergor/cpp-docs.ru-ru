---
title: Класс CommandLine
description: Справочник C++ по классу командной строки SDK для сборки Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ff16646920fe77f7f3b4cb8a194a38984c3e6c32
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334988"
---
# <a name="commandline-class"></a>Класс CommandLine

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `CommandLine` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [COMMAND_LINEного](../event-table.md#command-line) события.

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

Вместе с наследуемыми членами из своего базового класса [симпливент](simple-event.md) класс `CommandLine` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Команд](#command-line)

### <a name="functions"></a>Функции

[Value](#value)

## <a name="command-line"></a>Команд

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [COMMAND_LINE](../event-table.md#command-line) .

## <a name="value"></a>Значений

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая командную строку. Значение включает аргументы, полученные из файла ответов, и из переменных среды, таких как CL, \_CL\_, Link и \_LINK\_.

::: moniker-end
