---
title: "Класс CMFCPopupMenuBar | Microsoft Docs"
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
  - "CMFCPopupMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CMFCPopupMenuBar"
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CMFCPopupMenuBar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Строка меню, встроенную в контекстное меню меню.  
  
## Синтаксис  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](../Topic/CMFCPopupMenuBar::AdjustSizeImmediate.md)|Немедленно выполняет перерасчет структуры области.  Переопределения \( [CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md)\).|  
|[CMFCPopupMenuBar::BuildOrigItems](../Topic/CMFCPopupMenuBar::BuildOrigItems.md)|Загружает всплывающие пункты меню из определенного ресурса меню.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](../Topic/CMFCPopupMenuBar::CloseDelayedSubMenu.md)|Закрывает задержанная всплывающая кнопка меню.|  
|[CMFCPopupMenuBar::ExportToMenu](../Topic/CMFCPopupMenuBar::ExportToMenu.md)|Создает из меню кнопки всплывающий\- меню.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](../Topic/CMFCPopupMenuBar::FindDestintationToolBar.md)|Найдите инструмент, определенная точка находится.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](../Topic/CMFCPopupMenuBar::GetCurrentMenuImageSize.md)|Отображает размер изображений возврата кнопки.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](../Topic/CMFCPopupMenuBar::GetDefaultMenuId.md)|Возвращает идентификатор элемента меню по умолчанию.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](../Topic/CMFCPopupMenuBar::GetLastCommandIndex.md)|Получает индекс последним призванной команды меню.|  
|[CMFCPopupMenuBar::GetOffset](../Topic/CMFCPopupMenuBar::GetOffset.md)|Получает смещение строки всплывающей строки меню.|  
|[CMFCPopupMenuBar::ImportFromMenu](../Topic/CMFCPopupMenuBar::ImportFromMenu.md)|Импортирует всплывающие меню кнопки из указанного меню.|  
|[CMFCPopupMenuBar::IsDropDownListMode](../Topic/CMFCPopupMenuBar::IsDropDownListMode.md)|Указывает, является ли строка меню отобразится в режиме раскрывающегося списка.|  
|[CMFCPopupMenuBar::IsPaletteMode](../Topic/CMFCPopupMenuBar::IsPaletteMode.md)|Указывает, является ли строка меню отобразится в режиме палитры.|  
|[CMFCPopupMenuBar::IsRibbonPanel](../Topic/CMFCPopupMenuBar::IsRibbonPanel.md)|Указывает, является ли это панель ленты по умолчанию \(`FALSE` \).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](../Topic/CMFCPopupMenuBar::IsRibbonPanelInRegularMode.md)|Указывает, является ли это панель ленты в обычном режиме \(`FALSE` \) по умолчанию.|  
|[CMFCPopupMenuBar::LoadFromHash](../Topic/CMFCPopupMenuBar::LoadFromHash.md)|Загружает архивированное меню.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](../Topic/CMFCPopupMenuBar::RestoreDelayedSubMenu.md)|Восстановление задержанной кнопки меню для закрыть всплывающая строки меню.|  
|[CMFCPopupMenuBar::SetButtonStyle](../Topic/CMFCPopupMenuBar::SetButtonStyle.md)|Задает стиль кнопки панели инструментов в заданной индекс.  Переопределения \( [CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md)\).|  
|[CMFCPopupMenuBar::SetOffset](../Topic/CMFCPopupMenuBar::SetOffset.md)|Задает смещение строки всплывающей строки меню.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](../Topic/CMFCPopupMenuBar::StartPopupMenuTimer.md)|Запускает таймер для указанной задержанной всплывающей кнопки меню.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPopupMenuBar::m\_bDisableSideBarInXPMode](../Topic/CMFCPopupMenuBar::m_bDisableSideBarInXPMode.md)|Определяет, отображается ли серое поле, когда приложение будет иметь вид Windows XP.|  
  
## Заметки  
 `CMFCPopupMenuBar` создается в то время как [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md) и внедряется внутри него.  `CMFCPopupMenuBar` охватывает всю клиентскую область объекта `CMFCPopupMenu`.  Он поддерживает ввода мыши и клавиатуры.  Он также связывает эти сведения в `CMFCPopupMenu` и к высшего уровня фреймовому окно.  
  
## Пример  
 В следующем примере показано, как инициализировать объект `CMFCPopupMenuBar` из объекта `CMFCPopupMenu`.  Этот фрагмент кода часть [В образце клиента рисования](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/CPP/cmfcpopupmenubar-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## Требования  
 **Заголовок:** afxpopupmenubar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md)