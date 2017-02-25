---
title: "CMFCTasksPaneTaskGroup Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPaneTaskGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTaskGroup class"
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCTasksPaneTaskGroup Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCTasksPaneTaskGroup` вспомогательный класс, который используется элементом управления [CMFCTasksPane](../Topic/CMFCTasksPane%20Class.md).  Объекты типа `CMFCTasksPaneTaskGroup` представляют *группу целевого назначения*.  Группа целевого назначения список элементов, которые отображает платформы в отдельном окне, имеется кнопка свернуть ".  Окно может иметь необязательный заголовок \(имя группы\).  Если группа свернута, то список задач не виден.  
  
## Синтаксис  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](../Topic/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup.md)|Создает объект `CMFCTasksPaneTaskGroup`.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](../Topic/CMFCTasksPaneTaskGroup::SetACCData.md)|Определяет сведения о специальных возможностей для текущей группы целевого назначения.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTasksPaneTaskGroup::m\_bIsBottom](../Topic/CMFCTasksPaneTaskGroup::m_bIsBottom.md)|Определяет, является ли группа выравнена целевого назначения до нижней части элемента управления области задач.|  
|[CMFCTasksPaneTaskGroup::m\_bIsCollapsed](../Topic/CMFCTasksPaneTaskGroup::m_bIsCollapsed.md)|Определяет, является ли группа свернута целевого назначения.|  
|[CMFCTasksPaneTaskGroup::m\_bIsSpecial](../Topic/CMFCTasksPaneTaskGroup::m_bIsSpecial.md)|Определяет, является ли группа целевого назначения *специальна.* Границы отображаются специальные заголовки в другом цветом.|  
|[CMFCTasksPaneTaskGroup::m\_lstTasks](../Topic/CMFCTasksPaneTaskGroup::m_lstTasks.md)|Содержит внутренний список задач.|  
|[CMFCTasksPaneTaskGroup::m\_rect](../Topic/CMFCTasksPaneTaskGroup::m_rect.md)|Указывает ограничивающий прямоугольник заголовка группы.|  
|[CMFCTasksPaneTaskGroup::m\_rectGroup](../Topic/CMFCTasksPaneTaskGroup::m_rectGroup.md)|Указывает ограничивающий прямоугольник группы.|  
|[CMFCTasksPaneTaskGroup::m\_strName](../Topic/CMFCTasksPaneTaskGroup::m_strName.md)|Указывает имя группы.|  
  
## Заметки  
 На следующей иллюстрации показана развернутую группу целевого назначения.  
  
 ![Развернутая группа задач](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
 На следующей иллюстрации показана свернутую группу целевого назначения.  
  
 ![Свернутая группа задач](../Image/NextTaskGrpCollapse.png "NextTaskGrpCollapse")  
  
 На следующей иллюстрации показана группа целевого назначения не имеет заголовка.  
  
 ![Группа задач без заголовка](../../mfc/reference/media/nexttaskgrpnocapt.png "NextTaskGrpNoCapt")  
  
 На следующей иллюстрации показана 2 группы целевого назначения.  Первая группа целевого назначения помечена как специальный с помощью пометить `m_bIsSpecial` к `TRUE`, а вторая группа целевого назначения не специальна.  Обратите внимание, что заголовок для первой группы целевого назначения темне, чем вторая группа целевого назначения.  
  
 ![Специальная группа задач](../../mfc/reference/media/nexttaskgrpspecial.png "NextTaskGrpSpecial")  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## Требования  
 **заголовок:** afxTasksPane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCTasksPane Class](../Topic/CMFCTasksPane%20Class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject Class](../Topic/CObject%20Class.md)