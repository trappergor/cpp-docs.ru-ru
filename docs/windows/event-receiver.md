---
title: "event_receiver | Microsoft Docs"
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
  - "vc-attr.event_receiver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event_receiver attribute"
  - "event receivers"
  - "events [C++], event receivers (sinks)"
  - "event handling [C++], attributes"
  - "event handling [C++], creating receiver"
  - "event sinks, creating"
  - "event sinks"
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# event_receiver
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает приемник событий \(получатель\).  
  
## Синтаксис  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### Параметры  
 `type`  
 Перечисление одно из следующих значений:  
  
-   `native` для неуправляемого кода C\/C\+\+ \(по умолчанию для собственных классов\).  
  
-   `com` для кода модели COM.  Это значение необходимо включить следующие файлы заголовков:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 layout\_dependent  
 Определение layout\_dependent только если `type`\=**com**.  *layout\_dependent* логическое значение:  
  
-   **true** означает, что подпись приемников делегатов в случае должно точно соответствовать разделах, к которым они закрепленный в случае источник.  Имена обработчиков приемника событий должны соответствовать именам, определенным в соответствующем интерфейсе источника события.  Необходимо использовать **CoClass** после layout\_dependent существует  **true**.  Он немного более эффективно определять **true**.  
  
-   **false** \(по умолчанию\) означает, что вызывающий класс соглашения и хранения \(фактически, статическими и различаются\) не должен соответствовать методу события и обработчики; не выполняет обработчик имена должны соответствовать именам методов интерфейса источника события.  
  
## Заметки  
 Event\_receiver Атрибут C\+\+ определяет, что класс или структура, к которому он применяется будет приемником событий, используя модель события универсальную Visual C\+\+.  
  
 **event\_receiver** используется с  [event\_source](../windows/event-source.md) атрибут и  [\_\_hook](../cpp/hook.md) и  [\_\_unhook](../cpp/unhook.md) ключевые слова.  Используйте event\_source создание источников событий.  Используйте `__hook` внутри методов приемника событий для сопоставления \("обработчик"\) методы приемника событий события источника события.  Используйте `__unhook` разъединить их.  
  
 layout\_dependent определяет только для приемников событий модели COM \(`type`\=**com**\).  Значение по умолчанию layout\_dependent существует **false**.  
  
> [!NOTE]
>  Класс\-шаблон или структура не могут содержать события.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|**CoClass** после layout\_dependent\=**true**|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_source](../windows/event-source.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)