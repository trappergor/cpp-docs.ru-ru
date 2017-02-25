---
title: "CComHeap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComHeap"
  - "ATL.CComHeap"
  - "ATL::CComHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeap class"
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CComHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций выделения памяти модели COM.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CComHeap : public IAtlMemMgr  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComHeap::Allocate](../Topic/CComHeap::Allocate.md)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CComHeap::Free](../Topic/CComHeap::Free.md)|Этот метод вызывается для освобождения блоков памяти, выделенной данным диспетчером памяти.|  
|[CComHeap::GetSize](../Topic/CComHeap::GetSize.md)|Вызывайте этот метод для получения выделенный размер блока памяти, выделенных данным диспетчером памяти.|  
|[CComHeap::Reallocate](../Topic/CComHeap::Reallocate.md)|Вызовите этот метод, чтобы reallocate память, выделенная данным диспетчером памяти.|  
  
## Заметки  
 `CComHeap` реализует функции выделения памяти с использованием модели COM для функции, включая [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226) и [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  Максимальный объем памяти, выделяемой равно **INT\_MAX** \(2147483647\) байт.  
  
## Пример  
 См. пример для [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Иерархия наследования  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## Требования  
 **Header:** ATLComMem.h  
  
## См. также  
 [Образец DynamicConsumer](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)