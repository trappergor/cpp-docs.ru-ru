---
title: "CComPtrBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComPtrBase"
  - "ATL::CComPtrBase<T>"
  - "ATL.CComPtrBase<T>"
  - "ATL::CComPtrBase"
  - "CComPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtrBase class"
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет основу для умных классов указателя с помощью модели, основанные COM\- подпрограммы памяти.  
  
## Синтаксис  
  
```  
  
      template <  
   class T   
> class CComPtrBase  
```  
  
#### Параметры  
 `T`  
 Тип объекта, который будет ссылаться автоматически указатель.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPtrBase::~CComPtrBase](../Topic/CComPtrBase::~CComPtrBase.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|Вызывайте этот метод для создания подключения между точкой подключения `CComPtrBase` и приемником клиента.|  
|[CComPtrBase::Attach](../Topic/CComPtrBase::Attach.md)|Вызовите этот метод, чтобы принять владение существующего указателя.|  
|[CComPtrBase::CoCreateInstance](../Topic/CComPtrBase::CoCreateInstance.md)|Вызовите этот метод, чтобы создать объект класса, связанного с указанным идентификатором класса, либо запрограммировать идентификатор.|  
|[CComPtrBase::CopyTo](../Topic/CComPtrBase::CopyTo.md)|Вызовите этот метод, чтобы скопировать указатель `CComPtrBase` к другой переменной указателя.|  
|[CComPtrBase::Detach](../Topic/CComPtrBase::Detach.md)|Этот метод вызывается для освобождения владение указателя.|  
|[CComPtrBase::IsEqualObject](../Topic/CComPtrBase::IsEqualObject.md)|Вызывайте этот метод для проверки, если указанные точки **IUnknown** к одному и тому же объекту, связанному с `CComPtrBase` объект.|  
|[CComPtrBase::QueryInterface](../Topic/CComPtrBase::QueryInterface.md)|Вызовите этот метод, чтобы вернуть указатель к заданному интерфейсу.|  
|[CComPtrBase::Release](../Topic/CComPtrBase::Release.md)|Этот метод вызывается для освобождения интерфейс.|  
|[CComPtrBase::SetSite](../Topic/CComPtrBase::SetSite.md)|Вызывайте этот метод для задания сайт объекта `CComPtrBase` к **IUnknown** родительского объекта.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPtrBase::operator T\*](../Topic/CComPtrBase::operator%20T*.md)|Оператор приведения.|  
|[CComPtrBase::operator \!](../Topic/CComPtrBase::operator%20!.md)|Оператор NOT.|  
|[CComPtrBase::operator &](../Topic/CComPtrBase::operator%20&.md)|Оператор &.|  
|[CComPtrBase::operator \*](../Topic/CComPtrBase::operator%20*.md)|Оператор \*.|  
|[CComPtrBase::operator \<](../Topic/CComPtrBase::operator%20%3C.md)|Менее\- оператор "Меньше".|  
|[CComPtrBase::operator \=\=](../Topic/CComPtrBase::operator%20==.md)|Оператор равенства.|  
|[CComPtrBase::operator \-\>](../Topic/CComPtrBase::operator%20-%3E.md)|Оператор указатель\-к\- элементов.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPtrBase::p](../Topic/CComPtrBase::p.md)|Переменная элемента данных.|  
  
## Заметки  
 Этот класс предоставляет основу для других умных указателей, использующих процедур управления памятью модели COM, например [CComQIPtr](../../atl/reference/ccomqiptr-class.md) и [CComPtr](../../atl/reference/ccomptr-class.md).  Производные классы добавить собственные конструкторы и операторы, но полагаются на методах, предоставляемых `CComPtrBase`.  
  
## Требования  
 **Header:** atlcomcli.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)