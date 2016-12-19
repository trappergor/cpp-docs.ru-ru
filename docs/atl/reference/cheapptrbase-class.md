---
title: "CHeapPtrBase Class | Microsoft Docs"
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
  - "ATL.CHeapPtrBase"
  - "ATL::CHeapPtrBase"
  - "CHeapPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrBase class"
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс формы основу для нескольких умных классов указателя кучи.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
class T,  
class Allocator= CCRTAllocator   
> class CHeapPtrBase  
```  
  
#### Параметры  
 `T`  
 Тип объекта, который будет храниться в куче.  
  
 `Allocator`  
 Класс выделения памяти для использования.  Подпрограммы CRT по умолчанию используются для выделения и освобождения памяти.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtrBase::~CHeapPtrBase](../Topic/CHeapPtrBase::~CHeapPtrBase.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtrBase::AllocateBytes](../Topic/CHeapPtrBase::AllocateBytes.md)|Вызовите этот метод, чтобы выделить память.|  
|[CHeapPtrBase::Attach](../Topic/CHeapPtrBase::Attach.md)|Вызовите этот метод, чтобы принять владение существующего указателя.|  
|[CHeapPtrBase::Detach](../Topic/CHeapPtrBase::Detach.md)|Этот метод вызывается для освобождения владение указателя.|  
|[CHeapPtrBase::Free](../Topic/CHeapPtrBase::Free.md)|Вызывайте этот метод для удаления объекта указанный на `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](../Topic/CHeapPtrBase::ReallocateBytes.md)|Вызовите этот метод, чтобы reallocate память.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtrBase::operator T\*](../Topic/CHeapPtrBase::operator%20T*.md)|Оператор приведения.|  
|[CHeapPtrBase::operator &](../Topic/CHeapPtrBase::operator%20&.md)|Оператор &.|  
|[CHeapPtrBase::operator \-\>](../Topic/CHeapPtrBase::operator%20-%3E.md)|Оператор указатель\-к\- элемента.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtrBase::m\_pData](../Topic/CHeapPtrBase::m_pData.md)|Переменная элемента данных.|  
  
## Заметки  
 Этот класс формы основу для нескольких умных классов указателя кучи.  Производные классы, например, [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), добавить собственные конструкторы и операторов.  См. раздел эти классы примеры реализации.  
  
## Требования  
 **Header:** atlcore.h  
  
## См. также  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)