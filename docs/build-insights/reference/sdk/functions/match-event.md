---
title: МатчСобытие
description: Ссылка на функцию «Исследования сборки SDK MatchEvent».
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0c60653641c676716bcdd60865433773da79325f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323860"
---
# <a name="matchevent"></a>МатчСобытие

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEvent` используется для сопоставления события со списком типов событий. Если событие соответствует типу в списке, оно перенаправляется обработчику для дальнейшей обработки.

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

*TEvent*\
Первый тип события, который вы хотите сопоставить.

*TEvents*\
Остальные типы событий, которые вы хотите сопоставить.

*TCallable*\
Тип, поддерживающий. `operator()` Для получения дополнительной информации о том, какие *callable* аргументы передаются оператору, см.

*TExtraArgs*\
Типы дополнительных аргументов, которые `MatchEvent`были переданы .

*Событие*\
Событие, сопозное типам событий, описанным *TEvent* и *TEvents.*

*Вызываемые*\
`MatchEvent`вызывает *вызываемый* вызов после успешного сопоставления события с любым из типов событий, описанных *TEvent* и *TEvents.* Первым аргументом, передаваемым *вызываемому,* является r-значение совмещенных типов событий. Пакет параметров *extraArgs* идеально переадресован в остальных параметрах *callable.*  

*extraArgs*\
Аргументы, которые идеально перенаправляются в *callable* вместе с соответствующим типом события.

### <a name="return-value"></a>Возвращаемое значение

Значение **bool,** что **верно,** если соответствие было успешным, или **ложные** в противном случае.

## <a name="remarks"></a>Remarks

Типы событий для использования для параметров *TEvent* и *TEvents* выбираются из списка *классов захвата.* Для списка событий и классов захвата, которые можно использовать для их сопоставления, см. таблицу [событий.](../event-table.md)

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
