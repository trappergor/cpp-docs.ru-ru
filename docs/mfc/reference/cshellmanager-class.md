---
title: "CShellManager Class | Microsoft Docs"
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
  - "CShellManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CShellManager class"
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CShellManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует несколько методов, которые позволяют работать с указателями к спискам идентификатора \(PIDLs\).  
  
## Синтаксис  
  
```  
class CShellManager : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CShellManager::CShellManager](../Topic/CShellManager::CShellManager.md)|Создает объект `CShellManager`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CShellManager::BrowseForFolder](../Topic/CShellManager::BrowseForFolder.md)|Отображает диалоговое окно, которое позволяет пользователю выбрать папку оболочки.|  
|[CShellManager::ConcatenateItem](../Topic/CShellManager::ConcatenateItem.md)|Сцепляет 2 PIDLs.|  
|[CShellManager::CopyItem](../Topic/CShellManager::CopyItem.md)|Создает новый PIDL и копирует в него заданное PIDL.|  
|[CShellManager::CreateItem](../Topic/CShellManager::CreateItem.md)|Создает новый PIDL указанного размера.|  
|[CShellManager::FreeItem](../Topic/CShellManager::FreeItem.md)|Удаляет указанное PIDL.|  
|[CShellManager::GetItemCount](../Topic/CShellManager::GetItemCount.md)|Возвращает количество элементов в предоставляемом PIDL.|  
|[CShellManager::GetItemSize](../Topic/CShellManager::GetItemSize.md)|Возвращает размер предоставленного PIDL.|  
|[CShellManager::GetNextItem](../Topic/CShellManager::GetNextItem.md)|Возвращает следующий элемент из PIDL.|  
|[CShellManager::GetParentItem](../Topic/CShellManager::GetParentItem.md)|Возвращает родительский элемент указанного элемента.|  
|[CShellManager::ItemFromPath](../Topic/CShellManager::ItemFromPath.md)|Извлекает PIDL для элемента заданного предоставленным путем.|  
  
## Заметки  
 Все методы `CShellManager` классифицируют дело с PIDLs.  PIDL уникальный идентификатор для объекта оболочки.  
  
 Не следует создать объект `CShellManager` вручную.  Он будет создать автоматически платформой приложения.  Однако необходимо вызвать [CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md) в процессе инициализации приложения.  Получить указатель на него оболочки для приложения, вызов [CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## Требования  
 **заголовок:** afxshellmanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)