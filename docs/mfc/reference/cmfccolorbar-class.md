---
title: "CMFCColorBar Class | Microsoft Docs"
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
  - "CMFCColorBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorBar class"
  - "CMFCColorBar::m_bInternal data member"
  - "CMFCColorBar::m_bIsEnabled data member"
  - "CMFCColorBar::m_bIsTearOff data member"
  - "CMFCColorBar::m_BoxSize data member"
  - "CMFCColorBar::m_bShowDocColorsWhenDocked data member"
  - "CMFCColorBar::m_bStdColorDlg data member"
  - "CMFCColorBar::m_ColorAutomatic data member"
  - "CMFCColorBar::m_ColorNames data member"
  - "CMFCColorBar::m_colors data member"
  - "CMFCColorBar::m_ColorSelected data member"
  - "CMFCColorBar::m_lstDocColors data member"
  - "CMFCColorBar::m_nCommandID data member"
  - "CMFCColorBar::m_nHorzMargin data member"
  - "CMFCColorBar::m_nHorzOffset data member"
  - "CMFCColorBar::m_nNumColumns data member"
  - "CMFCColorBar::m_nNumColumnsVert data member"
  - "CMFCColorBar::m_nNumRowsHorz data member"
  - "CMFCColorBar::m_nRowHeight data member"
  - "CMFCColorBar::m_nVertMargin data member"
  - "CMFCColorBar::m_nVertOffset data member"
  - "CMFCColorBar::m_Palette data member"
  - "CMFCColorBar::m_pParentBtn data member"
  - "CMFCColorBar::m_pParentRibbonBtn data member"
  - "CMFCColorBar::m_pWndPropList data member"
  - "CMFCColorBar::m_strAutoColor data member"
  - "CMFCColorBar::m_strDocColors data member"
  - "CMFCColorBar::m_strOtherColor data member"
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCColorBar` закрепляющий представляет панель элементов управления, может выбирать цвета в документе или приложении.  
  
## Синтаксис  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorBar::CMFCColorBar](../Topic/CMFCColorBar::CMFCColorBar.md)|Создает объект `CMFCColorBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorBar::ContextToSize](../Topic/CMFCColorBar::ContextToSize.md)|Вычисляет отраслевую вертикали и горизонтальные поля, которое требуется для кнопок в элементе управления области содержат цвета, а затем обрабатывает расположение этих кнопок.|  
|[CMFCColorBar::CreateControl](../Topic/CMFCColorBar::CreateControl.md)|Создает окно элементе управления панель цвета, вложение его к объекту `CMFCColorBar` и изменяет размер элемента управления для размещения определенную палитру цветов.|  
|[CMFCColorBar::Create](../Topic/CMFCColorBar::Create.md)|Создает окно элементе управления панель цвета и вложение его к объекту `CMFCColorBar`.|  
|[CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md)|Автоматическая кнопку показывать или скрывать.|  
|[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)|Позволяет включить или отключить отображение диалогового окна, позволяющей пользователю выбрать дополнительные цвета.|  
|[CMFCColorBar::GetColor](../Topic/CMFCColorBar::GetColor.md)|Извлекает выбранный цвет.|  
|[CMFCColorBar::GetCommandID](../Topic/CMFCColorBar::GetCommandID.md)|Извлекает идентификатор команды управления панели текущего цвета.|  
|[CMFCColorBar::GetHighlightedColor](../Topic/CMFCColorBar::GetHighlightedColor.md)|Получает цвет, означает, что кнопку цвета имеет фокус; то есть кнопка *горяча*.|  
|[CMFCColorBar::GetHorzMargin](../Topic/CMFCColorBar::GetHorzMargin.md)|Извлекает горизонтальные поля, пространство между левой или правой ячейки, цвета и границы клиентской области.|  
|[CMFCColorBar::GetVertMargin](../Topic/CMFCColorBar::GetVertMargin.md)|Извлекает вертикальные поля, расстояние между верхней или нижней ячейки, цвета и границы клиентской области.|  
|[CMFCColorBar::IsTearOff](../Topic/CMFCColorBar::IsTearOff.md)|Показывает, является ли текущая закрепляемая панель цвета.|  
|[CMFCColorBar::SetColor](../Topic/CMFCColorBar::SetColor.md)|Устанавливает цвет, который в настоящий момент выбраны.|  
|[CMFCColorBar::SetColorName](../Topic/CMFCColorBar::SetColorName.md)|Устанавливает новое имя для указанного цвета.|  
|[CMFCColorBar::SetCommandID](../Topic/CMFCColorBar::SetCommandID.md)|Устанавливает новый идентификатор команды для управления панели цвета.|  
|[CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)|Задает список цветов, используемых в текущем документе.|  
|[CMFCColorBar::SetHorzMargin](../Topic/CMFCColorBar::SetHorzMargin.md)|Задает горизонтальные поля, пространство между левой или правой ячейки, цвета и границы клиентской области.|  
|[CMFCColorBar::SetVertMargin](../Topic/CMFCColorBar::SetVertMargin.md)|Задает вертикальные поля, расстояние между верхней или нижней ячейки, цвета и границы клиентской области.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorBar::AdjustLocations](../Topic/CMFCColorBar::AdjustLocations.md)|Обрабатывает положения кнопки цвет на элементе управления панели цвета.|  
|[CMFCColorBar::AllowChangeTextLabels](../Topic/CMFCColorBar::AllowChangeTextLabels.md)|Указывает, является ли текстовая подпись кнопки цвет может измениться.|  
|[CMFCColorBar::AllowShowOnList](../Topic/CMFCColorBar::AllowShowOnList.md)|Указывает, является ли объект управления панели цвета может появиться в списке панели инструментов во время процесса настройки.|  
|[CMFCColorBar::CalcSize](../Topic/CMFCColorBar::CalcSize.md)|Вызываемый платформой как часть процесса вычисления макета.|  
|[CMFCColorBar::CreatePalette](../Topic/CMFCColorBar::CreatePalette.md)|Initalizes палитра с цветами в указанном массиве цветов.|  
|[CMFCColorBar::GetColorGridSize](../Topic/CMFCColorBar::GetColorGridSize.md)|Вычисляет количество строк и столбцов в сетке управления панели цвета.|  
|[CMFCColorBar::GetExtraHeight](../Topic/CMFCColorBar::GetExtraHeight.md)|Вычисляет дополнительную высоту которой текущая область цвета для отображения различных элементов как **другое**, цветов документа пользовательского интерфейса и т д|  
|[CMFCColorBar::InitColors](../Topic/CMFCColorBar::InitColors.md)|Инициализирует массив цветов с цветами палитры или определенной палитры значения по умолчанию.|  
|[CMFCColorBar::OnKey](../Topic/CMFCColorBar::OnKey.md)|Вызываемый платформой, когда пользователь отожмет кнопку клавиатуры.|  
|[CMFCColorBar::OnSendCommand](../Topic/CMFCColorBar::OnSendCommand.md)|Вызываемый платформой, чтобы закрыть иерархия всплывающих элементов управления.|  
|[CMFCColorBar::OnUpdateCmdUI](../Topic/CMFCColorBar::OnUpdateCmdUI.md)|Вызываемый платформой отображения, чтобы включить или отключить элемент пользовательского интерфейса элемента управления панели цвета перед элементом.|  
|[CMFCColorBar::OpenColorDialog](../Topic/CMFCColorBar::OpenColorDialog.md)|Открывает диалоговое окно цвет.|  
|[CMFCColorBar::Rebuild](../Topic/CMFCColorBar::Rebuild.md)|Полностью перерисовывает элемент управления панель цвета.|  
|[CMFCColorBar::SelectPalette](../Topic/CMFCColorBar::SelectPalette.md)|Задает логическое палитру контекста заданного устройства в палитре родительской кнопки текущего элемента управления панели цвета.|  
|[CMFCColorBar::SetPropList](../Topic/CMFCColorBar::SetPropList.md)|Задает элемент данных, защищенный `m_pWndPropList` в заданный указатель к элементу управления сетки свойств.|  
|[CMFCColorBar::ShowCommandMessageString](../Topic/CMFCColorBar::ShowCommandMessageString.md)|Запрашивает фреймовое окно, содержащее элемент управления панель цвета для обновления линия сообщения в строке состояния.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|`m_bInternal`|Логическое поле, которое определяет, обрабатываются ли события мыши.  Обычно события мыши обрабатываются, когда это поле `TRUE` и настройка `FALSE`.|  
|`m_bIsEnabled`|Логическое значение, которое указывает, включен ли элемент управления.|  
|`m_bIsTearOff`|Логическое значение, указывающее, поддерживает ли элемент управления панели закрепления цвета.|  
|`m_BoxSize`|Объект [CSize](../../atl-mfc-shared/reference/csize-class.md), который определяет размер ячейки в сетке панели цвета.|  
|`m_bShowDocColorsWhenDocked`|Логическое значение, которое указывает, следует ли отображать цвета документа, если панель закреплена цвета.  Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md).|  
|`m_bStdColorDlg`|Логическое значение, которое указывает, следует ли отображать стандартная система рисует диалоговое окно или диалоговое окно [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md).  Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
|`m_ColorAutomatic`|[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449), которое сохраняет текущий автоцвет.  Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
|`m_ColorNames`|Объект [CMap](../../mfc/reference/cmap-class.md), который связывает набор RGB закрашивает с их именами.|  
|`m_colors`|[CArray](../../mfc/reference/carray-class.md) значений [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449), содержащее цветов, отображаемых в элементе управления панель цвета.|  
|`m_ColorSelected`|Значение [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449), являющийся цветом, который в данный момент пользователь выбрал из элемента управления панели цвета.|  
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) значений [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449), содержащее цвета, которые в данный момент используются в документе.|  
|`m_nCommandID`|Целое число без знака, идентификатор команды кнопки цвета.|  
|`m_nHorzMargin`|Целое число, горизонтальные поля между цветом застегивает в сетке цветов.|  
|`m_nHorzOffset`|Целое число, представляющее горизонтальное смещение в центре кнопки цвета.  Данное значение значительно если отображает кнопки СМС или вставке изображение в дополнение к цвету.|  
|`m_nNumColumns`|Целое число, представляющее количество столбцов в сетке элементе управления панель цвета цветов.|  
|`m_nNumColumnsVert`|Целое число, представляющее количество столбцов в вертикально, ориентированной сетке цветов.|  
|`m_nNumRowsHorz`|Целое число, представляющее количество столбцов в ориентированной сетке цветов по горизонтали.|  
|`m_nRowHeight`|Целое число, высота строки, цвета застегивает в сетке цветов.|  
|`m_nVertMargin`|Целое число, вертикальные поля между цветом застегивает в сетке цветов.|  
|`m_nVertOffset`|Целое число, вертикальное смещение в центре кнопки цвета.  Данное значение значительно если отображает кнопки СМС или вставке изображение в дополнение к цвету.|  
|`m_Palette`|[CPalette](../../mfc/reference/cpalette-class.md) цветов, используемых в элементе управления панель цвета.|  
|`m_pParentBtn`|Указатель на объект [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md), являющийся родительским для текущего кнопки.  Данное значение значительно, если кнопка цвета в иерархии элементов управления " Панель инструментов или в элементе управления сетки свойств цвета.|  
|`m_pParentRibbonBtn`|Указатель на объект [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md), на ленте и родительское текущей кнопки.  Данное значение значительно, если кнопка цвета в иерархии элементов управления " Панель инструментов или в элементе управления сетки свойств цвета.|  
|`m_pWndPropList`|Указатель на объект [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md).|  
|`m_strAutoColor`|[CString](../../atl-mfc-shared/reference/cstringt-class.md), текст, отображаемый на кнопке **Автоматически**.  Дополнительные сведения см. в разделе [CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md).|  
|`m_strDocColors`|[CString](../../atl-mfc-shared/reference/cstringt-class.md), текст, отображаемый на кнопке цветов документа.  Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md).|  
|`m_strOtherColor`|[CString](../../atl-mfc-shared/reference/cstringt-class.md), текст, отображаемый в *другой* кнопки.  Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
  
