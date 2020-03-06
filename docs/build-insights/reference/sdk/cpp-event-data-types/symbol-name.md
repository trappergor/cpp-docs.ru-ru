---
title: Класс Симболнаме
description: Справочник C++ по классу SDK для Build Insights симболнаме.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b5e9a9b22db99c099b9f7dc1813fb335358a83e8
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334550"
---
# <a name="symbolname-class"></a>Класс Симболнаме

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `SymbolName` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [SYMBOL_NAMEного](../event-table.md#symbol-name) события.

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

Вместе с наследуемыми членами из своего базового класса [симпливент](simple-event.md) класс `SymbolName` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[симболнаме](#symbol-name)

### <a name="functions"></a>Функции

[Имя](#name)
[ключа](#key)

## <a name="key"></a>Раздел

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>Возвращаемое значение

Числовой идентификатор для типа, представленного этим символом. Этот идентификатор уникален в рамках внешнего прохода компилятора.

## <a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя типа, представленного символом в кодировке UTF-8.

## <a name="symbol-name"></a>симболнаме

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [SYMBOL_NAME](../event-table.md#symbol-name) .

::: moniker-end
