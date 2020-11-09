---
title: Класс SymbolName
description: Справочник по классу SymbolName пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a749d95b3812df8b1cc0cd7d2da037e98467cefc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920480"
---
# <a name="symbolname-class"></a>Класс SymbolName

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `SymbolName` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [SYMBOL_NAME](../event-table.md#symbol-name).

## <a name="syntax"></a>Синтаксис

```cpp
class SymbolName : public SimpleEvent
{
public:
    SymbolName(const RawEvent& event);

    const unsigned long long&  Key() const;
    const char*                Name() const;
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [SimpleEvent](simple-event.md) класс `SymbolName` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[SymbolName](#symbol-name)

### <a name="functions"></a>Функции

[Key](#key)
[Name](#name)

## <a name="key"></a><a name="key"></a> Key

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>Возвращаемое значение

Числовой идентификатор для типа, представленного этим символом. Этот идентификатор уникален в пределах этапа внешнего интерфейса компилятора.

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа, представленного символом в кодировке UTF-8.

## <a name="symbolname"></a><a name="symbol-name"></a> SymbolName

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [SYMBOL_NAME](../event-table.md#symbol-name).

::: moniker-end
