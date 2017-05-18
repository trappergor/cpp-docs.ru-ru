---
title: "Класс CMFCColorBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCColorBar class
- CMFCColorBar::m_ColorAutomatic data member
- CMFCColorBar::m_bInternal data member
- CMFCColorBar::m_bIsEnabled data member
- CMFCColorBar::m_nNumColumnsVert data member
- CMFCColorBar::m_nVertMargin data member
- CMFCColorBar::m_strDocColors data member
- CMFCColorBar::m_BoxSize data member
- CMFCColorBar::m_pParentBtn data member
- CMFCColorBar::m_bIsTearOff data member
- CMFCColorBar::m_nHorzOffset data member
- CMFCColorBar::m_pParentRibbonBtn data member
- CMFCColorBar::m_nNumRowsHorz data member
- CMFCColorBar::m_bStdColorDlg data member
- CMFCColorBar::m_strAutoColor data member
- CMFCColorBar::m_ColorNames data member
- CMFCColorBar::m_strOtherColor data member
- CMFCColorBar::m_lstDocColors data member
- CMFCColorBar::m_pWndPropList data member
- CMFCColorBar::m_ColorSelected data member
- CMFCColorBar::m_nCommandID data member
- CMFCColorBar::m_nHorzMargin data member
- CMFCColorBar::m_nRowHeight data member
- CMFCColorBar::m_Palette data member
- CMFCColorBar::m_colors data member
- CMFCColorBar::m_nVertOffset data member
- CMFCColorBar::m_nNumColumns data member
- CMFCColorBar::m_bShowDocColorsWhenDocked data member
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: bf4d431a3f3237587dc9f86be91f11b9b5016fe2
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbar-class"></a>Класс CMFCColorBar
`CMFCColorBar` Класс представляет закрепления панели элементов управления, которая может выбирать цвета в документе или приложении.  
  
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
|[CMFCColorBar::ContextToSize](#contexttosize)|Вычисляет вертикальное и горизонтальное поля, должны содержать кнопки в элемент управления цветовую шкалу и затем изменяет положение этих кнопок.|  
|[CMFCColorBar::CreateControl](#createcontrol)|Создает окно управления цветовую шкалу, присоединяется к `CMFCColorBar` объекта и изменяет элемент управления, содержащий указанный палитры цветов.|  
|[CMFCColorBar::Create](#create)|Создает окно управления цветовую шкалу и присоединяет его к `CMFCColorBar` объекта.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Показывает или скрывает кнопку автоматического.|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Включает или отключает отображение диалогового окна, позволяющий пользователю выбрать дополнительные цвета.|  
|[CMFCColorBar::GetColor](#getcolor)|Получает текущий выбранный цвет.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|Извлекает идентификатор команды текущий цвет элемента управления.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Получает цвет, который означает, что кнопка цвета имеет фокус; кнопка является *горячей*.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Возвращает горизонтальное поле представляет собой пространство между влево или вправо цвет ячейки и границы области клиента.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Возвращает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейке цвет и границы области клиента.|  
|[CMFCColorBar::IsTearOff](#istearoff)|Указывает, является ли текущий цветовую шкалу Закрепляемое.|  
|[CMFCColorBar::SetColor](#setcolor)|Задает цвет, который выбран в данный момент.|  
|[CMFCColorBar::SetColorName](#setcolorname)|Задает новое имя для выбранного цвета.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|Задает новый идентификатор команды для управления цветовой шкалы.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Задает список цветов, используемых в текущем документе.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Задает горизонтальное поле, которое представляет собой пространство между влево или вправо цвет ячейки и границы области клиента.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Задает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейке цвет и границы области клиента.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Регулирует положение кнопки цветов на цветовой шкале управления.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Указывает, можно ли изменить текстовую метку цветные кнопки.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Указывает ли объект управления цветовую шкалу может отображаться в списке панели инструментов в процессе настройки.|  
|[CMFCColorBar::CalcSize](#calcsize)|Вызывается средой в процессе вычисления макета.|  
|[CMFCColorBar::CreatePalette](#createpalette)|Инициализирует палитры цветов в указанном массиве цветов.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Вычисляет количество строк и столбцов в сетке управления цветовой шкалы.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Вычисляет дополнительных высоту, текущий цветовую шкалу для отображения прочие элементы интерфейса, такие как **других** кнопки, цвета документа и т. д.|  
|[CMFCColorBar::InitColors](#initcolors)|Инициализирует массив цветов с цветами в указанный палитру или палитре системы по умолчанию.|  
|[CMFCColorBar::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает клавишу клавиатуры.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Вызывается платформой для закрытия иерархию элементов управления всплывающее окно.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывается средой, чтобы включить или отключить элемент пользовательского интерфейса элемента управления цветовую шкалу, перед отображением элемента.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Откроется диалоговое окно.|  
|[CMFCColorBar::Rebuild](#rebuild)|Полностью перерисовывает цветовой панели управления.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|Задает логический палитры заданного контекста устройств палитре кнопку родительского элемента цветовую шкалу.|  
|[CMFCColorBar::SetPropList](#setproplist)|Наборы `m_pWndPropList` защищенный член данных в заданный указатель в сетке свойств.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Запрашивает фрейме окна, которому принадлежит управления цветовую шкалу для обновления строки сообщения в строке состояния.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|`m_bInternal`|Логическое поле, которое определяет, обрабатываются ли события мыши. Обычно обрабатываются события мыши, если это поле является `TRUE` и режим настройки `FALSE`.|  
|`m_bIsEnabled`|Логическое значение, указывающее, включен ли элемент управления.|  
|`m_bIsTearOff`|Логическое значение, указывающее, поддерживает ли элемент управления цветовую шкалу закрепления.|  
|`m_BoxSize`|Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта, указывающее размер ячейки в сетке цветовой шкалы.|  
|`m_bShowDocColorsWhenDocked`|Логическое значение, указывающее, следует ли отображать цвета документа при прикреплении цветовой шкалы. Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_bStdColorDlg`|Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorAutomatic`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , в котором хранится текущий автоматическое цвет. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorNames`|[CMap](../../mfc/reference/cmap-class.md) объект, который связывает набор RGB цветов с их именами.|  
|`m_colors`|Объект [CArray](../../mfc/reference/carray-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения, которые содержит цвета, отображаемые в элементе управления цветовой шкалы.|  
|`m_ColorSelected`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее цвет, который пользователь выбрал в данный момент в элементе управления цветовой шкалы.|  
|`m_lstDocColors`|Объект [CList](../../mfc/reference/clist-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения, которые содержит цвета, которые в настоящее время используются в документе.|  
|`m_nCommandID`|Целое число без знака, являющееся Идентификатором команды цвет кнопки.|  
|`m_nHorzMargin`|Целое число, поля по горизонтали между кнопками цвета в таблице цветов.|  
|`m_nHorzOffset`|Целое число, смещение по горизонтали относительно центральной части «цвет». Это значение имеет значение, если кнопка отображает текст или изображение, а также цвета.|  
|`m_nNumColumns`|Целое число, число столбцов в сетке управления цветовой шкалы цветов.|  
|`m_nNumColumnsVert`|Целое число, число столбцов в сетке вертикально цветов.|  
|`m_nNumRowsHorz`|Целое число, число столбцов в сетке горизонтальный цветов.|  
|`m_nRowHeight`|Целое число, имеет высоту строки цвет кнопок в сетке цветов.|  
|`m_nVertMargin`|Целое число, вертикальное поле между кнопками цвета в таблице цветов.|  
|`m_nVertOffset`|Целое число, смещение по вертикали относительно центральной части «цвет». Это значение имеет значение, если кнопка отображает текст или изображение, а также цвета.|  
|`m_Palette`|Объект [CPalette](../../mfc/reference/cpalette-class.md) цветов, которые используются при управлении цветовой шкалы.|  
|`m_pParentBtn`|Указатель на [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) объект, являющийся родительским для текущего кнопки. Это значение имеет значение, если в иерархии элементов управления панели инструментов «цвет» или в сетке свойств цвета.|  
|`m_pParentRibbonBtn`|Указатель на [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) объект и используется для родительского текущей кнопки на ленте. Это значение имеет значение, если в иерархии элементов управления панели инструментов «цвет» или в сетке свойств цвета.|  
|`m_pWndPropList`|Указатель на [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) объекта.|  
|`m_strAutoColor`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , определяющее текст, который отображается на **автоматического** кнопки. Дополнительные сведения см. в разделе [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|  
|`m_strDocColors`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , определяющее текст, отображаемый на кнопке цвета документа. Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_strOtherColor`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , определяющее текст, который отображается на *других* кнопки. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
  
## <a name="remarks"></a>Примечания  
 Как правило, не следует создавать `CMFCColorBar` напрямую. Вместо этого [класса CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) (используется в меню и панели инструментов) или [класса CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) создает `CMFCColorBar` объекта.  
  
 `CMFCColorBar` Класс предоставляет следующие функциональные возможности:  
  
-   Автоматически настраивает список цветов документа.  
  
-   Сохраняет и восстанавливает состояние, а также состояние документа.  
  
-   Управляет кнопки «автоматический».  
  
-   Использует [для CMFCColorPickerCtrl класса](../../mfc/reference/cmfccolorpickerctrl-class.md) управления, чтобы выбрать другой цвет.  
  
-   Поддерживает состояние «перемещаемое» (если она создается с помощью [CMFCColorMenuButton класса](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 Для включения `CMFCColorBar` функциональности в приложении:  
  
1.  Создание кнопки меню регулярных и ему присваивается идентификатор, например ID_CHAR_COLOR.  
  
2.  В классе фрейма окна переопределения [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) и замените регулярных меню кнопки [класса CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) объекта (путем вызова [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  Установка всех стилей и включение или отключение функции `CMFCColorBar` объекта во время [CMFCColorMenuButton класса](../../mfc/reference/cmfccolormenubutton-class.md) создания. `CMFCColorMenuButton` Динамически создает объект `CMFCColorBar` объекта после платформа вызывает функцию `CreatePopupMenu` метод.  
  
 Когда пользователь нажимает кнопку управления цветовую шкалу, инфраструктура использует `ON_COMMAND` макрос для уведомления родительского элемента управления цветовой шкалы. В макросе параметр идентификатор команды-значение, присвоенное кнопки управления цветовую шкалу на шаге 1 (ID_CHAR_COLOR в этом примере). Дополнительные сведения см. в разделе [класса CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md), [класса CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md), [класса для CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md), [класса CFrameWndEx](../../mfc/reference/cframewndex-class.md), и [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md) классы.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить цветовую шкалу, с помощью различных методов в `CMFCColorBar` класса. Методы задайте горизонтальное и вертикальное, включить другие кнопки, создать окно управления цветовую шкалу и задает выбранный цвет. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#1;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#2;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]  
  
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
  
##  <a name="adjustlocations"></a>CMFCColorBar::AdjustLocations  
 Регулирует положение кнопки цветов на цветовой шкале управления.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается средой во время `WM_SIZE` обработки сообщений.  
  
##  <a name="allowchangetextlabels"></a>CMFCColorBar::AllowChangeTextLabels  
 Указывает, можно ли изменить текстовую метку цветные кнопки.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `FALSE`, что означает текстовые метки не может быть изменен. Переопределите этот метод, чтобы включить изменение текстовых меток.  
  
##  <a name="allowshowonlist"></a>CMFCColorBar::AllowShowOnList  
 Указывает ли объект управления цветовую шкалу может отображаться в списке панели инструментов в процессе настройки.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `TRUE`, означающее платформы можно отобразить элемент управления цветовую шкалу в процессе настройки. Переопределите этот метод, чтобы реализовать другое поведение.  
  
##  <a name="calcsize"></a>CMFCColorBar::CalcSize  
 Вызывается средой в процессе вычисления макета.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bVertDock`  
 `TRUE`Чтобы указать, что управления цветовую шкалу расположенное; `FALSE` для указания цветов управления закреплена горизонтально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер массива цвет кнопок в элементе управления цветовой шкалы.  
  
##  <a name="cmfccolorbar"></a>CMFCColorBar::CMFCColorBar  
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
 Массив цветов, отображаемых на цветовой шкале управления структурой.  
  
 [in] `color`  
 Изначально выбранного цвета.  
  
 [in] `lpszAutoColor`  
 Текстовая метка *автоматического* кнопка цвета (по умолчанию), или `NULL`.  
  
 Стандартную метку для автоматического кнопки — **автоматическое**.  
  
 [in] `lpszOtherColor`  
 Текстовая метка *других* кнопку, которая отображает выбор цветов, или `NULL`.  
  
 Стандартная метки другие кнопки **Дополнительные цвета... **.  
  
 [in] `lpszDocColors`  
 Текстовая метка «цвета» документа. Палитра цветов документа перечислены все цвета, которые в настоящее время использует документ.  
  
 [in] `lstDocColors`  
 Список цветов, которые в настоящее время используются.  
  
 [in] `nColumns`  
 Число столбцов, которые содержит массив цветов.  
  
 [in] `nRowsDockHorz`  
 Число строк, которые цветовую шкалу при закреплена горизонтально.  
  
 [in] `nColDockVert`  
 Число столбцов, которые цветовую шкалу при закреплена вертикально.  
  
 [in] `colorAutomatic`  
 Цвет по умолчанию платформа применяется при нажатии кнопки «автоматический».  
  
 [in] `nCommandID`  
 Идентификатор команды управления цветовой шкалы.  
  
 [in] `pParentBtn`  
 Указатель на родительский кнопки.  
  
 [in] `src`  
 Существующий `CMFCColorBar` скопировать в новый объект `CMFCColorBar` объект.  
  
 [in] `uiCommandID`  
 Идентификатор команды.  
  
##  <a name="contexttosize"></a>CMFCColorBar::ContextToSize  
 Вычисляет вертикальное и горизонтальное поля, необходимые для размещения кнопок на цветовой шкале управления и корректирует положение этих кнопок.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `bSquareButtons`|`TRUE`Чтобы задать квадрат; фигуры кнопки в элемент управления цветовой шкалы в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.|  
|[in] `bCenterButtons`|`TRUE`Чтобы указать, что содержимое на поверхности нажимаемой кнопки управления цветовую шкалу выравнивается по центру; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.|  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>CMFCColorBar::Create  
 Создает окно управления цветовую шкалу и присоединяет его к `CMFCColorBar` объекта.  
  
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
 Побитовое сочетание (или) [стили окна](../../mfc/reference/window-styles.md).  
  
 [in] `nID`  
 Идентификатор команды.  
  
 [in] `pPalette`  
 Указатель на палитру цветов. Значение по умолчанию — `NULL`.  
  
 [in] `nColumns`  
 Число столбцов в элементе управления цветовой шкалы. Значение по умолчанию — 0.  
  
 [in] `nRowsDockHorz`  
 Число строк в элементе управления цветовую шкалу, когда она закреплена горизонтально. Значение по умолчанию — 0.  
  
 [in] `nColDockVert`  
 Число столбцов в элементе управления цветовую шкалу, когда она закреплена вертикально. Значение по умолчанию — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для создания `CMFCColorBar` объекта, вызовите конструктор класса, а затем этот метод. `Create` Метод создает элемент управления Windows и инициализирует список цветов.  
  
##  <a name="createcontrol"></a>CMFCColorBar::CreateControl  
 Создает окно управления цветовую шкалу, присоединяется к `CMFCColorBar` объекта и изменяет размер окна элемента управления, содержащий указанный палитры цветов.  
  
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
 Ограничивающий прямоугольник, указывающий, куда нарисуйте элемент управления цветовой шкалы.  
  
 [in] `nID`  
 Идентификатор элемента управления.  
  
 [in] `nColumns`  
 Оптимальное количество столбцов в элементе управления цветовой шкалы. Этот метод изменяет это число в соответствии с указанным палитры цветов. Значение по умолчанию — -1, это означает, что этот параметр не указан.  
  
 [in] `pPalette`  
 Указатель на палитру цветов, или `NULL`. Если этот параметр равен `NULL`, этот метод вычисляет размер элемента управления цветовую шкалу, как при указанном 20 цветов. Значение по умолчанию — `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `rect`, `nColumns`, и `pPalette` параметры для расчета соответствующий номер или строки и столбцы в цветовой шкале управления, а затем вызывает [CMFCColorBar::Create](#create) метод.  
  
##  <a name="createpalette"></a>CMFCColorBar::CreatePalette  
 Инициализирует палитры цветов в указанном массиве цветов.  
  
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
 `TRUE`Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
##  <a name="enableautomaticbutton"></a>CMFCColorBar::EnableAutomaticButton  
 Показывает или скрывает кнопку автоматического.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Текстовая метка *автоматического* кнопка цвета (по умолчанию), или `NULL`.  
  
 Стандартную метку для автоматического кнопки — **автоматическое**.  
  
 [in] `colorAutomatic`  
 Цвет по умолчанию платформа применяется при нажатии кнопки «автоматический».  
  
 [in] `bEnable`  
 `TRUE`Чтобы включить автоматическое кнопки. `FALSE` для отключения автоматического кнопки. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Текстовая метка кнопки автоматического удаляется, если `lpszLabel` параметр `NULL` или `bEnable` параметр `FALSE`.  
  
##  <a name="enableotherbutton"></a>CMFCColorBar::EnableOtherButton  
 Включает или отключает отображение диалогового окна, позволяющий пользователю выбрать дополнительные цвета.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Текстовая метка *других* кнопку, которая отображает выбор цветов, или `NULL`.  
  
 Имеет стандартную метку для этой кнопки **Дополнительные цвета... **.  
  
 [in] `bAltColorDlg`  
 `TRUE`для отображения [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговым окном. `FALSE` для отображения стандартного [CColorDialog](../../mfc/reference/ccolordialog-class.md) диалоговое окно. Значение по умолчанию — `TRUE`.  
  
 [in] `bEnable`  
 `TRUE`для включения кнопки. `FALSE` для выключения кнопки. Значение по умолчанию — `TRUE`.  
  
##  <a name="getcolor"></a>CMFCColorBar::GetColor  
 Получает текущий выбранный цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выбранный цвет.  
  
##  <a name="getcolorgridsize"></a>CMFCColorBar::GetColorGridSize  
 Вычисляет количество строк и столбцов в сетке управления цветовой шкалы.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `bVertDock`|`TRUE`для выполнения вычисления для элемента управления по вертикали закрепленной цветовую шкалу; в противном случае — выполните вычисления для горизонтально закрепления элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) которого `cx` компонент содержит количество столбцов, для которых `cy` компонент содержит количество строк.  
  
##  <a name="getcommandid"></a>CMFCColorBar::GetCommandID  
 Извлекает идентификатор команды текущий цвет элемента управления.  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает новый цвет, платформа отправляет идентификатор команды в `WM_COMMAND` сообщения для уведомления родительский `CMFCColorBar` объекта.  
  
##  <a name="getextraheight"></a>CMFCColorBar::GetExtraHeight  
 Вычисляет дополнительных высоту, текущий цветовую шкалу для отображения элементов прочие пользовательского интерфейса, такие как **других** цвета кнопки или документа.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nNumColumns`|Если в элементе управления цветовой шкалы цвета документа, число столбцов для отображения в сетке цвета документа. В противном случае это значение не используется.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вычисляемые дополнительных высоту, является обязательным.  
  
##  <a name="gethighlightedcolor"></a>CMFCColorBar::GetHighlightedColor  
 Получает цвет, который означает, что кнопка цвета имеет фокус; кнопка является *горячей*.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethorzmargin"></a>CMFCColorBar::GetHorzMargin  
 Возвращает горизонтальное поле представляет собой пространство между влево или вправо цвет ячейки и границы области клиента.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поля по горизонтали.  
  
##  <a name="getvertmargin"></a>CMFCColorBar::GetVertMargin  
 Возвращает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейке цвет и границы области клиента.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальное поле.  
  
##  <a name="initcolors"></a>CMFCColorBar::InitColors  
 Инициализирует массив цветов, цвета в палитру указанного или с палитре системы по умолчанию.  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pPalette`|Указатель на объект палитру или `NULL`. Если этот параметр равен `NULL`, этот метод использует палитра по умолчанию операционной системы.|  
|[in] `arColors`|Массив цветов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в массиве цветов.  
  
##  <a name="istearoff"></a>CMFCColorBar::IsTearOff  
 Указывает, является ли текущий цветовую шкалу Закрепляемое.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если текущий элемент управления цветовую шкалу фиксируемого; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если фиксируемый элемент управления цветовую шкалу, его можно обрыва выключить панель элементов управления и закреплено в другом месте.  
  
##  <a name="onkey"></a>CMFCColorBar::OnKey  
 Вызывается платформой, когда пользователь нажимает клавишу клавиатуры.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nChar`  
 Виртуальный код для ключа, нажал пользователь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод обрабатывает заданный ключ. в противном случае — `FALSE`.  
  
##  <a name="onsendcommand"></a>CMFCColorBar::OnSendCommand  
 Вызывается средой, чтобы закрывать всплывающие элементы иерархии.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pButton`|Указатель на элемент управления, который находится на панели инструментов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
##  <a name="onupdatecmdui"></a>CMFCColorBar::OnUpdateCmdUI  
 Вызывается средой, чтобы включить или отключить элемент пользовательского интерфейса элемента управления цветовую шкалу, перед отображением элемента.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTarget`  
 Указатель на окно, содержащее элемент пользовательского интерфейса, чтобы обновить.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE`отключение элемента пользовательского интерфейса, если обработчик не определен в схеме сообщений; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По щелчку элемента пользовательского интерфейса пользователя приложения элемента необходимо знать ли он должен отображаться как включен или отключен. Цель сообщения команда предоставляет эти сведения при реализации `ON_UPDATE_COMMAND_UI` обработчик команды. Используйте этот метод для обработки команды. Дополнительные сведения см. в разделе [CCmdUI-класс](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="opencolordialog"></a>CMFCColorBar::OpenColorDialog  
 Откроется диалоговое окно.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `colorDefault`  
 Цвет, который выбран по умолчанию в открывшемся диалоговом окне цветов.  
  
 [выходной] `colorRes`  
 Цвет, выбранный пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если пользователь выбрал цвета; `FALSE` Если пользователь отменил диалоговое окно цвет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="rebuild"></a>CMFCColorBar::Rebuild  
 Полностью перерисовывает цветовой панели управления.  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>CMFCColorBar::SelectPalette  
 Задает логический палитры заданного контекста устройств палитре кнопку родительского элемента цветовую шкалу.  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pDC`|Указатель на контекст устройства кнопки родительского элемента цветовой шкалы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на палитре, заменяемые палитре кнопку родительского элемента цветовой шкалы.  
  
##  <a name="setcolor"></a>CMFCColorBar::SetColor  
 Задает цвет, который выбран в данный момент.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Значение цвета RGB.  
  
##  <a name="setcolorname"></a>CMFCColorBar::SetColorName  
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
  
##  <a name="setcommandid"></a>CMFCColorBar::SetCommandID  
 Задает новый идентификатор команды для управления цветовой шкалы.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCommandID`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод для изменения идентификатор команды управления цветовую шкалу и уведомить родительского окна элемента управления, который был изменен идентификатор.  
  
##  <a name="setdocumentcolors"></a>CMFCColorBar::SetDocumentColors  
 Задает список цветов, используемых в текущем документе.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszCaption`  
 Заголовок, отображаемый, когда не присоединяется данный элемент управления цветовой шкалы.  
  
 [in] `lstDocColors`  
 Список цветов, который заменяет цвета текущего документа.  
  
 [in] `bShowWhenDocked`  
 `TRUE`Чтобы показать цвета документа при присоединении цвет панели управления; в противном случае — `FALSE`. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 *Цвета документа* цветов, которые в настоящее время используются в документе. Платформа framework автоматически поддерживает список цветов документа, но этот метод можно использовать для изменения списка.  
  
##  <a name="sethorzmargin"></a>CMFCColorBar::SetHorzMargin  
 Задает горизонтальное поле, которое представляет собой пространство между влево или вправо цвет ячейки и границы клиентской области.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHorzMargin`  
 Поля по горизонтали, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию [CMFCColorBar::CMFCColorBar](#cmfccolorbar) конструктор задает горизонтальное поле 4 пикселей.  
  
##  <a name="setproplist"></a>CMFCColorBar::SetPropList  
 Наборы `m_pWndPropList` защищенный член данных в заданный указатель в сетке свойств.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pWndList`|Указатель на объект элемента управления сетки свойств.|  
  
##  <a name="setvertmargin"></a>CMFCColorBar::SetVertMargin  
 Задает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейке цвет и границы области клиента.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nVertMargin`  
 Вертикальное поле в пикселях.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию [CMFCColorBar::CMFCColorBar](#cmfccolorbar) конструктор задает вертикальное поле для 4 пикселей.  
  
##  <a name="showcommandmessagestring"></a>CMFCColorBar::ShowCommandMessageString  
 Запрашивает фрейме окна, которому принадлежит управления цветовую шкалу для обновления строки сообщения в строке состояния.  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатор команды. (Этот параметр учитывается).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет `WM_SETMESSAGESTRING` сообщение владельца элемента цветовой шкалы.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

