---
title: event_receiver | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_receiver
dev_langs:
- C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23607eb9d59a5c860d89444205c675c95e2b907e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594073"
---
# <a name="eventreceiver"></a>event_receiver

Создает приемник событий (получатель).

## <a name="syntax"></a>Синтаксис

```cpp
[ event_receiver(
   type
   [, layout_dependent=false]
) ]
```

### <a name="parameters"></a>Параметры

*type*  
Перечисление одного из следующих значений:

- `native` для неуправляемого кода C/C++ (по умолчанию к собственным классам).

- `com` для кода COM. Это значение требует включить следующие файлы заголовка:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*  
Укажите *layout_dependent* только если `type` = **com**. *layout_dependent* является логическое значение:

- **значение true,** означает, что сигнатуры делегатов в приемник должен точно соответствуют тем, к которым они прикреплены событий источника событий. Имена обработчиков событий приемника должны совпадать с именами, указанных в интерфейсе источника соответствующего события. Необходимо использовать `coclass` при *layout_dependent* — **true**. Немного более эффективно, чтобы указать **true**.

- **false** (по умолчанию) означает, что классом вызывающего соглашение о вызовах и хранения (виртуальный, статический и другие) не могут быть разными, метод события и обработчики; и не обязательно должны совпадать имена методов интерфейса источника событий имена обработчиков.

## <a name="remarks"></a>Примечания

**Event_receiver** C++ атрибут указывает, что класс или структура, к которому применяется приемник событий, с помощью модели единой событий Visual C++.

**event_receiver** используется с [event_source](../windows/event-source.md) атрибут и [__hook](../cpp/hook.md) и [__unhook](../cpp/unhook.md) ключевые слова. Используйте `event_source` для создания источников событий. Используйте **__hook** в методах приемника событий для связи («ловушка») методы приемника событий для события источника событий. Используйте **__unhook** отменить связь с ними.

*layout_dependent* указывается только для приемников событий COM (`type`=**com**). По умолчанию для *layout_dependent* — **false**.

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|`coclass` Когда *layout_dependent*=**true**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](../windows/compiler-attributes.md)  
[event_source](../windows/event-source.md)  
[__event](../cpp/event.md)  
[__hook](../cpp/hook.md)  
[__unhook](../cpp/unhook.md)  
[Атрибуты классов](../windows/class-attributes.md)  