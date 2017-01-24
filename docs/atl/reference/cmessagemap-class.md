---
title: "CMessageMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMessageMap"
  - "ATL.CMessageMap"
  - "ATL::CMessageMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, обработчики сообщений"
  - "CMessageMap class"
  - "message maps, ATL - библиотека"
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMessageMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс позволяет сопоставления сообщения объекта, чтобы иметь доступ другим объектом.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class ATL_NO_VTABLE CMessageMap  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMessageMap::ProcessWindowMessage](../Topic/CMessageMap::ProcessWindowMessage.md)|Обращается к сопоставлению в `CMessageMap`\- производный класс сообщений.|  
  
## Заметки  
 `CMessageMap` абстрактный базовый класс, который позволяет сопоставления сообщения объекта для доступа к другой объект.  Для этого объекта, чтобы сделать его сопоставления сообщения, этот класс должен наследоваться от `CMessageMap`.  
  
 Использование `CMessageMap` поддержки, содержащихся в окне, и динамическое связывание библиотеки ATL сопоставить сообщение.  Например, любой классифицируют содержать объект [CContainedWindow](../Topic/CContainedWindowT%20Class.md), должны наследоваться от `CMessageMap`.  Следующий фрагмент кода взят из образца [SUBEDIT](../../top/visual-cpp-samples.md).  С помощью [CComControl](../../atl/reference/ccomcontrol-class.md), класс `CAtlEdit` автоматически наследуется от `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/CPP/cmessagemap-class_1.h)]  
  
 Поскольку содержащийся окно, `m_EditCtrl`, будет использоваться сопоставление сообщений во внешнем классе `CAtlEdit` является производным от `CMessageMap`.  
  
 Дополнительные сведения о сопоставлениях сообщений см. в разделе [сопоставления сообщения](../../atl/message-maps-atl.md) в статье "классах окна библиотеки ATL."  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [CDynamicChain Class](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)