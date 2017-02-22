---
title: "CMultiLock Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiLock class"
  - "synchronization objects, управление доступом"
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMultiLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс представляет механизм контроля доступа к ресурсам в многопоточных программах.  
  
## Синтаксис  
  
```  
class CMultiLock  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMultiLock::CMultiLock](../Topic/CMultiLock::CMultiLock.md)|Создает объект `CMultiLock`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMultiLock::IsLocked](../Topic/CMultiLock::IsLocked.md)|Определяет, если определенный объект синхронизации в массиве блокирована.|  
|[CMultiLock::Lock](../Topic/CMultiLock::Lock.md)|Ожидания в массиве объектов синхронизации.|  
|[CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)|Освобождает все объекты, принадлежащие синхронизации.|  
  
## Заметки  
 `CMultiLock` не имеет базовый класс.  
  
 Для использования классов [CSemaphore](../../mfc/reference/csemaphore-class.md) синхронизации, [CMutex](../../mfc/reference/cmutex-class.md) и [CEvent](../../mfc/reference/cevent-class.md) можно создать или **CMultiLock**  или объект [CSingleLock](../../mfc/reference/csinglelock-class.md) ожидания в on и освобождение объекта синхронизации.  Используйте **CMultiLock**  если несколько объектов, которые можно использовать в указанное время.  Используйте `CSingleLock` обрабатывается при необходимости дожидаться в одном объекте.  
  
 Чтобы использовать объект **CMultiLock** , сначала создайте массив синхронизации возражает, что необходимо дождаться on.  Затем вызовите конструктор объекта **CMultiLock**  в функцию\-член управляемого ресурса в классе.  Затем вызовите функцию\-член [блокировка](../Topic/CMultiLock::Lock.md) для определения если ресурс доступен \(просигнализированный\).  Если таковой, то продолжите с остатком функции\-члена.  Если ресурс недоступен или подождите указанное время для ресурса должен освобождаться и возвращает ошибку.  После завершения использования ресурса любой вызов функции [Unlock](../Topic/CMultiLock::Unlock.md), если объект **CMultiLock**  использоваться повторно или позволяет объекту **CMultiLock** , который необходимо удалить.  
  
 Объекты **CMultiLock**  наиболее полезным, когда поток имеет большое количество объектов `CEvent` он может отвечать.  Создайте массив, содержащий все указатели `CEvent` и вызовите `Lock`.  Это приведет к потоку ожидать, пока не произойдет одно из событий посылается сигнал.  
  
 Дополнительные сведения о том, как использовать объекты **CMultiLock**  см. в статье [Многопоточность. Использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Иерархия наследования  
 `CMultiLock`  
  
## Требования  
 **Header:**  afxmt.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)