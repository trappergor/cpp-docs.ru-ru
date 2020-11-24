---
title: event_receiver (атрибут COM C++)
description: Узнайте, как использовать атрибут com расширения Microsoft C++ `event_receiver` .
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.openlocfilehash: 8ed6ef6113d72a9565b275dff4e035dc56f11e82
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483286"
---
# <a name="event_receiver-attribute"></a>Атрибут `event_receiver`

Создает приемник событий (получатель).

> [!NOTE]
> Атрибуты событий в машинном коде C++ несовместимы со стандартным C++. Они не компилируются при указании [`/permissive-`](../../build/reference/permissive-standards-conformance.md) режима соответствия.

## <a name="syntax"></a>Синтаксис

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Параметры

*`type`*\
Перечисление одного из следующих значений:

- `native` для неуправляемого кода C/C++ (по умолчанию для собственных классов).

- `com` для кода COM. Это значение требует включения следующих файлов заголовков:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`layout_dependent`*\
Указывайте *`layout_dependent`* , только если `type` = **com**. *`layout_dependent`* является логическим значением:

- **`true`** означает, что сигнатуры делегатов в приемнике событий должны точно совпадать с теми, к которым они привязаны в источнике событий. Имена обработчиков приемников событий должны совпадать с именами, указанными в соответствующем исходном интерфейсе события. Используется `coclass` *`layout_dependent`* , если имеет **`true`** . Это немного более эффективно для указания **`true`** .

- **`false`** (по умолчанию) означает, что соглашение о вызовах и класс хранения ( `virtual` , `static` и др.) не должны соответствовать методу события и обработчикам. Имена обработчиков также не должны совпадать с именами методов интерфейса источника событий.

## <a name="remarks"></a>Комментарии

**`event_receiver`** Атрибут C++ указывает, что класс или структура, к которой он применяется, будет приемником событий с помощью унифицированной модели событий Microsoft C++.

**`event_receiver`** используется с [`event_source`](event-source.md) атрибутом и [`__hook`](../../cpp/hook.md) [`__unhook`](../../cpp/unhook.md) ключевыми словами и. Используйте `event_source` для создания источников событий. Используйте **`__hook`** в методах приемника событий, чтобы связать методы приемника событий с событиями источника событий. Используйте **`__unhook`** для их отсвязи.

*`layout_dependent`* указывается только для приемников событий COM ( `type` = **`com`** ). Значение по умолчанию для *`layout_dependent`* — **`false`** .

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|--|--|
| **Относится к** | **`class`**, **`struct`** |
| **REPEATABLE** | Нет |
| **Требуемые атрибуты** | `coclass` When *`layout_dependent`*=**`true`** |
| **Недопустимые атрибуты** | None |

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)\
[`event_source`](event-source.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[Атрибуты класса](class-attributes.md)
