---
title: "Memory Management Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "память, управление"
ms.assetid: be564a5e-577e-40a7-bfe3-25ad21e57270
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Memory Management Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти классы обеспечивают поддержку указателей кучи, умных указателей и других подпрограмм выделения памяти.  
  
-   [CAutoPtr](../atl/reference/cautoptr-class.md) этот класс представляет интеллектуальное объект указателя.  
  
-   [CAutoPtrArray](../atl/reference/cautoptrarray-class.md) этот класс содержит методы умных полезные при создании массива указателей.  
  
-   [CAutoPtrList](../atl/reference/cautoptrlist-class.md) этот класс предоставляет методы полезных для построения списка умных указателей.  
  
-   [CAutoVectorPtr](../atl/reference/cautovectorptr-class.md) этот класс представляет автоматически, используя новый объект указателя и операторы удаления.  
  
-   [CComAllocator](../atl/reference/ccomallocator-class.md) этот класс содержит методы для управления ими память с помощью процедуры памяти модели COM.  
  
-   [CComGITPtr](../Topic/CComGITPtr%20Class.md) этот класс содержит методы для ведения дела с указателями интерфейса и глобальный таблицей интерфейса \(GIT\).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функций выделения памяти модели COM.  
  
-   Класс указателя [CComHeapPtr](../atl/reference/ccomheapptr-class.md) a smart для управления указатели кучи.  
  
-   Класс указателя [CComPtr](../atl/reference/ccomptr-class.md) a smart для управления указатели интерфейса модели COM.  
  
-   [CComPtrBase](../atl/reference/ccomptrbase-class.md) этот класс предоставляет основу для умных классов указателя с помощью модели, основанные COM\- подпрограммы памяти.  
  
-   Класс указателя [CComQIPtr](../atl/reference/ccomqiptr-class.md) a smart для управления указатели интерфейса модели COM.  
  
-   [CCRTAllocator](../atl/reference/ccrtallocator-class.md) этот класс содержит методы для управления ими память с помощью процедуры памяти CRT.  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функции кучи CRT.  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью глобальные функции кучи Win32.  
  
-   [CHandle](../atl/reference/chandle-class.md) этот класс содержит методы для создания и использования объекта маркера.  
  
-   Класс указателя [CHeapPtr](../atl/reference/cheapptr-class.md) a smart для управления указатели кучи.  
  
-   [CHeapPtrBase](../atl/reference/cheapptrbase-class.md) этот класс формы основу для нескольких умных классов указателя кучи.  
  
-   [CHeapPtrList](../atl/reference/cheapptrlist-class.md) этот класс предоставляет методы полезных для построения списка указателей кучи.  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md), используя локальные функции кучи Win32.  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функций выделения кучи Win32.  
  
-   [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) этот класс представляет интерфейс диспетчера памяти.  
  
## См. также  
 [Class Overview](../atl/atl-class-overview.md)