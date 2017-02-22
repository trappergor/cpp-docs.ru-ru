---
title: "COleDispatchDriver Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDispatchDriver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation clients, implementing Automation"
  - "COleDispatchDriver class"
  - "OLE dispatch interface"
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleDispatchDriver Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует сторону клиента ole\-автоматизации.  
  
## Синтаксис  
  
```  
class COleDispatchDriver  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDispatchDriver::COleDispatchDriver](../Topic/COleDispatchDriver::COleDispatchDriver.md)|Создает объект `COleDispatchDriver`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDispatchDriver::AttachDispatch](../Topic/COleDispatchDriver::AttachDispatch.md)|Вложение соединение `IDispatch` к объекту `COleDispatchDriver`.|  
|[COleDispatchDriver::CreateDispatch](../Topic/COleDispatchDriver::CreateDispatch.md)|Создает соединение `IDispatch` и вложение его к объекту `COleDispatchDriver`.|  
|[COleDispatchDriver::DetachDispatch](../Topic/COleDispatchDriver::DetachDispatch.md)|Наконец удаляет соединение `IDispatch` без его освобождения.|  
|[COleDispatchDriver::GetProperty](../Topic/COleDispatchDriver::GetProperty.md)|Возвращает свойство автоматизации.|  
|[COleDispatchDriver::InvokeHelper](../Topic/COleDispatchDriver::InvokeHelper.md)|Вспомогательный метод для вызова методов автоматизации.|  
|[COleDispatchDriver::ReleaseDispatch](../Topic/COleDispatchDriver::ReleaseDispatch.md)|Освобождает соединение `IDispatch`.|  
|[COleDispatchDriver::SetProperty](../Topic/COleDispatchDriver::SetProperty.md)|Устанавливает свойство автоматизации.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDispatchDriver::operator \=](../Topic/COleDispatchDriver::operator%20=.md)|Копирует значение источника в объект `COleDispatchDriver`.|  
|[COleDispatchDriver::operator LPDISPATCH](../Topic/COleDispatchDriver::operator%20LPDISPATCH.md)|Обращается к базовому указатель `IDispatch`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDispatchDriver::m\_bAutoRelease](../Topic/COleDispatchDriver::m_bAutoRelease.md)|Определяет, является ли выпуск `IDispatch` во время `ReleaseDispatch` или возразить разрушение.|  
|[COleDispatchDriver::m\_lpDispatch](../Topic/COleDispatchDriver::m_lpDispatch.md)|Выводит указатель на интерфейс `IDispatch` вложенный к этому `COleDispatchDriver`.|  
  
## Заметки  
 `COleDispatchDriver` не имеет базовый класс.  
  
 Интерфейсы OLE диспетчера обеспечивают доступ к методам и свойствам объекта.  Функции\-члены `COleDispatchDriver` вложат, наконец удалить, создают и освобождает соединение диспетчера типа `IDispatch`.  Другие функции\-члены используют переменные списки аргументов, чтобы упростить вызов **IDispatch::Invoke**.  
  
 Этот класс может использоваться непосредственно, но обычно используется только теми классами, созданными с помощью мастера добавления классов.  При создании нового C\+\+ classify, импортировать библиотеку типов, новые классы являются производными от `COleDispatchDriver`.  
  
 Дополнительные сведения об использовании `COleDispatchDriver` см. в следующих статьях:  
  
-   [Клиенты автоматизации](../../mfc/automation-clients.md)  
  
-   [Серверы автоматизации](../../mfc/automation-servers.md)  
  
## Иерархия наследования  
 `COleDispatchDriver`  
  
## Требования  
 **Header:**  afxdisp.h  
  
## См. также  
 [Пример CALCDRIV MFC](../../top/visual-cpp-samples.md)   
 [Образец ACDUAL MFC](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)