---
title: MatchEventInMemberФункция
description: Ссылка на функцию «Си- Сборка Исследования SDK MatchEventInMemberFunction»
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 522630da16e3f4a1294316d88140f4bc25dca2c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323902"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInMemberФункция

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventInMemberFunction` используется для сопоставления события с типом, описанным первым параметром функции участника. Сопоставленное событие направляется функции участника для дальнейшей обработки.

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

*TInterface*\
Тип, содержащий функцию члена.

*TReturn*\
Тип возврата функции участника.

*TEvent*\
Тип события, чтобы соответствовать.

*TExtraParams*\
Типы дополнительных параметров, принятых функцией участника, а также тип события совпадают.

*TExtraArgs*\
Типы дополнительных аргументов, которые `MatchEventInMemberFunction`были переданы .

*Событие*\
Событие, сопозное типу события, описанному *TEvent.*

*objectPtr*\
Указатель на объект, на котором вызывается *memberFunc.*

*memberFunc*\
Функция участника, описывающая тип события для сопоставления.

*extraArgs*\
Аргументы, которые идеально перенаправляются *членуFunc* вместе с параметром типа события.

### <a name="return-value"></a>Возвращаемое значение

Значение **bool,** что **верно,** если соответствие было успешным, или **ложные** в противном случае.

## <a name="remarks"></a>Remarks

Тип события, использоваемый для параметра *TEvent,* может быть выбран из списка *классов захвата.* Для списка событий и классов захвата, которые можно использовать для их сопоставления, см. таблицу [событий.](../event-table.md)

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
