---
title: "CSplitButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitButton class"
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSplitButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CSplitButton` представляющий разворачивающуюся кнопку элемента управления.  Управление разворачивающаяся кнопка выполняет расширение функциональности по умолчанию, когда пользователь щелкает основной части кнопки и отображает раскрывающееся меню, когда пользователь нажимает стрелку раскрывающегося меню кнопки.  
  
## Синтаксис  
  
```  
class CSplitButton : public CButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSplitButton::CSplitButton](../Topic/CSplitButton::CSplitButton.md)|Создает объект `CSplitButton`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSplitButton::Create](../Topic/CSplitButton::Create.md)|Создает элемент управления разворачивающаяся кнопка с различными стилями и вложение его к текущему объекту `CSplitButton`.|  
|[CSplitButton::SetDropDownMenu](../Topic/CSplitButton::SetDropDownMenu.md)|Устанавливает раскрывающееся меню, которое отображается, когда пользователь нажимает стрелку раскрывающегося списка для текущего элемента управления разворачивающейся кнопки.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSplitButton::OnDropDown](../Topic/CSplitButton::OnDropDown.md)|Обрабатывает уведомление `BCN_DROPDOWN`, система отправляет когда пользователь щелкает стрелку раскрывающегося списка для текущего элемента управления разворачивающейся кнопки.|  
  
## Заметки  
 Класс `CSplitButton` является производным от класса [CButton](../../mfc/reference/cbutton-class.md).  Управление разворачивающуюся кнопку элемента управления "Кнопка" стиль, `BS_SPLITBUTTON`.  Отображает пользовательское меню, когда пользователь нажимает стрелку раскрывающегося списка.  Дополнительные сведения см. в разделе styles `BS_SPLITBUTTON` и `BS_DEFSPLITBUTTON` в [стили кнопки](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 Следующая диаграмма отображает диалоговое окно, содержащее элемент управления страничного навигатора \(1\) и элемент управления разворачивающейся кнопки.  \(2\) Стрелку раскрывающегося списка уже была нажата и \(3\), подменю ".  
  
 ![Диалоговое окно с кнопкой&#45;разделителем и элементом управления страничного навигатора.](../../mfc/reference/media/splitbutton_pager.png "SplitButton\_Pager")  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## Требования  
 **заголовок:** afxcmn.h  
  
 Этот класс поддерживается в [!INCLUDE[windowsver](../Token/windowsver_md.md)] и более поздних версиях.  
  
 Дополнительные требования для этого класса см. в [Требования к сборке для использования стандартных элементов управления в Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
## См. также  
 [CSplitButton Class](../../mfc/reference/csplitbutton-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)