---
title: "CControlBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CControlBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlBar class"
  - "control bars [C++], базовый класс"
  - "dialog bars, базовый класс"
  - "OLE resize bars"
  - "OLE resize bars, базовый класс"
  - "строки состояния, базовый класс"
  - "панели инструментов [C++], базовый класс"
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CControlBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для классов [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md) и [COleResizeBar](../../mfc/reference/coleresizebar-class.md) для панелей элементов управления.  
  
## Синтаксис  
  
```  
class CControlBar : public CWnd  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CControlBar::CControlBar](../Topic/CControlBar::CControlBar.md)|Создает объект `CControlBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CControlBar::CalcDynamicLayout](../Topic/CControlBar::CalcDynamicLayout.md)|Возвращает размер панели динамического элемента управления как объект [CSize](../../atl-mfc-shared/reference/csize-class.md).|  
|[CControlBar::CalcFixedLayout](../Topic/CControlBar::CalcFixedLayout.md)|Возвращает размер панели элементов управления как объект [CSize](../../atl-mfc-shared/reference/csize-class.md).|  
|[CControlBar::CalcInsideRect](../Topic/CControlBar::CalcInsideRect.md)|Возвращает текущие размеры области панели элементов управления; включая границы.|  
|[CControlBar::DoPaint](../Topic/CControlBar::DoPaint.md)|Отображает границы и границу панели элементов управления.|  
|[CControlBar::DrawBorders](../Topic/CControlBar::DrawBorders.md)|Отображает границы панели элементов управления.|  
|[CControlBar::DrawGripper](../Topic/CControlBar::DrawGripper.md)|Отрисовывает границу панели элементов управления.|  
|[CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md)|Позволяет панель элементов управления для закрепления или плавать.|  
|[CControlBar::GetBarStyle](../Topic/CControlBar::GetBarStyle.md)|Получает параметры стиля панели элементов управления.|  
|[CControlBar::GetBorders](../Topic/CControlBar::GetBorders.md)|Извлекает значения границы панели элементов управления.|  
|[CControlBar::GetCount](../Topic/CControlBar::GetCount.md)|Возвращает количество элементов `HWND` не в панели элементов управления.|  
|[CControlBar::GetDockingFrame](../Topic/CControlBar::GetDockingFrame.md)|Возвращает указатель на кадр, к которому панель элементов управления обрезается.|  
|[CControlBar::IsFloating](../Topic/CControlBar::IsFloating.md)|Возвращает ненулевое значение, если панель элементов управления в сообщении панель элементов управления с плавающей запятой.|  
|[CControlBar::OnUpdateCmdUI](../Topic/CControlBar::OnUpdateCmdUI.md)|Вызывает обработчик пользовательского интерфейса команды.|  
|[CControlBar::SetBarStyle](../Topic/CControlBar::SetBarStyle.md)|Изменяет параметры стиля панели элементов управления.|  
|[CControlBar::SetBorders](../Topic/CControlBar::SetBorders.md)|Задает граничные значения панели элементов управления.|  
|[CControlBar::SetInPlaceOwner](../Topic/CControlBar::SetInPlaceOwner.md)|Изменяется на месте владелец панели элементов управления.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CControlBar::m\_bAutoDelete](../Topic/CControlBar::m_bAutoDelete.md)|Если значение не равно нулю, объект `CControlBar` удаляется, когда панель элементов управления Windows разрушена.|  
|[CControlBar::m\_pInPlaceOwner](../Topic/CControlBar::m_pInPlaceOwner.md)|Внутренний владелец панели элементов управления.|  
  
## Заметки  
 Панель элементов управления окно, обычно выравнивано в левой или правой фреймового окна.  Она может содержать дочерние элементы, все элементы управления `HWND` на основе, окна, которые создают и отвечать на них Windows, или не элементы `HWND` на основе, что не окон и управляемых кодом приложения или кодом платформы.  Списки и элементы управления "Поле ввода" примеры элементов управления, основанных на `HWND`. области строки состояния и кнопки растрового изображения примеры, элементов управления, основанных на `HWND`.  
  
 Окно панели элементов управления обычно дочерние окна родительского фреймового окна и обычно одноуровневые в представление клиента или клиент MDI фреймового окна.  Объект `CControlBar` использует сведения о прямоугольнике клиента родительского окна для размещения.  После этого родительское окно уведомляет о влияния пробел остается освобожданным в клиентской области родительского окна.  
  
 Дополнительные сведения о `CControlBar` см. в разделе:  
  
-   [Панели элементов управления](../Topic/Control%20Bars.md)  
  
-   [Техническое примечание 31. Панели элементов управления](../../mfc/tn031-control-bars.md).  
  
-   Q242577 статья базы знаний: PRB: Обработчики пользовательского интерфейса команды обновления не работают для вложенного меню в диалоговое окно  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CControlBar`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [Пример CTRLBARS MFC](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar Class](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)   
 [CReBar Class](../../mfc/reference/crebar-class.md)