---
title: "CMFCTasksPaneTask Class | Microsoft Docs"
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
  - "CMFCTasksPaneTask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTask class"
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTasksPaneTask Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCTasksPaneTask` вспомогательный класс, представляющий задачи для управления области задач \([CMFCTasksPane](../Topic/CMFCTasksPane%20Class.md)\).  Объект задачи представляет элемент в группе целевого назначения \([CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)\).  Каждая задача может иметь границы команду, которая выполняется, когда пользователь щелкает задачу и значок, который отображается слева от имени задачи.  
  
## Синтаксис  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](../Topic/CMFCTasksPaneTask::CMFCTasksPaneTask.md)|Создает и инициализирует объект `CMFCTasksPaneTask`.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTasksPaneTask::SetACCData](../Topic/CMFCTasksPaneTask::SetACCData.md)|Определяет сведения о специальных возможностей для текущей задачи.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTasksPaneTask::m\_bAutoDestroyWindow](../Topic/CMFCTasksPaneTask::m_bAutoDestroyWindow.md)|Определяет, является ли окно задачи уничтожении автоматически.|  
|[CMFCTasksPaneTask::m\_bIsBold](../Topic/CMFCTasksPaneTask::m_bIsBold.md)|Определяет, является ли выпишут границы метка задачи полужирным шрифтом.|  
|[CMFCTasksPaneTask::m\_dwUserData](../Topic/CMFCTasksPaneTask::m_dwUserData.md)|Содержит определяемые пользователем данные, которые связаны с задачей границы.  Задайте значение ноль, если задача не имеет связанных данных.|  
|[CMFCTasksPaneTask::m\_hwndTask](../Topic/CMFCTasksPaneTask::m_hwndTask.md)|Дескриптор окна задачи.|  
|[CMFCTasksPaneTask::m\_nIcon](../Topic/CMFCTasksPaneTask::m_nIcon.md)|Индекс в списке завершения образа образа отображается рядом с задачей платформы.|  
|[CMFCTasksPaneTask::m\_nWindowHeight](../Topic/CMFCTasksPaneTask::m_nWindowHeight.md)|Высота окна задачи.  Если задача не имеет окно "задачи", то это значение равно нулю.|  
|[CMFCTasksPaneTask::m\_pGroup](../Topic/CMFCTasksPaneTask::m_pGroup.md)|Указатель на `CMFCTasksPaneTaskGroup`, что эта задача принадлежит.|  
|[CMFCTasksPaneTask::m\_rect](../Topic/CMFCTasksPaneTask::m_rect.md)|Указывает ограничивающий прямоугольник задачи.|  
|[CMFCTasksPaneTask::m\_strName](../Topic/CMFCTasksPaneTask::m_strName.md)|Имя данной задачи.|  
|[CMFCTasksPaneTask::m\_uiCommandID](../Topic/CMFCTasksPaneTask::m_uiCommandID.md)|Указывает идентификатор команды, границы выполняются, когда пользователь щелкает задачу.  Если это значение не является допустимым идентификатором команды, задача обрабатывается как простая метка.|  
  
## Заметки  
 На следующей иллюстрации показана группа целевого назначения, которая содержит 3 задачи:  
  
 ![Развернутая группа задач](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
> [!NOTE]
>  Если задача не имеют допустимого идентификатор команды, она обрабатывается как простая метка.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## Требования  
 **заголовок:** afxTasksPane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CObject Class](../Topic/CObject%20Class.md)