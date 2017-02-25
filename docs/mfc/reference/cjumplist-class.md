---
title: "CJumpList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxadv/CJumpList"
  - "CJumpList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CJumpList class"
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CJumpList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CJumpList`, приведенный список ярлыков при нажатии правой кнопкой мыши на значок в области задач.  
  
## Синтаксис  
  
```  
class CJumpList;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CJumpList::CJumpList](../Topic/CJumpList::CJumpList.md)|Создает объект `CJumpList`.|  
|[CJumpList::~CJumpList](../Topic/CJumpList::~CJumpList.md)|Удаляет объект `CJumpList`.|  
  
|Имя|Описание|  
|---------|--------------|  
|[CJumpList::AbortList](../Topic/CJumpList::AbortList.md)|Прерывает построение без фиксации транзакции список\-.|  
|[CJumpList::AddDestination](../Topic/CJumpList::AddDestination.md)|Перегружен.  Добавление назначения к списку.|  
|[CJumpList::AddKnownCategory](../Topic/CJumpList::AddKnownCategory.md)|Добавляет известной категорию в список.|  
|[CJumpList::AddTask](../Topic/CJumpList::AddTask.md)|Перегружен.  Добавляет элементы в канонической категории задач.|  
|[CJumpList::AddTasks](../Topic/CJumpList::AddTasks.md)|Добавляет элементы в канонической категории задач.|  
|[CJumpList::AddTaskSeparator](../Topic/CJumpList::AddTaskSeparator.md)|Добавляет разделитель между задачами.|  
|[CJumpList::ClearAll](../Topic/CJumpList::ClearAll.md)|Удаляет все задачи и назначения, которые были добавлены к текущему экземпляру `CJumpList` на данный момент.|  
|[CJumpList::ClearAllDestinations](../Topic/CJumpList::ClearAllDestinations.md)|Удаляет все назначения, которые были добавлены к текущему экземпляру `CJumpList` на данный момент.|  
|[CJumpList::CommitList](../Topic/CJumpList::CommitList.md)|Завершает транзакцию и фиксирует построение список\- определяется список в связанный обработчик действия хранилище \(реестр в этом случае\).|  
|[CJumpList::GetDestinationList](../Topic/CJumpList::GetDestinationList.md)|Получает указатель интерфейса на список назначения.|  
|[CJumpList::GetMaxSlots](../Topic/CJumpList::GetMaxSlots.md)|Возвращает максимальное количество элементов, включая заголовки категории, которые могут отображаться в меню назначения вызывающего приложения.|  
|[CJumpList::GetRemovedItems](../Topic/CJumpList::GetRemovedItems.md)|Массив возвращений элементов, представляющих удаленные назначения.|  
|[CJumpList::InitializeList](../Topic/CJumpList::InitializeList.md)|Начинает транзакцию список\- дома.|  
|[CJumpList::SetAppID](../Topic/CJumpList::SetAppID.md)|Задает идентификатор модели пользователя приложения список, который будет построен.|  
  
## Иерархия наследования  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## Требования  
 **заголовок:**  afxadv.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)