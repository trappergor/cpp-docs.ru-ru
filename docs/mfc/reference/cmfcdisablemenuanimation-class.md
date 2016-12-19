---
title: "CMFCDisableMenuAnimation Class | Microsoft Docs"
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
  - "CMFCDisableMenuAnimation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDisableMenuAnimation class"
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDisableMenuAnimation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Запрещает анимация раскрывающегося меню.  
  
## Синтаксис  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Создает объект `CMFCDisableMenuAnimation`.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Деструктор.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCDisableMenuAnimation::Restore](../Topic/CMFCDisableMenuAnimation::Restore.md)|Извлекает предыдущая анимации, границы, используемые для отображения раскрывающегося меню.|  
  
### Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDisableMenuAnimation::m_animType`|Хранит предыдущий тип анимации раскрывающегося меню.|  
  
### Заметки  
 Используйте этот вспомогательный класс для временного отключения анимации раскрывающегося меню \(например, при обработаете команды мыши или клавиатуры\).  
  
 Объект `CMFCDisableMenuAnimation` запрещает анимация раскрывающегося меню во время существования.  Конструктор сохраняет текущую анимация раскрывающегося меню и введите в поле наборы `m_animType` текущий тип анимации к `CMFCPopupMenu::NO_ANIMATION`.  Деструктор извлекает предыдущий тип анимации.  
  
 Можно создать объект `CMFCDisableMenuAnimation` в стеке для отключения анимации раскрывающегося меню в рамках одной функции.  Если требуется отключить всплывающая анимация меню между функциями, создайте объект `CMFCDisableMenuAnimation` в куче, а затем удалите его, если необходимо извлечь анимация раскрывающегося меню.  
  
## Пример  
 В следующем примере показано, как использовать стек, чтобы временно отключить анимация меню.  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/CPP/cmfcdisablemenuanimation-class_1.h)]  
  
## Иерархия наследования  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## Требования  
 **заголовок:** afxpopupmenu.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md)