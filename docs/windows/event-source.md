---
title: event_source | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_source
dev_langs:
- C++
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6fc8d8100786f78d516bb5f880e4238b7e3a2388
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611868"
---
# <a name="eventsource"></a>event_source

Создает источник событий.

## <a name="syntax"></a>Синтаксис

```cpp
[ event_source(
   type,
   optimize=[speed | size],
   decorate=[true | false]
) ]
```

### <a name="parameters"></a>Параметры

*type*  
Перечисление одного из следующих значений:

- `native` для неуправляемого кода C/C++ (по умолчанию для неуправляемых классов).

- `com` для кода COM. При `coclass` = `type`=`com`. Это значение требует включить следующие файлы заголовка:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*  
Когда *тип* — `native`, можно указать `optimize=size`, чтобы указать, что доступно 4 байта хранилища (минимум) для всех событий в классе или `optimize=speed` (по умолчанию) для указания, что доступно 4 * (число событий) байт для хранения.

*украшения*  
Когда *тип* — `native`, можно указать `decorate=false`, чтобы указать, что развернутое имя в объединенном файле (MRG) не должно содержать имя включающего класса. [/Fx](../build/reference/fx-merge-injected-code.md) позволяет создавать MRG-файлы. `decorate=false`, который используется по умолчанию, приводит-полных имен типов в объединенном файле.

## <a name="remarks"></a>Примечания

Атрибут **event_source** языка C++ указывает, что класс или структура, к которым он применяется, будут источником события.

**event_source** используется в сочетании с атрибутом [event_receiver](../windows/event-receiver.md) и ключевым словом [__event](../cpp/event.md) . Используйте `event_receiver` для создания приемников событий. Используйте **__event** для методов в пределах источника событий, чтобы указать эти методы в качестве событий.

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

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](../windows/compiler-attributes.md)  
[event_receiver](../windows/event-receiver.md)  
[__event](../cpp/event.md)  
[__hook](../cpp/hook.md)  
[__unhook](../cpp/unhook.md)  
[Атрибуты классов](../windows/class-attributes.md)  