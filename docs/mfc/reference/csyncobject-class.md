---
title: "CSyncObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSyncObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSyncObject class"
  - "классы синхронизации, CSyncObject"
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSyncObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чисто виртуальный класс, который предоставляет функциональные возможности, общие для синхронизации возражает в Win32.  
  
## Синтаксис  
  
```  
class CSyncObject : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSyncObject::CSyncObject](../Topic/CSyncObject::CSyncObject.md)|Создает объект `CSyncObject`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSyncObject::Lock](../Topic/CSyncObject::Lock.md)|Увеличений доступ к объекту синхронизации.|  
|[CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md)|Увеличений доступ к объекту синхронизации.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSyncObject::operator HANDLE](../Topic/CSyncObject::operator%20HANDLE.md)|Предоставляет доступ к объекту синхронизации.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CSyncObject::m\_hObject](../Topic/CSyncObject::m_hObject.md)|Дескриптор к основному объекту синхронизации.|  
  
## Заметки  
 Библиотеки Microsoft Foundation Class предоставляет несколько классов, производных от `CSyncObject`.  Эти [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../Topic/CCriticalSection%20Class.md) и [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Сведения о том, как использовать объекты синхронизации см. в статье [Многопоточность. Использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CSyncObject`  
  
## Требования  
 **Header:**  afxmt.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)