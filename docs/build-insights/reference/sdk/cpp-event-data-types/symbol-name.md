---
title: Класс SymbolName
description: Ссылка на s' Build Insights SDK SymbolName.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1306fb43d6c2140a75b36c5f142532916cf26ae4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324356"
---
# <a name="symbolname-class"></a>Класс SymbolName

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `SymbolName` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [SYMBOL_NAME](../event-table.md#symbol-name) событию.

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

## <a name="members"></a>Участники

Наряду с унаследованных членов из `SymbolName` своего базового класса [SimpleEvent,](simple-event.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[СимволИ](#symbol-name)

### <a name="functions"></a>Функции

[Имя ключа](#key)
[Name](#name)

## <a name="key"></a><a name="key"></a>Ключ

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>Возвращаемое значение

Численный идентификатор для типа, представленного этим символом. Этот идентификатор уникален в компиляторе переднего прохода.

## <a name="name"></a><a name="name"></a>Имя

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название типа, представленного символом, закодировано в UTF-8.

## <a name="symbolname"></a><a name="symbol-name"></a>СимволИ

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие SYMBOL_NAME.](../event-table.md#symbol-name)

::: moniker-end
