---
title: "CAutoPtr Class | Microsoft Docs"
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
  - "CAutoPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtr class"
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет интеллектуальное объект указателя.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<   
typename T  
>  
class CAutoPtr  
```  
  
#### Параметры  
 `T`  
 Тип указателя.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoPtr::CAutoPtr](../Topic/CAutoPtr::CAutoPtr.md)|Конструктор.|  
|[CAutoPtr::~CAutoPtr](../Topic/CAutoPtr::~CAutoPtr.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoPtr::Attach](../Topic/CAutoPtr::Attach.md)|Вызовите этот метод, чтобы принять владение существующего указателя.|  
|[CAutoPtr::Detach](../Topic/CAutoPtr::Detach.md)|Этот метод вызывается для освобождения владение указателя.|  
|[CAutoPtr::Free](../Topic/CAutoPtr::Free.md)|Вызывайте этот метод для удаления объекта указанный на `CAutoPtr`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoPtr::operator T\*](../Topic/CAutoPtr::operator%20T*.md)|Оператор приведения.|  
|[CAutoPtr::operator \=](../Topic/CAutoPtr::operator%20=.md)|Оператор присваивания.|  
|[CAutoPtr::operator \-\>](../Topic/CAutoPtr::operator%20-%3E.md)|Оператор указатель\-к\- элемента.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoPtr::m\_p](../Topic/CAutoPtr::m_p.md)|Переменная элемента данных.|  
  
## Заметки  
 Этот класс содержит методы для создания и управления автоматически указатель, который помогает защититься от утечки памяти автоматически освобождение ресурсов при его упадет из области.  
  
 Кроме того, конструктор копий `CAutoPtr` и оператор присваивания указателя, передающих владельца источника при копировании указатель на указатель на указатель источника и назначения параметр в значение NULL.  Поэтому невозможно иметь 2 объекта каждое `CAutoPtr` хранения один указатель, и это уменьшает возможность удаления одной и той же указатель дважды.  
  
 `CAutoPtr` также упрощает создание коллекций указателей.  Вместо создания производного класса коллекции и переопределить деструктор, он проще сделать коллекцию объектов `CAutoPtr`.  Если коллекция будет удаляется объекты `CAutoPtr` пойдут из области и автоматически удаляются.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) и варианты работают точно так же, как `CAutoPtr`, за исключением того, что они выбирают и освобождает память с помощью различных функций кучи, а не C\+\+ **новый** и операторов **удалить**.  [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) аналогично `CAutoPtr`, единственному различию быть что он использует **vector new\[\]** и **vector delete\[\]** для выделения и освобождения памяти.  
  
 См. также [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) и [CAutoPtrList](../../atl/reference/cautoptrlist-class.md), когда необходимы массивы или списки умных указателей.  
  
## Требования  
 **Header:** atlbase.h  
  
## Пример  
 [!CODE [NVC_ATL_Utilities#74](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#74)]  
  
## См. также  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr Class](../../atl/reference/cautovectorptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)