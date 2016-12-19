---
title: "_AtlCreateWndData Structure | Microsoft Docs"
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
  - "ATL::_AtlCreateWndData"
  - "ATL._AtlCreateWndData"
  - "_AtlCreateWndData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AtlCreateWndData structure"
  - "AtlCreateWndData structure"
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _AtlCreateWndData Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эта структура содержит данные экземпляра класса в коде над окнами в библиотеки ATL.  
  
## Синтаксис  
  
```  
  
      struct _AtlCreateWndData{  
   void* m_pThis;  
   DWORD m_dwThreadID;  
   _AtlCreateWndData* m_pNext;  
};  
```  
  
## Члены  
 **m\_pThis**  
 Указатель **this**, используемый для доступа к экземпляру класса в процедурах по окна.  
  
 `m_dwThreadID`  
 Идентификатор потока текущего экземпляра класса.  
  
 **m\_pNext**  
 Указатель на следующий объект `_AtlCreateWndData`.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [Структуры](../../atl/reference/atl-structures.md)