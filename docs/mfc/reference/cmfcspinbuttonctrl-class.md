---
title: "CMFCSpinButtonCtrl Class | Microsoft Docs"
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
  - "CMFCSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCSpinButtonCtrl class"
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCSpinButtonCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCSpinButtonCtrl` поддерживает диспетчер визуального представления, который рисует элемент управления "Кнопка", "счетчик".  
  
## Синтаксис  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Конструктор по умолчанию.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCSpinButtonCtrl::OnDraw](../Topic/CMFCSpinButtonCtrl::OnDraw.md)|Обновляет текущий элемент управления "Кнопка", "счетчик".|  
  
## Заметки  
 Для использования диспетчера визуального представления отрисовки элемента управления "Кнопка", "счетчик" в приложении замените все экземпляры класса `CSpinButtonCtrl` с классом `CMFCSpinButtonCtrl`.  
  
## Пример  
 В следующем примере показано, как создать объект класса `CMFCSpinButtonCtrl` и использовать его метод `Create`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/CPP/cmfcspinbuttonctrl-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## Требования  
 **заголовок:** afxspinbuttonctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)