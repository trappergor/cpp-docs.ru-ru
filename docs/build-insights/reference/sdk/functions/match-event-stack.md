---
title: матчевентстакк
description: Справочник C++ по функциям SDK для Build Insights матчевентстакк.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 445c2d00c24da10754d32256de0c691e82b557e1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334364"
---
# <a name="matcheventstack"></a>матчевентстакк

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventStack` используется для сопоставления стека событий с определенной иерархией событий. Сопоставленные иерархии перенаправляются обработчику для дальнейшей обработки. Дополнительные сведения о событиях, стеках событий и иерархиях см. в разделе [Таблица событий](../event-table.md).

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

*Тевент*\
Тип родителя толя для сопоставления в стеке событий.

*Тевентс*\
Остальные типы, которые вы хотите сопоставить в стеке событий.

*Ткаллабле*\
Тип, который поддерживает `operator()`. Дополнительные сведения о том, какие аргументы передаются этому оператору, см. в описании *вызываемого* параметра.

*Текстрааргс*\
Типы дополнительных аргументов, передаваемых в `MatchEventStack`.

*евентстакк*\
Стек событий для сопоставления с иерархией типов событий, описываемых *тевент* и *тевентс*.

*вызываемый*\
После успешного сопоставления стека событий с иерархией типов событий, описанной в *тевент* и *тевентс*, `MatchEventStack` вызывает *вызываемый*метод. Он передается *вызываемому* одному аргументу r-Value для каждого типа в иерархии событий. Пакет параметров *екстрааргс* идеально пересылается в остальных параметрах *вызываемого*.

*екстрааргс*\
Аргументы, которые поддаются идеальному перенаправлению для *вызываемого* вместе с соответствующим типом события.

### <a name="return-value"></a>Возвращаемое значение

**Логическое** значение, равное **true** , если сопоставление выполнено успешно, или **false** в противном случае.

## <a name="remarks"></a>Remarks

Последнее событие в *евентстакк* всегда сопоставляется с последней записью в списке типа сцепленных \[*тевент*, *тевентс...* \]. Все остальные записи *тевент* и *тевентс* могут соответствовать любой позиции в *евентстакк* , кроме последней, если они находятся в том же порядке.

Типы событий, используемые для параметров *тевент* и *тевентс* , выбираются из списка *классов отслеживания*. Список событий и классы отслеживания, которые можно использовать для сопоставления, см. в разделе [Таблица событий](../event-table.md).

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
