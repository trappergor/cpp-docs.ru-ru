---
title: "CSingleLock Class | Microsoft Docs"
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
  - "CSingleLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleLock class"
  - "synchronization objects, управление доступом"
  - "работа с потоками [MFC], управление доступом"
  - "работа с потоками [MFC], синхронизация"
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSingleLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс представляет механизм контроля доступа к определенному ресурсу в многопоточных программах.  
  
## Синтаксис  
  
```  
  
class CSingleLock  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSingleLock::CSingleLock](../Topic/CSingleLock::CSingleLock.md)|Создает объект `CSingleLock`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSingleLock::IsLocked](../Topic/CSingleLock::IsLocked.md)|Определяет, является ли объект блокирована.|  
|[CSingleLock::Lock](../Topic/CSingleLock::Lock.md)|Ожидания для объекта синхронизации.|  
|[CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)|Освобождает объект синхронизации.|  
  
## Заметки  
 `CSingleLock` не имеет базовый класс.  
  
 Для использования классов [CSemaphore](../../mfc/reference/csemaphore-class.md) синхронизации, [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../Topic/CCriticalSection%20Class.md) и [CEvent](../../mfc/reference/cevent-class.md), необходимо создать или `CSingleLock` или объект [CMultiLock](../../mfc/reference/cmultilock-class.md) ожидания в on и освобождение объекта синхронизации.  Используйте `CSingleLock` обрабатывается при необходимости дожидаться в одном объекте.  Используйте **CMultiLock**  если несколько объектов, которые можно использовать в указанное время.  
  
 Чтобы использовать объект `CSingleLock`, вызовите его в классе конструктора в функцию\-член управляемого ресурса.  Затем вызовите функцию\-член [IsLocked](../Topic/CSingleLock::IsLocked.md) для определения если ресурс доступен.  Если это так, то перейдите с остатком функции\-члена.  Если ресурс недоступен или подождите указанное время для ресурса должен освобождаться и возвращает ошибку.  После завершения использования ресурса любой вызов функции [Unlock](../Topic/CSingleLock::Unlock.md), если объект `CSingleLock` использоваться повторно или позволяет объекту `CSingleLock`, который необходимо удалить.  
  
 Объекты `CSingleLock` требуют наличия объекта, производного от [CSyncObject](../../mfc/reference/csyncobject-class.md).  Как правило, это элемент данных класса управляемого ресурса.  Дополнительные сведения о том, как использовать объекты `CSingleLock` см. в статье [Многопоточность. Использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Иерархия наследования  
 `CSingleLock`  
  
## Требования  
 **Header:**  afxmt.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CMultiLock Class](../../mfc/reference/cmultilock-class.md)