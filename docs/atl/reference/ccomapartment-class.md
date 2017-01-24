---
title: "CComApartment Class | Microsoft Docs"
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
  - "ATL::CComApartment"
  - "CComApartment"
  - "ATL.CComApartment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartments in ATL EXE modules"
  - "CComApartment class"
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComApartment Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс обеспечивает поддержку управления подразделение в объединенный в поток исполняемый модуль.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CComApartment  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComApartment::CComApartment](../Topic/CComApartment::CComApartment.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComApartment::Apartment](../Topic/CComApartment::Apartment.md)|Помечает адрес потока, начиная.|  
|[CComApartment::GetLockCount](../Topic/CComApartment::GetLockCount.md)|Возвращает количество блокировок текущего потока.|  
|[CComApartment::Lock](../Topic/CComApartment::Lock.md)|Увеличивает число блокировки потока.|  
|[CComApartment::Unlock](../Topic/CComApartment::Unlock.md)|Уменьшает объем блокирования потока.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComApartment::m\_dwThreadID](../Topic/CComApartment::m_dwThreadID.md)|Содержит идентификатор потока.|  
|[CComApartment::m\_hThread](../Topic/CComApartment::m_hThread.md)|Содержит дескриптор потока.|  
|[CComApartment::m\_nLockCnt](../Topic/CComApartment::m_nLockCnt.md)|Содержит количество блокировок текущего потока.|  
  
## Заметки  
 `CComApartment` используется [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) для управления подразделение в объединенный в поток исполняемый модуль.  `CComApartment` предоставляет методы для увеличения и уменьшения возлагать жизни на блокировки потока.  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)