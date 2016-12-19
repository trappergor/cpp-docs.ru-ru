---
title: "event_source | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.event_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка событий, атрибуты"
  - "журналы событий, источник события"
  - "источники событий, создание"
  - "event_source - атрибут"
  - "источники событий"
  - "обработка событий, создание источника событий"
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# event_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает источник событий.  
  
## Синтаксис  
  
```  
  
       [ event_source(  
       type,  
optimize=[speed | size],  
decorate=[true | false]) ]  
```  
  
#### Параметры  
 `type`  
 Перечисление одного из следующих значений:  
  
-   `native` для неуправляемого кода C\/C\+\+ \(по умолчанию для неуправляемых классов\).  
  
-   `com` для кода COM. При `type`\=`com` следует использовать `coclass`. Это значение требует включить следующие файлы заголовка:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 Когда `type` имеет значение **native**, можно задать **optimize\=size**, чтобы указать, что доступно 4 байта \(минимум\) для хранения всех событий в классе, или **optimize\=speed** \(по умолчанию\), чтобы указать, что доступно 4 \* \(число событий\) байт для хранения.  
  
 **decorate**  
 Если `type` имеет значение **native**, можно задать **decorate\=false**, чтобы указать, что развернутое имя в объединенном файле \(MRG\) не должно содержать имя включающего класса.[\/Fx](../build/reference/fx-merge-injected-code.md) позволяет создавать MRG\-файлы.**decorate\=false**, который используется по умолчанию, приводит к использованию полных имен типов в объединенном файле.  
  
## Заметки  
 Атрибут **event\_source** языка C\+\+ указывает, что класс или структура, к которым он применяется, будут источником события.  
  
 **event\_source** используется в сочетании с атрибутом [event\_receiver](../windows/event-receiver.md) и ключевым словом [\_\_event](../cpp/event.md). Используйте **event\_receiver** для создания приемников событий. Используйте `__event` для методов в пределах источника событий, чтобы указать эти методы в качестве событий.  
  
> [!NOTE]
>  Класс\-шаблон или структура не могут содержать события.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**coclass** при `type`\=**com**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)