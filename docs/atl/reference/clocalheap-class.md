---
title: "CLocalHeap Class | Microsoft Docs"
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
  - "ATL.CLocalHeap"
  - "ATL::CLocalHeap"
  - "CLocalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLocalHeap class"
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLocalHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md), используя локальные функции кучи Win32.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CLocalHeap : public IAtlMemMgr  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLocalHeap::Allocate](../Topic/CLocalHeap::Allocate.md)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CLocalHeap::Free](../Topic/CLocalHeap::Free.md)|Этот метод вызывается для освобождения блоков памяти, выделенной данным диспетчером памяти.|  
|[CLocalHeap::GetSize](../Topic/CLocalHeap::GetSize.md)|Вызывайте этот метод для получения выделенный размер блока памяти, выделенных данным диспетчером памяти.|  
|[CLocalHeap::Reallocate](../Topic/CLocalHeap::Reallocate.md)|Вызовите этот метод, чтобы reallocate память, выделенная данным диспетчером памяти.|  
  
## Заметки  
 `CLocalHeap` реализует функции выделения памяти с помощью локальные функции кучи Win32.  
  
> [!NOTE]
>  Локальные функции кучи медленнее, чем другие функции управления памятью и не содержат так много функций.  Таким образом, новые приложения должны использовать [функции кучи](http://msdn.microsoft.com/library/windows/desktop/aa366711).  Эти доступных в классе [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
## Пример  
 См. пример для [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Иерархия наследования  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## Требования  
 **Header:** atlmem.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)