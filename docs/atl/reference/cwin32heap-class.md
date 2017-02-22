---
title: "CWin32Heap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWin32Heap"
  - "ATL.CWin32Heap"
  - "CWin32Heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWin32Heap class"
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CWin32Heap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций выделения кучи Win32.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CWin32Heap : public IAtlMemMgr  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md)|Конструктор.|  
|[CWin32Heap::~CWin32Heap](../Topic/CWin32Heap::~CWin32Heap.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWin32Heap::Allocate](../Topic/CWin32Heap::Allocate.md)|Выделяет блок памяти из кучи объекта.|  
|[CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md)|Вложение объект кучи в существующей куче.|  
|[CWin32Heap::Detach](../Topic/CWin32Heap::Detach.md)|Наконец удаляет объект кучи из существующей кучи.|  
|[CWin32Heap::Free](../Topic/CWin32Heap::Free.md)|Освобождает ранее выбранную память из кучи.|  
|[CWin32Heap::GetSize](../Topic/CWin32Heap::GetSize.md)|Возвращает размер выделенного блока памяти из кучи объекта.|  
|[CWin32Heap::Reallocate](../Topic/CWin32Heap::Reallocate.md)|Reallocates блок памяти из кучи объекта.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CWin32Heap::m\_bOwnHeap](../Topic/CWin32Heap::m_bOwnHeap.md)|Пометить, используемый для определения текущего владельца дескриптора кучи.|  
|[CWin32Heap::m\_hHeap](../Topic/CWin32Heap::m_hHeap.md)|Дескриптор объекта в куче.|  
  
## Заметки  
 Методы выделения памяти инструментов `CWin32Heap` с помощью Win32 наваливают для функции, включая [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597) и [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701).  В отличие от других классов кучи, `CWin32Heap` требует допустимый дескриптор кучи предоставлен, прежде чем память выделена: другие классы имеют значения по умолчанию к использованию кучи процесса.  Дескриптор может быть передано конструктору или к методу [CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md).  См. в описании метода [CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md) дополнительные сведения.  
  
## Пример  
 См. пример для [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Иерархия наследования  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## Требования  
 **Header:** atlmem.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)