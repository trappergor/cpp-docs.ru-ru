---
title: "Схемы приемников событий | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "схемы приемников событий"
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Схемы приемников событий
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если вложенный элемент управления OLE вызывает событие, контейнер элемента управления получает событие с помощью механизма, называемый «сопоставления приемника событий,» является MFC.  Это сопоставление приемника событий обозначает функции обработчика для каждого конкретного события, а также параметры этих событий.  Дополнительные сведения о сопоставлениях приемника событий см. в статье [Контейнеры элементов управления ActiveX](../../mfc/activex-control-containers.md).  
  
### Сопоставления приемника событий  
  
|||  
|-|-|  
|[BEGIN\_EVENTSINK\_MAP](../Topic/BEGIN_EVENTSINK_MAP.md)|Запускает определение сопоставления приемника событий.|  
|[DECLARE\_EVENTSINK\_MAP](../Topic/DECLARE_EVENTSINK_MAP.md)|Объявляет сопоставление приемника событий.|  
|[END\_EVENTSINK\_MAP](../Topic/END_EVENTSINK_MAP.md)|Завершите определение сопоставления приемника событий.|  
|[ON\_EVENT](../Topic/ON_EVENT.md)|Определяет обработчик событий для определенного события.|  
|[ON\_EVENT\_RANGE](../Topic/ON_EVENT_RANGE.md)|Определяет обработчик событий для события увольнянного из определенного набора элементов управления OLE.|  
|[ON\_EVENT\_REFLECT](../Topic/ON_EVENT_REFLECT.md)|Получает события увольнянные элементом управления, прежде чем они обрабатываются контейнером элемента управления.|  
|[ON\_PROPNOTIFY](../Topic/ON_PROPNOTIFY.md)|Определяет обработчик для обработки уведомлений свойства из элемента управления OLE.|  
|[ON\_PROPNOTIFY\_RANGE](../Topic/ON_PROPNOTIFY_RANGE.md)|Определяет обработчик для обработки уведомлений свойства из набора элементов управления OLE.|  
|[ON\_PROPNOTIFY\_REFLECT](../Topic/ON_PROPNOTIFY_REFLECT.md)|Получает уведомления свойств, элементом управления, прежде чем они обрабатываются контейнером элемента управления.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)