---
title: "IAtlMemMgr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAtlMemMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlMemMgr class"
  - "память, управление"
  - "память, memory manager"
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IAtlMemMgr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет интерфейс диспетчера памяти.  
  
## Синтаксис  
  
```  
  
__interface __declspec( uuid( "654F7EF5-CFDF-4df9-A450-6C6A13C622C0" )) IAtlMemMgr  
  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[Выберите](../Topic/IAtlMemMgr::Allocate.md)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[Свободная](../Topic/IAtlMemMgr::Free.md)|Этот метод вызывается для освобождения блоков памяти.|  
|[GetSize](../Topic/IAtlMemMgr::GetSize.md)|Вызывайте этот метод для извлечения размер выделенного блока памяти.|  
|[Reallocate](../Topic/IAtlMemMgr::Reallocate.md)|Вызовите этот метод, чтобы reallocate блока памяти.|  
  
## Заметки  
 Этот интерфейс реализуется [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md) или [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  Локальные и глобальные функции кучи медленнее, чем другие функции управления памятью, и не содержат так много функций.  Таким образом, новые приложения должны использовать [функции кучи](http://msdn.microsoft.com/library/windows/desktop/aa366711).  Эти доступных в классе [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
## Пример  
 [!CODE [NVC_ATL_Utilities#94](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#94)]  
  
## Требования  
 **Header:** atlmem.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)