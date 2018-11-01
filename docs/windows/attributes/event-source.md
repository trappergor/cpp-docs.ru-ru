---
title: event_source (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
ms.openlocfilehash: e7a58abc617fcfed69020bdace60758a6bf75337
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510569"
---
# <a name="eventsource"></a>event_source

Создает источник событий.

## <a name="syntax"></a>Синтаксис

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Параметры

*type*<br/>
Перечисление одного из следующих значений:

- `native` для неуправляемого кода C/C++ (по умолчанию для неуправляемых классов).

- `com` для кода COM. При `coclass` = `type`=`com`. Это значение требует включить следующие файлы заголовка:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
Когда *тип* — `native`, можно указать `optimize=size`, чтобы указать, что доступно 4 байта хранилища (минимум) для всех событий в классе или `optimize=speed` (по умолчанию) для указания, что доступно 4 * (число событий) байт для хранения.

*decorate*<br/>
Когда *тип* — `native`, можно указать `decorate=false`, чтобы указать, что развернутое имя в объединенном файле (MRG) не должно содержать имя включающего класса. [/Fx](../../build/reference/fx-merge-injected-code.md) позволяет создавать MRG-файлы. `decorate=false`, который используется по умолчанию, приводит-полных имен типов в объединенном файле.

## <a name="remarks"></a>Примечания

Атрибут **event_source** языка C++ указывает, что класс или структура, к которым он применяется, будут источником события.

**event_source** используется в сочетании с атрибутом [event_receiver](event-receiver.md) и ключевым словом [__event](../../cpp/event.md) . Используйте `event_receiver` для создания приемников событий. Используйте **__event** для методов в пределах источника событий, чтобы указать эти методы в качестве событий.

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**Компонентный класс** при `type`=`com`|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Атрибуты классов](class-attributes.md)