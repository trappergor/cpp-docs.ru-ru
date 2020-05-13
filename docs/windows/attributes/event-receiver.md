---
title: event_receiver (C++ атрибут com)
ms.date: 10/02/2018
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
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
ms.openlocfilehash: 9653a0b5c756857d92914496b9c5c6f8aee56ebb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167086"
---
# <a name="event_receiver"></a>event_receiver

Создает приемник событий (получатель).

## <a name="syntax"></a>Синтаксис

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Параметры

*type*<br/>
Перечисление одного из следующих значений:

- `native` для неуправляемого C/C++ кода (по умолчанию для собственных классов).

- `com` для кода COM. Это значение требует включить следующие файлы заголовка:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Укажите *layout_dependent* , только если `type`=**com**. *layout_dependent* является логическим значением:

- **значение true** означает, что сигнатуры делегатов в приемнике событий должны точно совпадать с теми, к которым они привязаны в источнике событий. Имена обработчиков приемников событий должны совпадать с именами, указанными в соответствующем исходном интерфейсе события. Если *layout_dependent* имеет **значение true**, необходимо использовать `coclass`. Это несколько более эффективно для указания значения **true**.

- **false** (по умолчанию) означает, что соглашение о вызовах и класс хранения (виртуальный, статический и другие) не должны совпадать с методом события и обработчиками. Кроме того, имена обработчиков не должны совпадать с именами методов интерфейса источника событий.

## <a name="remarks"></a>Remarks

Атрибут **event_receiver** C++ указывает, что класс или структура, к которой он применяется, будет приемником событий с помощью модели визуального C++ унифицированного события.

**event_receiver** используется с атрибутом [event_source](event-source.md) , а также с ключевыми словами [__hook](../../cpp/hook.md) и [__unhook](../../cpp/unhook.md) . Для создания источников событий используйте `event_source`. Используйте **__hook** в методах приемника событий, чтобы связать методы приемника событий ("перехватчик") с событиями источника событий. Используйте **__unhook** , чтобы отменить связь между ними.

*layout_dependent* указывается только для приемников событий com (`type`=**com**). Значение по умолчанию для *layout_dependent* — **false**.

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|`coclass`, когда *layout_dependent*=**true**|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Атрибуты классов](class-attributes.md)