## Заметки  
 Обычно объект `CMFCColorBar` не создается непосредственно.  Вместо этого [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) \(используется в меню и панелей инструментов\) или [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md) создают объект `CMFCColorBar`.  
  
 Класс `CMFCColorBar` предоставляет следующие функциональные возможности:  
  
-   Автоматически обрабатывает список цветов документа.  
  
-   Сохраняет и получает ее состояние вместе с состоянием документа.  
  
-   Управляет "автоматический".  
  
-   Использует управление [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md), чтобы выбрать пользовательский цвет.  
  
-   Поддерживает "перемещаемое" состояние \(при его создании с помощью [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md)\).  
  
 Включать функции `CMFCColorBar` в приложение.  
  
1.  Создайте обычную кнопку меню и присвойте ей идентификатор, например ID\_CHAR\_COLOR.  
  
2.  В классе фреймового окна, переопределите метод [CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md) и замените обычную кнопку меню с объектом [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) \(путем вызова [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)\).  
  
3.  Установите все стили и включение или отключение функции объекта `CMFCColorBar` во время создания [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md).  Объект `CMFCColorMenuButton` динамически создает объект `CMFCColorBar` после того как платформа вызывает метод `CreatePopupMenu`.  
  
 При нажатии пользователем кнопки элементе управления панель цвета, границы используется макрос `ON_COMMAND` для уведомления родительский элемент управления панели цвета.  В макросе, параметр идентификатор команды значения, присвоенного ему пользователем кнопки элементе управления панель цвета в шаге 1 \(ID\_CHAR\_COLOR в этом примере\).  Дополнительные сведения см. в разделе [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) классы, [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md) и [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  
  
## Пример  
 В следующем примере показано, как настроить панель цвета с помощью различных методов в классе `CMFCColorBar`.  Методы устанавливают горизонтальной и вертикальной поля, включают другой кнопки, создают окно элементе управления панель цвета и наборы выбранный цвет.  Данный пример является частью [Создать образец элементов управления](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/CPP/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/CPP/cmfccolorbar-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## Требования  
 **заголовок:** afxcolorbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)