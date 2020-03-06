---
title: матчевентстаккинмемберфунктион
description: Справочник C++ по функциям SDK для Build Insights матчевентстаккинмемберфунктион.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2a966ea5209a25a62c08cb0873d0565299a15d27
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334370"
---
# <a name="matcheventstackinmemberfunction"></a>матчевентстаккинмемберфунктион

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventStackInMemberFunction` используется для сопоставления стека событий с определенной иерархией событий, описанной в списке параметров функции-члена. Сопоставленные иерархии пересылаются функции члена для дальнейшей обработки. Дополнительные сведения о событиях, стеках событий и иерархиях см. в разделе [Таблица событий](../event-table.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, TExtraParams...),
    TExtraArgs&&...           extraArgs);

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, TExtraParams...),
    TExtraArgs&&...           extraArgs);

// Etc...

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename     T3,
    typename     T4,
    typename     T5,
    typename     T6,
    typename     T7,
    typename     T8,
    typename     T9,
    typename     T10,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TExtraParams...),
    TExtraArgs&&...           extraArgs);
```

### <a name="parameters"></a>Параметры

*Тинтерфаце*\
Тип, содержащий функцию члена.

*Третурн*\
Возвращаемый тип функции члена.

*T1*,..., *T10*\
Типы, описывающие иерархию событий для сопоставления.

*Текстрапарамс*\
Типы дополнительных параметров, принимаемых функцией члена, и типы иерархии событий.

*Текстрааргс*\
Типы дополнительных аргументов, переданных в `MatchEventStackInMemberFunction`.

*евентстакк*\
Стек событий для сопоставления с иерархией типов событий, описываемых *T1* через *T10*.

*обжектптр*\
Указатель на объект, для которого вызывается *мемберфунк* .

*мемберфунк*\
Функция члена, которая описывает иерархию типов событий для сопоставления.

*екстрааргс*\
Аргументы, которые поддаются идеальному перенаправлению в *мемберфунк* вместе с параметрами иерархии типов событий.

### <a name="return-value"></a>Возвращаемое значение

**Логическое** значение, равное **true** , если сопоставление выполнено успешно, или **false** в противном случае.

## <a name="remarks"></a>Remarks

Последнее событие в *евентстакк* всегда сопоставляется с последней записью в иерархии типов событий для сопоставления. Все остальные типы в иерархии типов событий могут соответствовать любому положению в *евентстакк* , за исключением последнего, если они находятся в том же порядке.

Типы событий, используемые для параметров *T1* через *T10* , выбираются из списка *классов отслеживания*. Список событий и классы отслеживания, которые можно использовать для сопоставления, см. в разделе [Таблица событий](../event-table.md).

## <a name="example"></a>Пример

```cpp
void MyClass::Foo1(Compiler cl, BackEndPass bep, C2DLL c2,
    CodeGeneration cg, Thread t, Function f) { }

void MyClass::Foo2(Compiler cl, Function f) { }

void MyClass::Foo3(Thread t, Compiler cl, Function f) { }

void MyClass::Foo4(Compiler cl) { }

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo1);

    bool b2 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo2);

    bool b3 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo3);

    bool b4 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo4);

    // b1: true because the parameter types of Foo1 match the eventStack
    //     exactly.
    // b2: true because Function is the last entry in both the member
    //     function parameter list and 'eventStack', and also because
    //     Compiler comes before Function in 'eventStack' and in the
    //     parameter type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', the member function parameter
    //     list doesn't list them in the right order.
    // b4: false because the last entry in the member function parameter
    //     list is Compiler, which doesn't match the last entry in 'eventStack'
    //     (Function).
}
```

::: moniker-end
