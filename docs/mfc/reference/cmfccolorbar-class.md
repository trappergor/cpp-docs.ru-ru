---
title: Класс CMFCColorBar | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorBar [MFC], CMFCColorBar
- CMFCColorBar [MFC], ContextToSize
- CMFCColorBar [MFC], CreateControl
- CMFCColorBar [MFC], Create
- CMFCColorBar [MFC], EnableAutomaticButton
- CMFCColorBar [MFC], EnableOtherButton
- CMFCColorBar [MFC], GetColor
- CMFCColorBar [MFC], GetCommandID
- CMFCColorBar [MFC], GetHighlightedColor
- CMFCColorBar [MFC], GetHorzMargin
- CMFCColorBar [MFC], GetVertMargin
- CMFCColorBar [MFC], IsTearOff
- CMFCColorBar [MFC], SetColor
- CMFCColorBar [MFC], SetColorName
- CMFCColorBar [MFC], SetCommandID
- CMFCColorBar [MFC], SetDocumentColors
- CMFCColorBar [MFC], SetHorzMargin
- CMFCColorBar [MFC], SetVertMargin
- CMFCColorBar [MFC], AdjustLocations
- CMFCColorBar [MFC], AllowChangeTextLabels
- CMFCColorBar [MFC], AllowShowOnList
- CMFCColorBar [MFC], CalcSize
- CMFCColorBar [MFC], CreatePalette
- CMFCColorBar [MFC], GetColorGridSize
- CMFCColorBar [MFC], GetExtraHeight
- CMFCColorBar [MFC], InitColors
- CMFCColorBar [MFC], OnKey
- CMFCColorBar [MFC], OnSendCommand
- CMFCColorBar [MFC], OnUpdateCmdUI
- CMFCColorBar [MFC], OpenColorDialog
- CMFCColorBar [MFC], Rebuild
- CMFCColorBar [MFC], SelectPalette
- CMFCColorBar [MFC], SetPropList
- CMFCColorBar [MFC], ShowCommandMessageString
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2083c26943768afff4b3b20a2ba95c709648dd50
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccolorbar-class"></a>Класс CMFCColorBar
`CMFCColorBar` Класс представляет закрепляемую панель элементов управления, которая может выбирать цвета в документ или приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Создает объект `CMFCColorBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](#contexttosize)|Вычисляет вертикальное и горизонтальное рамки, которые требуются для размещения кнопок на цветовой панели управления и затем изменяет положение эти кнопки.|  
|[CMFCColorBar::CreateControl](#createcontrol)|Создает окно управления цветовую шкалу, присоединяется к `CMFCColorBar` объекта и изменяет элемент управления, содержащий указанный палитры цветов.|  
|[CMFCColorBar::Create](#create)|Создает окно управления цветовую шкалу и прикрепляет его к `CMFCColorBar` объекта.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Показывает или скрывает кнопку «автоматический».|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Включает или отключает отображение диалогового окна, позволяющий пользователю выбрать другие цвета.|  
|[CMFCColorBar::GetColor](#getcolor)|Получает текущий выбранный цвет.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|Возвращает идентификатор текущего элемента управления цветовой шкалы.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Получает цвет, который означает, что кнопка цвета имеет фокус; кнопка является *горячей*.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Возвращает горизонтальное поле — это пространство между влево или вправо цвет ячейки и границы области клиента.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Получает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейке цвет и границы области клиента.|  
|[CMFCColorBar::IsTearOff](#istearoff)|Указывает, является ли текущий цветовую шкалу фиксируемого.|  
|[CMFCColorBar::SetColor](#setcolor)|Задает цвет выбранного в данный момент.|  
|[CMFCColorBar::SetColorName](#setcolorname)|Задает новое имя для выбранного цвета.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|Задает новый идентификатор команды для элемента управления на цветовой шкале.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Задает список цветов, используемых в текущем документе.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Задает горизонтальное поле — это пространство между влево или вправо цвет ячейки и границы области клиента.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Задает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейки цвет и границы области клиента.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Регулирует положение кнопки цветов на цветовой панели управления.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Указывает, можно ли изменить текстовую подпись цвет кнопок.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Указывает ли объект цветовой панели управления может отображаться в списке панелей во время процесса настройки.|  
|[CMFCColorBar::CalcSize](#calcsize)|Вызывается платформой как часть процесса вычисления макета.|  
|[CMFCColorBar::CreatePalette](#createpalette)|Инициализирует цветами в указанный массив цветов палитры.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Вычисляет количество строк и столбцов в сетке управления цветовой шкалы.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Вычисляет дополнительных высоту, текущий цветовую шкалу для отображения прочие элементы интерфейса, такие как **других** кнопку цвета документа и т. д.|  
|[CMFCColorBar::InitColors](#initcolors)|Инициализирует массив цветов с цветами в указанный палитры или системной палитры по умолчанию.|  
|[CMFCColorBar::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает клавишу клавиатуры.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Вызывается платформой для закрытия иерархию элементов управления всплывающее окно.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывается платформой для включения или отключения элемент пользовательского интерфейса элемента управления цветовую шкалу до отображения элемента.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Откроется диалоговое окно «цвет».|  
|[CMFCColorBar::Rebuild](#rebuild)|Полностью перерисовывает цветовой панели управления.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|Задает логическую палитру для заданного контекста устройств палитры кнопки родительского элемента цветовой шкалы.|  
|[CMFCColorBar::SetPropList](#setproplist)|Наборы `m_pWndPropList` защищенный элемент данных в заданный указатель в сетке свойств.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Запрашивает фрейм окна, которому принадлежит управления цветовую шкалу для обновления строки сообщения в строке состояния.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|`m_bInternal`|Логическое поле, которое определяет, обрабатываются ли события мыши. Обычно события мыши обрабатываются, если это поле является `TRUE` и режим настройки `FALSE`.|  
|`m_bIsEnabled`|Логическое значение, указывающее, включен ли элемент управления.|  
|`m_bIsTearOff`|Значение Boolean, указывающее, поддерживает ли элемент управления цветовую шкалу закрепления.|  
|`m_BoxSize`|Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта, указывающее размер ячейки в сетке цветовой шкалы.|  
|`m_bShowDocColorsWhenDocked`|Логическое значение, указывающее, следует ли отображать цвета документа при присоединении цветовой шкалы. Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_bStdColorDlg`|Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorAutomatic`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , в которых хранятся текущий цвет автоматической. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorNames`|[CMap](../../mfc/reference/cmap-class.md) объект, который связывает набор RGB цветов с их именами.|  
|`m_colors`|Объект [CArray](../../mfc/reference/carray-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения, которые содержит цвета, отображаемые в элементе управления цветовой шкалы.|  
|`m_ColorSelected`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее цвет, который в данный момент пользователь выбрал из цветовой панели управления.|  
|`m_lstDocColors`|Объект [CList](../../mfc/reference/clist-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения, которые содержит цвета, которые в настоящее время используются в документе.|  
|`m_nCommandID`|Целое число без знака, являющееся Идентификатором команды цвет кнопки.|  
|`m_nHorzMargin`|Целое число, поля по горизонтали между кнопками цвет в сетке цветов.|  
|`m_nHorzOffset`|Целое число, является горизонтальное смещение относительно центральной части кнопку цвета. Это значение имеет значение, если на кнопке отображается текст или изображение в дополнение к цвет.|  
|`m_nNumColumns`|Целое число, представляющее количество столбцов в сетке управления цветовой шкалы цветов.|  
|`m_nNumColumnsVert`|Целое число, представляющее количество столбцов в сетке вертикально цветов.|  
|`m_nNumRowsHorz`|Целое число, представляющее количество столбцов в сетке горизонтальный цветов.|  
|`m_nRowHeight`|Целое число, имеет высоту строки цвет кнопок в сетке цветов.|  
|`m_nVertMargin`|Целое число, вертикальное поле между кнопками цвет в сетке цветов.|  
|`m_nVertOffset`|Целое число, вертикальное смещение относительно центральной части кнопку цвета. Это значение имеет значение, если на кнопке отображается текст или изображение в дополнение к цвет.|  
|`m_Palette`|Объект [CPalette](../../mfc/reference/cpalette-class.md) цветов, используемых в цветовой панели управления.|  
|`m_pParentBtn`|Указатель на [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) объект, являющийся родительским для текущего кнопки. Это значение имеет значение, если «цвет» в иерархии элементов управления панели инструментов или в сетке свойств цвета.|  
|`m_pParentRibbonBtn`|Указатель на [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) объект и кнопка «родительский» текущей кнопки на ленте. Это значение имеет значение, если «цвет» в иерархии элементов управления панели инструментов или в сетке свойств цвета.|  
|`m_pWndPropList`|Указатель на [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) объекта.|  
|`m_strAutoColor`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , определяющее текст, отображаемый на **автоматического** кнопки. Дополнительные сведения см. в разделе [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|  
|`m_strDocColors`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , определяющее текст, отображаемый на кнопке цветов документа. Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_strOtherColor`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , определяющее текст, отображаемый на *других* кнопки. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
  
## <a name="remarks"></a>Примечания  
 Как правило, не следует создавать `CMFCColorBar` объекта напрямую. Вместо этого [класса CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) (используется в меню и панелей инструментов) или [класса CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) создает `CMFCColorBar` объекта.  
  
 `CMFCColorBar` Класс предоставляет следующие функциональные возможности:  
  
-   Автоматически настраивает список цветов документа.  
  
-   Сохраняет и восстанавливает его состояние, а также состояние документа.  
  
-   Управляет кнопки «automatic».  
  
-   Использует [класса для CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md) управления, чтобы выбрать другой цвет.  
  
-   Поддерживает состояние «перемещаемые» (если она создана с помощью [CMFCColorMenuButton класса](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 Для включения `CMFCColorBar` функциональности в приложение:  
  
1.  Создание кнопки обычное меню и ему присваивается идентификатор, например ID_CHAR_COLOR.  
  
2.  В классе фрейма окна переопределить [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) метод и замены обычное меню кнопки с [класса CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) объекта (путем вызова [CMFCToolBar: : ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  Задать все стили и включить или отключить возможности `CMFCColorBar` объекта во время [CMFCColorMenuButton класса](../../mfc/reference/cmfccolormenubutton-class.md) создания. `CMFCColorMenuButton` Динамически создает объект `CMFCColorBar` объекта после платформа вызывает `CreatePopupMenu` метод.  
  
 Когда пользователь нажимает кнопку управления цветовую шкалу, платформа использует `ON_COMMAND` макрос для уведомления родительского элемента управления цветовой шкалы. В макросе параметр ID команды имеет значение, присвоенное кнопки управления цветовую шкалу на шаге 1 (ID_CHAR_COLOR в этом примере). Дополнительные сведения см. в разделе [класса CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md), [класса CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md), [класса для CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx класса](../../mfc/reference/cframewndex-class.md), и [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md) классы.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить цветовую шкалу с помощью различных методов в `CMFCColorBar` класса. Методы задания полей горизонтальные и вертикальные, включить другие кнопки, создать окно управления цветовую шкалу и задает выбранный цвет. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolorbar.h  
  
##  <a name="adjustlocations"></a>  CMFCColorBar::AdjustLocations  
 Регулирует положение кнопки цветов на цветовой панели управления.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается средой во время `WM_SIZE` обработки сообщений.  
  
##  <a name="allowchangetextlabels"></a>  CMFCColorBar::AllowChangeTextLabels  
 Указывает, можно ли изменить текстовую подпись цвет кнопок.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `FALSE`, что означает текстовые метки не может изменяться. Переопределите этот метод, чтобы включить изменение текстовых меток.  
  
##  <a name="allowshowonlist"></a>  CMFCColorBar::AllowShowOnList  
 Указывает ли объект цветовой панели управления может отображаться в списке панелей во время процесса настройки.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `TRUE`, означающее платформу можно отобразить в процессе настройки цветовой панели управления. Переопределите этот метод, чтобы реализовать другое поведение.  
  
##  <a name="calcsize"></a>  CMFCColorBar::CalcSize  
 Вызывается платформой как часть процесса вычисления макета.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bVertDock`  
 `TRUE` Чтобы указать, цветовая панель управления закреплены по вертикали; `FALSE` для указания, что управления цветовая панель закреплена горизонтально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер массива цвет кнопок в элементе управления цветовой шкалы.  
  
##  <a name="cmfccolorbar"></a>  CMFCColorBar::CMFCColorBar  
 Создает объект `CMFCColorBar`.  
  
```  
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    int nRowsDockHorz,  
    int nColDockVert,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCColorButton* pParentBtn);

 
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCRibbonColorButton* pParentRibbonBtn);

 
CMFCColorBar(
    CMFCColorBar& src,  
    UINT uiCommandID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `colors`  
 Массив цветов, отображаемых на цветовой панели управления структурой.  
  
 [in] `color`  
 Изначально выбранного цвета.  
  
 [in] `lpszAutoColor`  
 Текстовая метка *автоматического* кнопку цвета (по умолчанию), или `NULL`.  
  
 Стандартная метки для кнопки автоматического **автоматического**.  
  
 [in] `lpszOtherColor`  
 Текстовая метка *других* кнопку, которая отображает дополнительные параметры цветов, или `NULL`.  
  
 Метки стандартной кнопки выбора другого **Дополнительные цвета...** .  
  
 [in] `lpszDocColors`  
 Текстовая подпись кнопки цветов документа. Палитра цветов документа перечислены все цвета, которые в настоящее время используются.  
  
 [in] `lstDocColors`  
 Список цветов, которые в настоящее время используются.  
  
 [in] `nColumns`  
 Число столбцов, которые содержит массив цветов.  
  
 [in] `nRowsDockHorz`  
 Число строк, которые имеет цветовую шкалу, если она закреплена горизонтально.  
  
 [in] `nColDockVert`  
 Число столбцов, которые цветовую шкалу при его закреплены по вертикали.  
  
 [in] `colorAutomatic`  
 Цвет по умолчанию платформа применяется при нажатии кнопки «автоматический».  
  
 [in] `nCommandID`  
 ИД команды управления цветовой шкалы.  
  
 [in] `pParentBtn`  
 Указатель на кнопку родительского.  
  
 [in] `src`  
 Существующий `CMFCColorBar` скопировать в новый объект `CMFCColorBar` объекта.  
  
 [in] `uiCommandID`  
 Идентификатор команды.  
  
##  <a name="contexttosize"></a>  CMFCColorBar::ContextToSize  
 Вычисляет вертикальное и горизонтальное поля, должны содержать кнопки на цветовой панели управления, которые изменяет положение эти кнопки.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `bSquareButtons`|`TRUE` Чтобы указать квадратными; форму кнопок в элементе управления цветовой шкалы в противном случае `FALSE`. Значение по умолчанию — `TRUE`.|  
|[in] `bCenterButtons`|`TRUE` Чтобы указать, что содержимое на лицевой стороне кнопки управления цветовую шкалу выравнивается по центру; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.|  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>  CMFCColorBar::Create  
 Создает окно управления цветовую шкалу и прикрепляет его к `CMFCColorBar` объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle,  
    UINT nID,  
    CPalette* pPalette=NULL,  
    int nColumns=0,  
    int nRowsDockHorz=0,  
    int nColDockVert=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указатель на родительское окно.  
  
 [in] `dwStyle`  
 Побитовое сочетание (OR) [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `nID`  
 Идентификатор команды.  
  
 [in] `pPalette`  
 Указатель на палитру цветов. Значение по умолчанию — `NULL`.  
  
 [in] `nColumns`  
 Число столбцов в элементе управления цветовой шкалы. Значение по умолчанию — 0.  
  
 [in] `nRowsDockHorz`  
 Число строк в элементе управления цветовую шкалу, когда она закреплена горизонтально. Значение по умолчанию — 0.  
  
 [in] `nColDockVert`  
 Число столбцов в элементе управления цветовую шкалу, когда она закреплена по вертикали. Значение по умолчанию — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для создания `CMFCColorBar` объекта, вызовите конструктор класса, а затем этот метод. `Create` Метод создает элемент управления Windows и инициализирует список цветов.  
  
##  <a name="createcontrol"></a>  CMFCColorBar::CreateControl  
 Создает окно управления цветовую шкалу, присоединяется к `CMFCColorBar` объекта и размера окна элемента управления для хранения указанного палитры цветов.  
  
```  
virtual BOOL CreateControl(
    CWnd* pParentWnd,  
    const CRect& rect,  
    UINT nID,  
    int nColumns=-1,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указатель на родительское окно. Не может быть `NULL`.  
  
 [in] `rect`  
 Ограничивающий прямоугольник, указывающий, куда цветовой панели элемента управления.  
  
 [in] `nID`  
 Идентификатор элемента управления.  
  
 [in] `nColumns`  
 Оптимальное количество столбцов в элементе управления цветовой шкалы. Этот метод изменяет эти номера в соответствии с указанным палитры цветов. Значение по умолчанию — -1, это означает, что этот параметр не указан.  
  
 [in] `pPalette`  
 Указатель на палитру цветов, или `NULL`. Если этот параметр равен `NULL`, этот метод вычисляет размер элемента управления цветовую шкалу, как при указанном 20 цветов. Значение по умолчанию — `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `rect`, `nColumns`, и `pPalette` параметров для вычисления соответствующего количества или строки и столбцы в цветовой панели управления, а затем вызывает [CMFCColorBar::Create](#create) метод.  
  
##  <a name="createpalette"></a>  CMFCColorBar::CreatePalette  
 Инициализирует цветами в указанный массив цветов палитры.  
  
```  
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,   
    CPalette& palette);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `arColors`|Массив цветов.|  
|[in] `palette`|Палитры цветов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorBar::EnableAutomaticButton  
 Показывает или скрывает кнопку «автоматический».  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Текстовая метка *автоматического* кнопку цвета (по умолчанию), или `NULL`.  
  
 Стандартная метки для кнопки автоматического **автоматического**.  
  
 [in] `colorAutomatic`  
 Цвет по умолчанию платформа применяется при нажатии кнопки «автоматический».  
  
 [in] `bEnable`  
 `TRUE` Чтобы включить автоматическое кнопки. `FALSE` отключение автоматической кнопки. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Текстовая метка автоматической кнопки удаляется, если `lpszLabel` параметр `NULL` или `bEnable` параметр `FALSE`.  
  
##  <a name="enableotherbutton"></a>  CMFCColorBar::EnableOtherButton  
 Включает или отключает отображение диалогового окна, позволяющий пользователю выбрать другие цвета.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Текстовая метка *других* кнопку, которая отображает дополнительные параметры цветов, или `NULL`.  
  
 Стандартная подпись эта кнопка является **Дополнительные цвета...** .  
  
 [in] `bAltColorDlg`  
 `TRUE` для отображения [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговым окном. `FALSE` для отображения стандартного [CColorDialog](../../mfc/reference/ccolordialog-class.md) диалоговое окно. Значение по умолчанию — `TRUE`.  
  
 [in] `bEnable`  
 `TRUE` для включения кнопки. `FALSE` для выключения кнопки. Значение по умолчанию — `TRUE`.  
  
##  <a name="getcolor"></a>  CMFCColorBar::GetColor  
 Получает текущий выбранный цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выбранный цвет.  
  
##  <a name="getcolorgridsize"></a>  CMFCColorBar::GetColorGridSize  
 Вычисляет количество строк и столбцов в сетке управления цветовой шкалы.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `bVertDock`|`TRUE` для выполнения вычисления для элемента управления по вертикали закрепленной цветовую шкалу; в противном случае выполните вычисления для горизонтально закрепленного элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) которого `cx` компонент содержит число столбцов, для которых `cy` компонент содержит количество строк.  
  
##  <a name="getcommandid"></a>  CMFCColorBar::GetCommandID  
 Возвращает идентификатор текущего элемента управления цветовой шкалы.  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает новый цвет, платформа отправляет идентификатор команды в `WM_COMMAND` сообщения для уведомления родительского элемента `CMFCColorBar` объекта.  
  
##  <a name="getextraheight"></a>  CMFCColorBar::GetExtraHeight  
 Вычисляет дополнительных высоту, текущий цветовую шкалу для отображения элементов прочие пользовательского интерфейса, такие как **других** цвета кнопки или документа.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nNumColumns`|Если в элементе управления цветовой полосы цвета документа, число столбцов для отображения в сетке цвета документа. В противном случае это значение не используется.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вычисленную ширину дополнительный, не требуется.  
  
##  <a name="gethighlightedcolor"></a>  CMFCColorBar::GetHighlightedColor  
 Получает цвет, который означает, что кнопка цвета имеет фокус; кнопка является *горячей*.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethorzmargin"></a>  CMFCColorBar::GetHorzMargin  
 Возвращает горизонтальное поле — это пространство между влево или вправо цвет ячейки и границы области клиента.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поля по горизонтали.  
  
##  <a name="getvertmargin"></a>  CMFCColorBar::GetVertMargin  
 Получает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейке цвет и границы области клиента.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальная поле.  
  
##  <a name="initcolors"></a>  CMFCColorBar::InitColors  
 Инициализирует массив цветов цветов в палитре указанного или с системной палитры по умолчанию.  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pPalette`|Указатель на объект палитры или `NULL`. Если этот параметр равен `NULL`, этот метод использует палитра по умолчанию операционной системы.|  
|[in] `arColors`|Массив цветов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в массиве цветов.  
  
##  <a name="istearoff"></a>  CMFCColorBar::IsTearOff  
 Указывает, является ли текущий цветовую шкалу фиксируемого.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если текущий элемент управления цветовую шкалу фиксируемого; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если фиксируемый элемент управления цветовую шкалу, его можно обрыва отключение панели элементов управления и закрепления в другом месте.  
  
##  <a name="onkey"></a>  CMFCColorBar::OnKey  
 Вызывается платформой, когда пользователь нажимает клавишу клавиатуры.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nChar`  
 Виртуальная клавиша код для ключа, который пользователь нажал клавиши.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод обрабатывает заданный ключ. в противном случае `FALSE`.  
  
##  <a name="onsendcommand"></a>  CMFCColorBar::OnSendCommand  
 Вызывается платформой для закрытия иерархию всплывающих элементов управления.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pButton`|Указатель на элемент управления, который находится на панели инструментов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
##  <a name="onupdatecmdui"></a>  CMFCColorBar::OnUpdateCmdUI  
 Вызывается платформой для включения или отключения элемент пользовательского интерфейса элемента управления цветовую шкалу до отображения элемента.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTarget`  
 Указатель на окно, содержащее элемент пользовательского интерфейса, чтобы обновить.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE` отключение элемента пользовательского интерфейса, если обработчик не определен в схеме сообщений; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По щелчку элемента пользовательского интерфейса пользователя приложения элемента необходимо знать ли он должен отображаться как включена или отключена. Цель сообщения команда поддерживает эти сведения путем реализации `ON_UPDATE_COMMAND_UI` обработчика команд. Используйте этот метод для обработки команды. Дополнительные сведения см. в разделе [CCmdUI-класс](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="opencolordialog"></a>  CMFCColorBar::OpenColorDialog  
 Откроется диалоговое окно «цвет».  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `colorDefault`  
 Цвет, который выбран по умолчанию при открытии диалогового окна цвет.  
  
 [выходной] `colorRes`  
 Цвет выбранного пользователя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если пользователь выбрал цвета; `FALSE` Если пользователь отменил диалоговое окно «цвет».  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="rebuild"></a>  CMFCColorBar::Rebuild  
 Полностью перерисовывает цветовой панели управления.  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>  CMFCColorBar::SelectPalette  
 Задает логическую палитру для заданного контекста устройств палитры кнопки родительского элемента цветовой шкалы.  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pDC`|Указатель на контекст устройства кнопки родительского элемента цветовой шкалы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на палитру, которая заменяется палитры кнопки родительского элемента цветовой шкалы.  
  
##  <a name="setcolor"></a>  CMFCColorBar::SetColor  
 Задает цвет выбранного в данный момент.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Значение цвета RGB.  
  
##  <a name="setcolorname"></a>  CMFCColorBar::SetColorName  
 Задает новое имя для выбранного цвета.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 RGB-значение цвета.  
  
 [in] `strName`  
 Новое имя для указанного цвета.  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет имя указанного цвета во всех `CMFCColorBar` объектов в приложении.  
  
##  <a name="setcommandid"></a>  CMFCColorBar::SetCommandID  
 Задает новый идентификатор команды для элемента управления на цветовой шкале.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandID`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы изменить идентификатор команды управления цветовую шкалу и известить родительского окна элемента управления, который изменился идентификатор.  
  
##  <a name="setdocumentcolors"></a>  CMFCColorBar::SetDocumentColors  
 Задает список цветов, используемых в текущем документе.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszCaption`  
 Заголовок, отображаемый при цветовой панели управления не закреплен.  
  
 [in] `lstDocColors`  
 Список цветов, который заменяет цвета текущего документа.  
  
 [in] `bShowWhenDocked`  
 `TRUE` для отображения цвета документа при присоединении цветовой панели управления; в противном случае `FALSE`. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 *Документирование цвета* цветов, которые в настоящее время используются в документе. Платформа автоматически сохраняет список цветов документа, но этот метод можно использовать для изменения списка.  
  
##  <a name="sethorzmargin"></a>  CMFCColorBar::SetHorzMargin  
 Задает горизонтальное поле — это пространство между влево или вправо цвет ячейки и границы клиентской области.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHorzMargin`  
 Поля по горизонтали, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию [CMFCColorBar::CMFCColorBar](#cmfccolorbar) конструктор задает горизонтальное поле до 4 пикселей.  
  
##  <a name="setproplist"></a>  CMFCColorBar::SetPropList  
 Наборы `m_pWndPropList` защищенный элемент данных в заданный указатель в сетке свойств.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pWndList`|Указатель на объект элемента управления сетки свойств.|  
  
##  <a name="setvertmargin"></a>  CMFCColorBar::SetVertMargin  
 Задает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейки цвет и границы области клиента.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nVertMargin`  
 Вертикальная поле в пикселях.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию [CMFCColorBar::CMFCColorBar](#cmfccolorbar) конструктор задает вертикальное поле для 4 пикселя.  
  
##  <a name="showcommandmessagestring"></a>  CMFCColorBar::ShowCommandMessageString  
 Запрашивает фрейм окна, которому принадлежит управления цветовую шкалу для обновления строки сообщения в строке состояния.  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатор команды. (Этот параметр учитывается).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет `WM_SETMESSAGESTRING` сообщение, владельцу элемента управления цветовой шкалы.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
