---
title: "Message Map Macros (ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Message Map Macros (ATL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти макросы указывают сопоставления и записи сообщения.  
  
|||  
|-|-|  
|[ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)|Отмечает начало другого сопоставления сообщения.|  
|[BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)|Отмечает начало по умолчанию сопоставления сообщения.|  
|[CHAIN\_MSG\_MAP\_ALT](../Topic/CHAIN_MSG_MAP_ALT.md)|Цепочки в другое сопоставление сообщений в базовом классе.|  
|[CHAIN\_MSG\_MAP\_ALT\_MEMBER](../Topic/CHAIN_MSG_MAP_ALT_MEMBER.md)|Цепочки в другое сопоставление сообщения в элементе данных класса.|  
|[CHAIN\_MSG\_MAP](../Topic/CHAIN_MSG_MAP.md)|Добавляет к сопоставлению по умолчанию сообщения в базовом классе.|  
|[CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md)|Добавляет к сопоставлению сообщения в другом классе во время выполнения.|  
|[CHAIN\_MSG\_MAP\_MEMBER](../Topic/CHAIN_MSG_MAP_MEMBER.md)|Добавляет к сопоставлению сообщения по умолчанию в элементе данных класса.|  
|[COMMAND\_CODE\_HANDLER](../Topic/COMMAND_CODE_HANDLER.md)|Сопоставляет сообщение **WM\_COMMAND** функции обработчика, основанный на коде уведомления.|  
|[COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md)|Сопоставляет сообщение **WM\_COMMAND** функции обработчика, основанный на коде уведомления и идентификатор пункта меню, элемента управления или сочетаний клавиш.|  
|[COMMAND\_ID\_HANDLER](../Topic/COMMAND_ID_HANDLER.md)|Сопоставляет сообщение **WM\_COMMAND** функции обработчика, основанный на идентификаторе пункта меню, элемента управления или сочетаний клавиш.|  
|[COMMAND\_RANGE\_CODE\_HANDLER](../Topic/COMMAND_RANGE_CODE_HANDLER.md)|Сопоставляет сообщение **WM\_COMMAND** функции обработчика, основанный на коде уведомления и сопредельном диапазон идентификаторов элемента управления.|  
|[COMMAND\_RANGE\_HANDLER](../Topic/COMMAND_RANGE_HANDLER.md)|Сопоставляет сообщение **WM\_COMMAND** функции обработчика, основываясь на сопредельном диапазон идентификаторов элемента управления.|  
|[DECLARE\_EMPTY\_MSG\_MAP](../Topic/DECLARE_EMPTY_MSG_MAP.md)|Реализует сопоставление пустого сообщения.|  
|[DEFAULT\_REFLECTION\_HANDLER](../Topic/DEFAULT_REFLECTION_HANDLER.md)|По умолчанию автоматически предоставляет обработчик для устанавливанных сообщений, которые не меняются в противном случае.|  
|[END\_MSG\_MAP](../Topic/END_MSG_MAP.md)|Помечает конец сопоставления сообщения.|  
|[FORWARD\_NOTIFICATIONS](../Topic/FORWARD_NOTIFICATIONS.md)|Переадресует сообщения уведомления родительского окна.|  
|[MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md)|Сопоставляет сообщение Windows для функции обработчика.|  
|[MESSAGE\_RANGE\_HANDLER](../Topic/MESSAGE_RANGE_HANDLER.md)|Сопоставляет сопредельное диапазон сообщений Windows функции обработчика.|  
|[NOTIFY\_CODE\_HANDLER](../Topic/NOTIFY_CODE_HANDLER.md)|Сопоставляет сообщение **WM\_NOTIFY** функции обработчика, основанный на коде уведомления.|  
|[NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md)|Сопоставляет сообщение **WM\_NOTIFY** функции обработчика, основанный на коде уведомления и идентификаторе элемента управления.|  
|[NOTIFY\_ID\_HANDLER](../Topic/NOTIFY_ID_HANDLER.md)|Сопоставляет сообщение **WM\_NOTIFY** функции обработчика, основанный на идентификаторе элемента управления.|  
|[NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/NOTIFY_RANGE_CODE_HANDLER.md)|Сопоставляет сообщение **WM\_NOTIFY** функции обработчика, основанный на коде уведомления и сопредельном диапазон идентификаторов элемента управления.|  
|[NOTIFY\_RANGE\_HANDLER](../Topic/NOTIFY_RANGE_HANDLER.md)|Сопоставляет сообщение **WM\_NOTIFY** функции обработчика, основываясь на сопредельном диапазон идентификаторов элемента управления.|  
|[REFLECT\_NOTIFICATIONS](../Topic/REFLECT_NOTIFICATIONS.md)|Отражает сообщения уведомления обратно в окно, отправленных их.|  
|[REFLECTED\_COMMAND\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_CODE_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_COMMAND** функции обработчика, основанный на коде уведомления.|  
|[REFLECTED\_COMMAND\_HANDLER](../Topic/REFLECTED_COMMAND_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_COMMAND** функции обработчика, основанный на коде уведомления и идентификатор пункта меню, элемента управления или сочетаний клавиш.|  
|[REFLECTED\_COMMAND\_ID\_HANDLER](../Topic/REFLECTED_COMMAND_ID_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_COMMAND** функции обработчика, основанный на идентификаторе пункта меню, элемента управления или сочетаний клавиш.|  
|[REFLECTED\_COMMAND\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_CODE_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_COMMAND** функции обработчика, основанный на коде уведомления и сопредельном диапазон идентификаторов элемента управления.|  
|[REFLECTED\_COMMAND\_RANGE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_COMMAND** функции обработчика, основываясь на сопредельном диапазон идентификаторов элемента управления.|  
|[REFLECTED\_NOTIFY\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_CODE_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_NOTIFY** функции обработчика, основанный на коде уведомления.|  
|[REFLECTED\_NOTIFY\_HANDLER](../Topic/REFLECTED_NOTIFY_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_NOTIFY** функции обработчика, основанный на коде уведомления и идентификаторе элемента управления.|  
|[REFLECTED\_NOTIFY\_ID\_HANDLER](../Topic/REFLECTED_NOTIFY_ID_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_NOTIFY** функции обработчика, основанный на идентификаторе элемента управления.|  
|[REFLECTED\_NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_CODE_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_NOTIFY** функции обработчика, основанный на коде уведомления и сопредельном диапазон идентификаторов элемента управления.|  
|[REFLECTED\_NOTIFY\_RANGE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_HANDLER.md)|Сопоставляет отраженное сообщение **WM\_NOTIFY** функции обработчика, основываясь на сопредельном диапазон идентификаторов элемента управления.|  
  
## См. также  
 [Macros](../../atl/reference/atl-macros.md)