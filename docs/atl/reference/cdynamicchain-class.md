---
title: "CDynamicChain Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDynamicChain"
  - "ATL.CDynamicChain"
  - "CDynamicChain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicChain class"
  - "chaining message maps"
  - "message maps, связывание"
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDynamicChain Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы, поддерживающие динамическое связывание сопоставления сообщения.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CDynamicChain  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDynamicChain::CDynamicChain](../Topic/CDynamicChain::CDynamicChain.md)|Конструктор.|  
|[CDynamicChain::~CDynamicChain](../Topic/CDynamicChain::~CDynamicChain.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDynamicChain::CallChain](../Topic/CDynamicChain::CallChain.md)|Направляет сообщение Windows для сопоставления сообщения другого объекта.|  
|[CDynamicChain::RemoveChainEntry](../Topic/CDynamicChain::RemoveChainEntry.md)|Удаляет запись сопоставления сообщения из коллекции.|  
|[CDynamicChain::SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md)|Добавляет запись сопоставления сообщения в коллекцию или изменяет существующую запись.|  
  
## Заметки  
 `CDynamicChain` управляет коллекцией сопоставлений сообщения, после чего сообщение Windows для непосредственно, во время выполнения для сопоставления сообщения другого объекта.  
  
 Чтобы добавить поддержку для динамического создания цепочки сопоставления сообщения, выполните следующие действия:  
  
-   Создайте производный класс от `CDynamicChain`.  При сопоставлении сообщений, определить макрос [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) для привязан к сопоставлению сообщения другого объекта по умолчанию.  
  
-   Создайте каждый класс будет привязан к из [CMessageMap](../../atl/reference/cmessagemap-class.md).  `CMessageMap` позволяет объекту предоставить его сопоставления сообщения с другими объектами.  
  
-   Вызовите `CDynamicChain::SetChainEntry`, чтобы определить, какие объект и сопоставление сообщения требуется привязан к.  
  
 Например, предположим, что класс определяется следующим образом:  
  
 [!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/CPP/cdynamicchain-class_1.h)]  
  
 После этого клиент вызывает метод `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/CPP/cdynamicchain-class_2.cpp)]  
  
 где `chainedObj` прикованный объект, а экземпляр класса, производного от `CMessageMap`.  Теперь, если `myCtl` получает сообщение, которое не изменяется `OnPaint` или `OnSetFocus`, процедура окна направляет сообщение для сопоставления сообщения `chainedObj` по умолчанию.  
  
 Дополнительные сведения о сопоставлении сообщений владения см. в разделе [сопоставления сообщения](../../atl/message-maps-atl.md) в статье "классах окна библиотеки ATL."  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [CWindowImpl Class](../Topic/CWindowImpl%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)