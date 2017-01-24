---
title: "CHeapPtr Class | Microsoft Docs"
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
  - "ATL::CHeapPtr"
  - "CHeapPtr"
  - "ATL.CHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtr class"
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Интеллектуальное класс указателя для управления указатели кучи.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
typename T,  
class Allocator= CCRTAllocator  
> class CHeapPtr :  
public CHeapPtrBase< T, Allocator>  
```  
  
#### Параметры  
 `T`  
 Тип объекта, который будет храниться в куче.  
  
 `Allocator`  
 Класс выделения памяти для использования.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtr::CHeapPtr](../Topic/CHeapPtr::CHeapPtr.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtr::Allocate](../Topic/CHeapPtr::Allocate.md)|Этот метод вызывается для выделения памяти в куче к объектам хранилища.|  
|[CHeapPtr::Reallocate](../Topic/CHeapPtr::Reallocate.md)|Вызовите этот метод, чтобы reallocate память в куче.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtr::operator \=](../Topic/CHeapPtr::operator%20=.md)|Оператор присваивания.|  
  
## Заметки  
 `CHeapPtr` является производным от [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) и по умолчанию использует подпрограммы CRT \(в [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)\) для выделения и освобождения памяти.  Класс [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) может использоваться для построения списка указателей кучи.  См. также [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), который использует процедур выделения памяти модели COM.  
  
## Иерархия наследования  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## Требования  
 **Header:** atlcore.h  
  
## См. также  
 [CHeapPtrBase Class](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)