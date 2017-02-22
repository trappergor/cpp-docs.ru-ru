---
title: "CCRTHeap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CCRTHeap"
  - "ATL.CCRTHeap"
  - "CCRTHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTHeap class"
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCRTHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функции кучи CRT.  
  
## Синтаксис  
  
```  
  
class CCRTHeap : public IAtlMemMgr  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCRTHeap::Allocate](../Topic/CCRTHeap::Allocate.md)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CCRTHeap::Free](../Topic/CCRTHeap::Free.md)|Этот метод вызывается для освобождения блоков памяти, выделенной данным диспетчером памяти.|  
|[CCRTHeap::GetSize](../Topic/CCRTHeap::GetSize.md)|Вызывайте этот метод для получения выделенный размер блока памяти, выделенных данным диспетчером памяти.|  
|[CCRTHeap::Reallocate](../Topic/CCRTHeap::Reallocate.md)|Вызовите этот метод, чтобы reallocate память, выделенная данным диспетчером памяти.|  
  
## Заметки  
 Функции выделения памяти CRT наваливают инструментов `CCRTHeap` с помощью функции, включая [malloc](../../c-runtime-library/reference/malloc.md), [free](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md) и [\_msize](../Topic/_msize.md).  
  
## Пример  
 См. пример для [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Иерархия наследования  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## Требования  
 **Header:** atlmem.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)