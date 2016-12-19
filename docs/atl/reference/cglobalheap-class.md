---
title: "CGlobalHeap Class | Microsoft Docs"
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
  - "ATL.CGlobalHeap"
  - "ATL::CGlobalHeap"
  - "CGlobalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGlobalHeap class"
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGlobalHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью глобальные функции кучи Win32.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CGlobalHeap : public IAtlMemMgr  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGlobalHeap::Allocate](../Topic/CGlobalHeap::Allocate.md)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CGlobalHeap::Free](../Topic/CGlobalHeap::Free.md)|Этот метод вызывается для освобождения блоков памяти, выделенной данным диспетчером памяти.|  
|[CGlobalHeap::GetSize](../Topic/CGlobalHeap::GetSize.md)|Вызывайте этот метод для получения выделенный размер блока памяти, выделенных данным диспетчером памяти.|  
|[CGlobalHeap::Reallocate](../Topic/CGlobalHeap::Reallocate.md)|Вызовите этот метод, чтобы reallocate память, выделенная данным диспетчером памяти.|  
  
## Заметки  
 Функции выделения памяти инструментов `CGlobalHeap` кучу с помощью глобальной функции Win32.  
  
> [!NOTE]
>  Глобальные функции кучи медленнее, чем другие функции управления памятью и не содержат так много функций.  Таким образом, новые приложения должны использовать [функции кучи](http://msdn.microsoft.com/library/windows/desktop/aa366711).  Эти доступных в классе [CWin32Heap](../../atl/reference/cwin32heap-class.md).  Глобальные функции по\-прежнему используются DDE и функциями буфера обмена.  
  
## Пример  
 См. пример для [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Иерархия наследования  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## Требования  
 **Header:** atlmem.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)