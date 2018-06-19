---
title: event_receiver | Документы Microsoft
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
ms.openlocfilehash: 01ab5aeee7d706da7016cb1ea1f01ff7367de888
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875569"
---
# <a name="eventreceiver"></a>event_receiver
Создает приемник событий (получатель).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 Перечисление одного из следующих значений:  
  
-   `native` для неуправляемого кода C/C++ (по умолчанию для собственных классов).  
  
-   `com` для кода COM. Это значение требует включить следующие файлы заголовка:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout_dependent**  
 Укажите *layout_dependent* только тогда, когда `type` = **com**. *layout_dependent* является логическое значение:  
  
-   **значение true,** означает, что в сигнатуру делегатов в приемник должны совпадать к которым они прикреплены событий источника событий. Имена обработчиков событий приемника должны совпадать с именами, указанный в интерфейсе источника соответствующее событие. Необходимо использовать **coclass** при *layout_dependent* — **true**. Немного более эффективно, чтобы указать **true**.  
  
-   **false** (по умолчанию) означает, что вызывающий соглашение и класс хранения (виртуальный, статический и другие) не обязательно совпадают с метод события и обработчики; ни имена обработчиков должны соответствовать имена методов интерфейса источника событий.  
  
## <a name="remarks"></a>Примечания  
 **Event_receiver** C++ атрибут указывает, класса или структуры, к которому применяется приемника событий, с помощью модели единой событий Visual C++.  
  
 **event_receiver** используется с [event_source](../windows/event-source.md) атрибута и [__hook](../cpp/hook.md) и [__unhook](../cpp/unhook.md) ключевые слова. Используйте **event_source** для создания источников событий. Используйте `__hook` в методах приемника событий для связи («обработчик») методы приемника событий к событиям источника события. Используйте `__unhook` отменить связь с ними.  
  
 *layout_dependent* задается только для приемников событий COM (`type`=**com**). Значение по умолчанию для *layout_dependent* — **false**.  
  
> [!NOTE]
>  Класс-шаблон или структура не могут содержать события.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**Компонентный класс** при *layout_dependent*=**true**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
 [event_source](../windows/event-source.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
