---
title: "CAutoVectorPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoVectorPtr"
  - "ATL.CAutoVectorPtr"
  - "ATL.CAutoVectorPtr<T>"
  - "CAutoVectorPtr"
  - "ATL::CAutoVectorPtr<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtr class"
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAutoVectorPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет автоматически, используя новый объект указателя и операторы удаления.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
typename T  
> class CAutoVectorPtr  
```  
  
#### Параметры  
 `T`  
 Тип указателя.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoVectorPtr::CAutoVectorPtr](../Topic/CAutoVectorPtr::CAutoVectorPtr.md)|Конструктор.|  
|[CAutoVectorPtr::~CAutoVectorPtr](../Topic/CAutoVectorPtr::~CAutoVectorPtr.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoVectorPtr::Allocate](../Topic/CAutoVectorPtr::Allocate.md)|Вызовите этот метод, чтобы выделить память, необходимая массивом объектов, указанных в `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](../Topic/CAutoVectorPtr::Attach.md)|Вызовите этот метод, чтобы принять владение существующего указателя.|  
|[CAutoVectorPtr::Detach](../Topic/CAutoVectorPtr::Detach.md)|Этот метод вызывается для освобождения владение указателя.|  
|[CAutoVectorPtr::Free](../Topic/CAutoVectorPtr::Free.md)|Вызывайте этот метод для удаления объекта указанный на `CAutoVectorPtr`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoVectorPtr::operator T \*](../Topic/CAutoVectorPtr::operator%20T%20*.md)|Оператор приведения.|  
|[CAutoVectorPtr::operator \=](../Topic/CAutoVectorPtr::operator%20=.md)|Оператор присваивания.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoVectorPtr::m\_p](../Topic/CAutoVectorPtr::m_p.md)|Переменная элемента данных.|  
  
## Заметки  
 Этот класс содержит методы для создания и управления автоматически указатель, который помогает защититься от утечки памяти автоматически освобождение ресурсов при его упадет из области.  `CAutoVectorPtr` аналогично `CAutoPtr`, единственное различие заключается в том, что быть одним использования [вектор новый &#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) и [удаление вектора &#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md)`CAutoVectorPtr` выбрать и освобождать память, а не C\+\+ **новый** и операторов **удалить**.  См. раздел [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md), если классы коллекций `CAutoVectorPtr` требуются.  
  
 См. раздел [CAutoPtr](../../atl/reference/cautoptr-class.md) пример использования умного класса указателя.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [CAutoPtr Class](../../atl/reference/cautoptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)