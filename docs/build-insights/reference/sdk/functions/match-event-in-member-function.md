---
title: матчевентинмемберфунктион
description: Справочник C++ по функциям SDK для Build Insights матчевентинмемберфунктион.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eabbb8a91609b1447ebcc19af32df2ffed347c24
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334382"
---
# <a name="matcheventinmemberfunction"></a>матчевентинмемберфунктион

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventInMemberFunction` используется для сопоставления события с типом, описанным в первом параметре функции-члена. Сопоставленное событие пересылается функции-члену для дальнейшей обработки.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     TEvent,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventInMemberFunction(
    const RawEvent&          event,
    TInterface*              objectPtr,
    TReturn (TInterface::*   memberFunc)(TEvent, TExtraParams...),
    TExtraArgs&&...          extraArgs);
```

### <a name="parameters"></a>Параметры

*Тинтерфаце*\
Тип, содержащий функцию члена.

*Третурн*\
Возвращаемый тип функции члена.

*Тевент*\
Тип сопоставляемого события.

*Текстрапарамс*\
Типы дополнительных параметров, принимаемых функцией члена, а также тип события для сопоставления.

*Текстрааргс*\
Типы дополнительных аргументов, переданных в `MatchEventInMemberFunction`.

*event*\
Событие для сопоставления с типом события, описанным *тевент*.

*обжектптр*\
Указатель на объект, для которого вызывается *мемберфунк* .

*мемберфунк*\
Функция члена, описывающая тип события для сопоставления.

*екстрааргс*\
Аргументы, которые поддаются идеальному перенаправлению в *мемберфунк* вместе с параметром типа события.

### <a name="return-value"></a>Возвращаемое значение

**Логическое** значение, равное **true** , если сопоставление выполнено успешно, или **false** в противном случае.

## <a name="remarks"></a>Remarks

Тип события, используемый для параметра *тевент* , можно выбрать из списка *классов отслеживания*. Список событий и классы отслеживания, которые можно использовать для сопоставления, см. в разделе [Таблица событий](../event-table.md).

## <a name="example"></a>Пример

```cpp
void MyClass::Foo1(Function f) {}

void MyClass::Foo2(Compiler cl) {}

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo1);

    bool b2 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo2);

    // b1: true because the first parameter of Foo1 is Function.
    // b2: false because the first parameter of Foo2 isn't Function.
}
```

::: moniker-end
