---
title: матчевент
description: Справочник C++ по функциям SDK для Build Insights матчевент.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f8022953e2f56f7c8917f161b094c50e0c5ecbdf
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334358"
---
# <a name="matchevent"></a>матчевент

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEvent` используется для сопоставления события со списком типов событий. Если событие соответствует типу в списке, оно пересылается обработчику для дальнейшей обработки.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename        TEvent,
    typename...     TEvents,
    typename        TCallable,
    typename...     TExtraArgs>
bool MatchEvent(
    const RawEvent& event,
    TCallable&&     callable,
    TExtraArgs&&... extraArgs);
```

### <a name="parameters"></a>Параметры

*Тевент*\
Первый тип события, который вы хотите сопоставить.

*Тевентс*\
Остальные типы событий, которые вы хотите сопоставить.

*Ткаллабле*\
Тип, который поддерживает `operator()`. Дополнительные сведения о том, какие аргументы передаются этому оператору, см. в описании *вызываемого* параметра.

*Текстрааргс*\
Типы дополнительных аргументов, переданных в `MatchEvent`.

*event*\
Событие для сопоставления с типами событий, описанными в *тевент* и *тевентс*.

*вызываемый*\
`MatchEvent` вызывает *вызываемый* после успешного сопоставления события с любыми типами событий, описанными в *тевент* и *тевентс*. Первый аргумент, передаваемый *вызываемому* методу, является значением r-значения для соответствующего типа события. Пакет параметров *екстрааргс* идеально пересылается в остальных параметрах *вызываемого*.  

*екстрааргс*\
Аргументы, которые поддаются идеальному перенаправлению для *вызываемого* вместе с соответствующим типом события.

### <a name="return-value"></a>Возвращаемое значение

**Логическое** значение, **равное true** , если сопоставление выполнено успешно, или **false** в противном случае.

## <a name="remarks"></a>Remarks

Типы событий, используемые для параметров *тевент* и *тевентс* , выбираются из списка *классов отслеживания*. Список событий и классы отслеживания, которые можно использовать для сопоставления, см. в разделе [Таблица событий](../event-table.md).

## <a name="example"></a>Пример

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEvent<Function, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});

    bool b2 = MatchEvent<CodeGeneration, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});


    // b1: true because the list of types contains Function, which is
    //     the type of the event we are trying to match.
    // b2: false because the list of types doesn't contain Function.
}
```

::: moniker-end
