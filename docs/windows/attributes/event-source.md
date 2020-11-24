---
title: event_source (атрибут COM C++)
description: Узнайте, как использовать атрибут com расширения Microsoft C++ `event_source` .
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.openlocfilehash: 3cdfaaa86f8fc36bf0dc90d7961077546362a662
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483273"
---
# <a name="event_source-attribute"></a>Атрибут `event_source`

Создает источник событий.

> [!NOTE]
> Атрибуты событий в машинном коде C++ несовместимы со стандартным C++. Они не компилируются при указании [`/permissive-`](../../build/reference/permissive-standards-conformance.md) режима соответствия.

## <a name="syntax"></a>Синтаксис

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Параметры

*`type`*\
Перечисление одного из следующих значений:

- `native` для неуправляемого кода C/C++ (по умолчанию для неуправляемых классов).

- `com` для кода COM. Используется `coclass` *`type`* = `com` , когда. Это значение требует включить следующие файлы заголовка:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`optimize`*\
Если *тип* — `native` , можно указать `optimize=size` , что для всех событий в классе или (по умолчанию) существует 4 байта хранилища (минимальное значение), `optimize=speed` чтобы указать, что существует 4 * (количество событий) памяти.

*`decorate`*\
Если *тип* имеет значение `native` , можно указать `decorate=false` , что развернутое имя в объединенном файле ( *`.mrg`* ) не должно включать имя включающего класса. [`/Fx`](../../build/reference/fx-merge-injected-code.md) позволяет создавать *`.mrg`* файлы. `decorate=false`, который является значением по умолчанию, приводит к полному именам типов в объединенном файле.

## <a name="remarks"></a>Комментарии

**`event_source`** Атрибут C++ указывает, что класс или структура, к которой он применяется, будет источником события.

**`event_source`** используется в сочетании с [`event_receiver`](event-receiver.md) атрибутом и [`__event`](../../cpp/event.md) ключевым словом. Используйте `event_receiver` для создания приемников событий. Используйте **`__event`** в методах в источнике события, чтобы указать эти методы в качестве событий.

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|--|--|
| **Относится к** | **`class`**, **`struct`** |
| **REPEATABLE** | Нет |
| **Требуемые атрибуты** | **`coclass`** When `type`=`com` |
| **Недопустимые атрибуты** | None |

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)\
[`event_receiver`](event-receiver.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[Атрибуты класса](class-attributes.md)
