---
title: "event_source | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.event_source
dev_langs: C++
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05371b5c2d9acd091adcbdf81d2994f205e36ef7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="eventsource"></a>event_source
Создает источник событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ event_source(  
   type,  
   optimize=[speed | size],  
   decorate=[true | false]  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 Перечисление одного из следующих значений:  
  
-   `native` для неуправляемого кода C/C++ (по умолчанию для неуправляемых классов).  
  
-   `com` для кода COM. При `coclass` = `type`=`com`. Это значение требует включить следующие файлы заголовка:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 Когда `type` имеет значение **native**, можно задать **optimize=size**, чтобы указать, что доступно 4 байта (минимум) для хранения всех событий в классе, или **optimize=speed** (по умолчанию), чтобы указать, что доступно 4 * (число событий) байт для хранения.  
  
 **decorate**  
 Если `type` имеет значение **native**, можно задать **decorate=false**, чтобы указать, что развернутое имя в объединенном файле (MRG) не должно содержать имя включающего класса. [/Fx](../build/reference/fx-merge-injected-code.md) позволяет создавать MRG-файлы. **decorate=false**, который используется по умолчанию, приводит к использованию полных имен типов в объединенном файле.  
  
## <a name="remarks"></a>Примечания  
 Атрибут **event_source** языка C++ указывает, что класс или структура, к которым он применяется, будут источником события.  
  
 **event_source** используется в сочетании с атрибутом [event_receiver](../windows/event-receiver.md) и ключевым словом [__event](../cpp/event.md) . Используйте **event_receiver** для создания приемников событий. Используйте `__event` для методов в пределах источника событий, чтобы указать эти методы в качестве событий.  
  
> [!NOTE]
>  Класс-шаблон или структура не могут содержать события.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**type** = `type`=**com**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
