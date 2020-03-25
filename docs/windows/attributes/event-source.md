---
title: event_source (C++ атрибут com)
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
ms.openlocfilehash: e187e57f21e9c94068c0b3396b93deed617fef2a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167073"
---
# <a name="event_source"></a>event_source

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
Если *тип* — `native`, можно указать `optimize=size`, чтобы указать, что существует 4 байта хранилища (минимум) для всех событий в классе или `optimize=speed` (по умолчанию), чтобы указать, что существует 4 * (число событий) в хранилище.

*decorate*<br/>
Если *тип* — `native`, можно указать `decorate=false`, чтобы указать, что развернутое имя в объединенном файле (. MRG) не должно содержать имя включающего класса. [/Fx](../../build/reference/fx-merge-injected-code.md) позволяет создавать MRG-файлы. `decorate=false`, который является значением по умолчанию, приводит к полному именам типов в объединенном файле.

## <a name="remarks"></a>Remarks

Атрибут **event_source** языка C++ указывает, что класс или структура, к которым он применяется, будут источником события.

**event_source** используется в сочетании с атрибутом [event_receiver](event-receiver.md) и ключевым словом [__event](../../cpp/event.md) . Для создания приемников событий используйте `event_receiver`. Используйте **__event** для методов в источнике события, чтобы указать эти методы в качестве событий.

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|**компонент coclass** , когда `type`=`com`|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Атрибуты классов](class-attributes.md)
