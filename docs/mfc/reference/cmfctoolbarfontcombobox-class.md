---
title: "CMFCToolBarFontComboBox Class | Microsoft Docs"
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
  - "CMFCToolBarFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontComboBox class"
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: 29
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Кнопка панели инструментов, содержащую элемент управления поля со списком, позволяющий пользователю выбрать шрифт из списка шрифтов системы.  
  
## Синтаксис  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](../Topic/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox.md)|Создает объект `CMFCToolBarFontComboBox`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md)|Возвращает указатель на объект `CMFCFontInfo` для указанного индекса в поле со списком.|  
|[CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md)|Выбирает шрифт в поле со списком шрифт или имя шрифта или в соответствии с префикса и кодировку шрифта.|  
  
### Элементы данных  
 [CMFCToolBarFontComboBox::m\_nFontHeight](../Topic/CMFCToolBarFontComboBox::m_nFontHeight.md)  
 Высота символов в поле со списком шрифт.  
  
## Заметки  
 Чтобы добавить поле со списком шрифт на панели инструментов, выполните следующие действия:  
  
1.  Зарезервируйте фиктивное идентификатор ресурса для кнопки в родительском ресурсе панели инструментов.  
  
2.  Создайте объект `CMFCToolBarFontComboBox`.  
  
3.  В обработчике сообщений, который обрабатывает сообщение `AFX_WM_RESETTOOLBAR` замените исходный кнопку с новой кнопкой поля со списком с помощью [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
4.  Синхронизировать шрифт, выберите в поле со списком с шрифтом в документе с помощью метода [CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md).  
  
 Чтобы синхронизировать шрифт документа с шрифт выбранного в поле со списком, используйте метод [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) для извлечения атрибутов выбранного шрифта и используйте эти атрибуты для создания объекта [CFont Class](../../mfc/reference/cfont-class.md).  
  
 Поле со списком шрифта Win32 [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) функция вызывается, чтобы определить шрифты экрана и принтера, доступные в системе.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../Topic/CMFCToolBarComboBoxButton%20Class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## Требования  
 **заголовок:** afxtoolbarfontcombobox.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../Topic/CMFCToolBarComboBoxButton%20Class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)