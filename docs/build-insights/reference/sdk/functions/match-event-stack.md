---
title: MatchEventStack
description: Ссылка на функцию «Си- Сборка» SDK MatchEventStack.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a223d420e8c48667fbd1c6569f02d0486f597b5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323875"
---
# <a name="matcheventstack"></a>MatchEventStack

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventStack` используется для сопоставления стека событий с определенной иерархией событий. Соответствующие иерархии препровождаются обработчику для дальнейшей обработки. Чтобы узнать больше о событиях, стеках событий и иерархиях, см. таблицу [событий.](../event-table.md)

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename          TEvent,
    typename...       TEvents,
    typename          TCallable,
    typename...       TExtraArgs>
bool MatchEventStack(
    const EventStack& eventStack,
    TCallable&&       callable,
    TExtraArgs&&...   extraArgs);
```

### <a name="parameters"></a>Параметры

*TEvent*\
Тип старшего родителя для сопоставления в стеке события.

*TEvents*\
Остальные типы, которые вы хотите сопоставить в стеке событий.

*TCallable*\
Тип, поддерживающий. `operator()` Для получения дополнительной информации о том, какие *callable* аргументы передаются оператору, см.

*TExtraArgs*\
Типы дополнительных аргументов `MatchEventStack`перешли к .

*EventStack*\
Стек события, сопозжаемый с иерархией типов событий, описанной *TEvent* и *TEvents.*

*Вызываемые*\
После успешного сопоставления стека событий с иерархией типов `MatchEventStack` событий, описанной *TEvent* и *TEvents,* вызывает *вызываемые вызовы.* Он переходит к *вызываемому* одному аргументу r-value для каждого типа в иерархии событий. Пакет параметров *extraArgs* идеально переадресован в остальных параметрах *callable.*

*extraArgs*\
Аргументы, которые идеально перенаправляются в *callable* вместе с соответствующим типом события.

### <a name="return-value"></a>Возвращаемое значение

Значение **bool,** что **верно,** если соответствие было успешным, или **ложные** в противном случае.

## <a name="remarks"></a>Remarks

Последнее событие в *eventStack* всегда сопоставляется с последней \[записью в concatenated *TEvent*, *TEvents...* \] список введите. Все остальные записи *TEvent* и *TEvents* могут соответствовать любой позиции в *eventStack,* за исключением последнего, при условии, что они находятся в том же порядке.

Типы событий для использования для параметров *TEvent* и *TEvents* выбираются из списка *классов захвата.* Для списка событий и классов захвата, которые можно использовать для их сопоставления, см. таблицу [событий.](../event-table.md)

## <a name="example"></a>Пример

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStack<Compiler, BackEndPass, C2DLL,
                CodeGeneration, Thread, Function>(
        eventStack, [](Compiler cl, BackEndPass bep, C2DLL c2,
            CodeGeneration cg, Thread t, Function f){ /* Do something ... */ });

    bool b2 = MatchEventStack<Compiler, Function>(
        eventStack, [](Compiler cl, Function f){ /* Do something... */ });

    bool b3 = MatchEventStack<Thread, Compiler, Function>(
        eventStack, [](Thread t, Compiler cl Function f){ /* Do something... */ });

    bool b4 = MatchEventStack<Compiler>(
        eventStack, [](Compiler cl){ /* Do something... */ });


    // b1: true because the list of types matches the eventStack exactly.
    // b2: true because Function is the last entry in both the type list
    //     and 'eventStack', and also because Compiler comes before
    //     Function in 'eventStack' and in the type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', they aren't listed in the
    //     right order in the type list.
    // b4: false because the last entry in the type list is Compiler,
    //     which doesn't match the last entry in 'eventStack' (Function).
}
```

::: moniker-end
