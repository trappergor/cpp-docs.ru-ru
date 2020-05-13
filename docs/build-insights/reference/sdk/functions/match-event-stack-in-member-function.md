---
title: MatchEventstackinMemberФункция
description: Ссылка на функцию «Си-Ксстрой Анализы SDK MatchEventStackInMemberFunction»
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28842a02e7edc2e00266d8c7941798f4ce714ded
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323889"
---
# <a name="matcheventstackinmemberfunction"></a>MatchEventstackinMemberФункция

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventStackInMemberFunction` используется для сопоставления стека событий с определенной иерархией событий, описанной в списке параметров функции участника. Соответствующие иерархии препровождаются функции члена для дальнейшей обработки. Чтобы узнать больше о событиях, стеках событий и иерархиях, см. таблицу [событий.](../event-table.md)

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

*TInterface*\
Тип, содержащий функцию члена.

*TReturn*\
Тип возврата функции участника.

*T1*, ..., *T10*\
Типы, описывающие иерархию событий для сопоставления.

*TExtraParams*\
Типы дополнительных параметров, принятых функцией участника, и типы иерархии событий.

*TExtraArgs*\
Типы дополнительных аргументов, которые `MatchEventStackInMemberFunction`были переданы .

*EventStack*\
Стек события, сопозжаемый с иерархией типов *событий,* описанной T1 через *T10.*

*objectPtr*\
Указатель на объект, на котором называется *memberFunc.*

*memberFunc*\
Функция участника, описывающая иерархию типа событий для сопоставления.

*extraArgs*\
Аргументы, которые идеально перенаправляются *в memberFunc* вместе с параметрами иерархии типов событий.

### <a name="return-value"></a>Возвращаемое значение

Значение **bool,** что **верно,** если соответствие было успешным, или **ложные** в противном случае.

## <a name="remarks"></a>Remarks

Последнее событие в *eventStack* всегда сопоставляется с последней записью в иерархии типов событий, чтобы соответствовать. Все остальные типы в иерархии типов событий могут соответствовать любой позиции в *eventStack,* кроме последнего, при условии, что они находятся в том же порядке.

Типы событий для использования для параметров *T1* через *T10* выбираются из списка *классов захвата.* Для списка событий и классов захвата, которые можно использовать для их сопоставления, см. таблицу [событий.](../event-table.md)

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
