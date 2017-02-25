---
title: "CHandle Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CHandle"
  - "ATL::CHandle"
  - "CHandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHandle class"
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CHandle Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для создания и использования объекта маркера.  
  
## Синтаксис  
  
```  
  
class CHandle  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHandle::CHandle](../Topic/CHandle::CHandle.md)|Конструктор.|  
|[CHandle::~CHandle](../Topic/CHandle::~CHandle.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHandle::Attach](../Topic/CHandle::Attach.md)|Вызовите этот метод, чтобы вложить объект `CHandle` в существующий маркер.|  
|[CHandle::Close](../Topic/CHandle::Close.md)|Вызовите этот метод, чтобы закрыть объект `CHandle`.|  
|[CHandle::Detach](../Topic/CHandle::Detach.md)|Вызовите этот метод, чтобы в итоге удалить из объекта `CHandle` маркер.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHandle::operator HANDLE](../Topic/CHandle::operator%20HANDLE.md)|Возвращает значение, хранящееся маркера.|  
|[CHandle::operator \=](../Topic/CHandle::operator%20=.md)|Оператор присваивания.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CHandle::m\_h](../Topic/CHandle::m_h.md)|Переменная\-член, хранящая дескриптор.|  
  
## Заметки  
 Объект `CHandle` может быть использована, если маркер не требуется. основное отличие состоит в том, что объект `CHandle` будет автоматически удалять.  
  
> [!NOTE]
>  Некоторые функции API, будут использовать значения NULL как пустой или недопустимый дескриптор, а другие используют INVALID\_HANDLE\_VALUE.  Использование `CHandle` и отображают только АННУЛИРУЮТ INVALID\_HANDLE\_VALUE как реальный дескриптор.  Если вызвать API, которое может вернуть INVALID\_HANDLE\_VALUE необходимо проверить перед вызовом этого значения [CHandle::Attach](../Topic/CHandle::Attach.md) или передать его в конструктор `CHandle`, а вместо этого передать значение NULL.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)