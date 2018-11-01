---
title: Класс CMFCColorBar
ms.date: 11/04/2016
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
ms.openlocfilehash: 6dc3044d1ca402ca099184eced2e5615ff161804
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636882"
---
# <a name="cmfccolorbar-class"></a>Класс CMFCColorBar

`CMFCColorBar` Класс представляет закрепляемую панель элементов управления, которая может выбирать цвета в документ или приложение.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Создает объект `CMFCColorBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorBar::ContextToSize](#contexttosize)|Вычисляет вертикального и горизонтального поля, должны содержать кнопки на цветовой панели управления и затем изменяет расположение этих кнопок.|
|[CMFCColorBar::CreateControl](#createcontrol)|Создает окно управления цветовой полосы, присоединяется к `CMFCColorBar` , а также изменяет размер элемента управления должен содержать указанный палитры цветов.|
|[CMFCColorBar::Create](#create)|Создает окно управления цветовую шкалу и присоединяет его к `CMFCColorBar` объекта.|
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Показывает или скрывает автоматической кнопки.|
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Включает или отключает отображение диалоговое окно, которое позволяет пользователю выбрать дополнительные цвета.|
|[CMFCColorBar::GetColor](#getcolor)|Извлекает выбранный цвет.|
|[CMFCColorBar::GetCommandID](#getcommandid)|Получает идентификатор команды текущего элемента управления цветовой полосы.|
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Получает цвет, который означает, что кнопка цвета имеет фокус; кнопка является *горячей*.|
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Извлекает горизонтального поля, которое представляет собой пространство между слева или ячейки правильный цвет и границы области клиента.|
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Получает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейки цвета и границы области клиента.|
|[CMFCColorBar::IsTearOff](#istearoff)|Указывает, является ли текущий цветовой полосы фиксируемого.|
|[CMFCColorBar::SetColor](#setcolor)|Задает цвет, который выбран в данный момент.|
|[CMFCColorBar::SetColorName](#setcolorname)|Задает новое имя для выбранного цвета.|
|[CMFCColorBar::SetCommandID](#setcommandid)|Задает новый идентификатор команды для элемента управления цветовой полосы.|
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Задает список цветов, используемых в текущем документе.|
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Задает горизонтальное поле, являющееся расстояние между левой или ячейки правильный цвет и границы области клиента.|
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Задает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейки цвета и границы области клиента.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Регулирует положение кнопки цветов на цветовой панели управления.|
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Указывает, можно ли изменить текстовую метку из кнопок цвет.|
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Указывает, может ли объект элемента управления цветовой полосы отображаться в списке панели инструментов во время процесса настройки.|
|[CMFCColorBar::CalcSize](#calcsize)|Вызвано структурой в ходе процесса вычисления макета.|
|[CMFCColorBar::CreatePalette](#createpalette)|Инициализирует палитры цветов в указанном массиве цветов.|
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Вычисляет количество строк и столбцов в сетке, цветовая панель элемента управления.|
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Вычисляет высоту дополнительных текущей цветовой полосы, необходимую для отображения прочие элементы интерфейса, такие как **других** кнопку цвета документа и т. д.|
|[CMFCColorBar::InitColors](#initcolors)|Инициализирует массив цветов с цветами в указанный палитры или системной палитре по умолчанию.|
|[CMFCColorBar::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает кнопку клавиатуры.|
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Вызывается платформой для закрытия иерархию элементов управления popup.|
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывается платформой, чтобы включить или отключить элемент пользовательского интерфейса элемента управления цветовой шкалы перед отображением элемента.|
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Откроется диалоговое окно цвета.|
|[CMFCColorBar::Rebuild](#rebuild)|Полностью перерисовывает элемент управления цветовой полосы.|
|[CMFCColorBar::SelectPalette](#selectpalette)|Задает логическую палитру из указанного контекста устройства в палитру кнопки родительского текущего элемента управления цветовой полосы.|
|[CMFCColorBar::SetPropList](#setproplist)|Наборы `m_pWndPropList` защищенный элемент данных в заданный указатель в сетке свойств.|
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Запрашивает фрейма окна, которому принадлежит обновление строки сообщения в строке состояния управления цветовой полосы.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|`m_bInternal`|Логическое поле, которое определяет, обрабатываются ли события мыши. Как правило события мыши обрабатываются, когда это поле имеет значение TRUE и FALSE — режим настройки.|
|`m_bIsEnabled`|Логическое значение, указывающее, включен ли элемент управления.|
|`m_bIsTearOff`|Логическое значение, указывающее, поддерживает ли элемент управления цвет панели закрепления.|
|`m_BoxSize`|Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , указывающий размер ячейки в сетке цветовой полосы.|
|`m_bShowDocColorsWhenDocked`|Логическое значение, указывающее, следует ли отображать цвета документа при присоединении цветовой полосы. Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|
|`m_bStdColorDlg`|Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|
|`m_ColorAutomatic`|Объект [COLORREF](/windows/desktop/gdi/colorref) , в котором хранится текущий цвет автоматической. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|
|`m_ColorNames`|[CMap](../../mfc/reference/cmap-class.md) объект, который связывает набор RGB цветов с их именами.|
|`m_colors`|Объект [CArray](../../mfc/reference/carray-class.md) из [COLORREF](/windows/desktop/gdi/colorref) значения, которые содержит цвета, отображаемые в элементе управления цветовой полосы.|
|`m_ColorSelected`|Объект [COLORREF](/windows/desktop/gdi/colorref) значение, которое является цвет, который пользователь выбрал в настоящее время из элемента управления цветовой полосы.|
|`m_lstDocColors`|Объект [CList](../../mfc/reference/clist-class.md) из [COLORREF](/windows/desktop/gdi/colorref) значения, которые содержит цвета, которые в настоящее время используются в документе.|
|`m_nCommandID`|Целое число без знака, являющееся Идентификатором команды, цвет кнопки.|
|`m_nHorzMargin`|Целое число, является горизонтального поля между кнопками цвет в сетке цветов.|
|`m_nHorzOffset`|Целое число, является смещение по горизонтали относительно центральной части кнопку цвета. Это значение важно в том случае, если кнопка отображает текст или изображение, а также цвет.|
|`m_nNumColumns`|Целое число, число столбцов в сетке управления цветовой шкалы цветов.|
|`m_nNumColumnsVert`|Целое число, число столбцов в сетке вертикально цветов.|
|`m_nNumRowsHorz`|Целое число, число столбцов в сетке горизонтальный цветов.|
|`m_nRowHeight`|Целое число, имеет высоту строки кнопок цвет в сетке цветов.|
|`m_nVertMargin`|Целое число, — это вертикальное поле между кнопками цвет в сетке цветов.|
|`m_nVertOffset`|Целое число, является смещение по вертикали относительно центральной части кнопку цвета. Это значение важно в том случае, если кнопка отображает текст или изображение, а также цвет.|
|`m_Palette`|Объект [CPalette](../../mfc/reference/cpalette-class.md) цветов, используемых в цветовой панели управления.|
|`m_pParentBtn`|Указатель на [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) объект, являющийся родительским для текущего кнопки. Это значение важен в том случае, если кнопка цвета в иерархии элементов управления панели инструментов или находится в сетке свойств цвета.|
|`m_pParentRibbonBtn`|Указатель на [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) объекта и используется родительской для текущей кнопки на ленте. Это значение важен в том случае, если кнопка цвета в иерархии элементов управления панели инструментов или находится в сетке свойств цвета.|
|`m_pWndPropList`|Указатель на [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) объекта.|
|`m_strAutoColor`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) то есть текст, отображаемый на **автоматического** кнопки. Дополнительные сведения см. в разделе [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|
|`m_strDocColors`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) то есть текст, отображаемый на кнопке цветов документа. Дополнительные сведения см. в разделе [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|
|`m_strOtherColor`|Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) то есть текст, отображаемый на *других* кнопки. Дополнительные сведения см. в разделе [CMFCColorBar::EnableOtherButton](#enableotherbutton).|

## <a name="remarks"></a>Примечания

Как правило, не создавайте `CMFCColorBar` объекта напрямую. Вместо этого [класс CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) (используется в меню и панелей инструментов) или [класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) создает `CMFCColorBar` объекта.

`CMFCColorBar` Класс предоставляет следующие функциональные возможности:

- Автоматически корректирует список цветов документа.

- Сохраняет и восстанавливает его состояние, а также состояние документа.

- Управляет кнопки «автоматически».

- Использует [класс CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md) управления, чтобы выбрать пользовательский цвет.

- Поддерживает состояние «перемещаемой» (если она создается с помощью [класс CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)).

Для включения `CMFCColorBar` функции в приложении:

1. Создание кнопки обычное меню и ему присваивается идентификатор, например ID_CHAR_COLOR.

1. В классе фрейма окна Переопределите [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) метод и замените обычное меню кнопку с [класс CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) объекта (путем вызова [CMFCToolBar: : ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).

1. Установка всех стилей, а также включить или отключить функции `CMFCColorBar` объекта во время [класс CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) создания. `CMFCColorMenuButton` Динамически создает объект `CMFCColorBar` объекта после вызовов framework `CreatePopupMenu` метод.

Когда пользователь нажимает кнопку управления цветовой полосы, инфраструктура использует `ON_COMMAND` макрос для уведомления родительского элемента управления цветовой полосы. В макросе параметр ID команды — это значение, которое было назначено кнопки управления цветовой полосы на шаге 1 (ID_CHAR_COLOR в этом примере). Дополнительные сведения см. в разделе [класс CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md), [класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md), [класс CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md), [класс CFrameWndEx](../../mfc/reference/cframewndex-class.md), и [класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) классы.

## <a name="example"></a>Пример

Следующий пример демонстрирует настройку цветовую шкалу с помощью различных методов в `CMFCColorBar` класса. Методы Установка полей горизонтальные и вертикальные, включить другие кнопки, создать окно управления цветовую шкалу и задает выбранный цвет. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).

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

Этот метод вызывается средой во время обработки сообщения WM_SIZE.

##  <a name="allowchangetextlabels"></a>  CMFCColorBar::AllowChangeTextLabels

Указывает, можно ли изменить текстовую метку из кнопок цвет.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда имеет значение FALSE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод всегда возвращает значение FALSE, что означает, что текстовые метки не может изменяться. Переопределите этот метод, чтобы включить изменение текстовых меток.

##  <a name="allowshowonlist"></a>  CMFCColorBar::AllowShowOnList

Указывает, может ли объект элемента управления цветовой полосы отображаться в списке панели инструментов во время процесса настройки.

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод всегда возвращает значение TRUE, это означает, что платформа может отображать цветовая панель элемента управления во время процесса настройки. Переопределите этот метод для реализации другое поведение.

##  <a name="calcsize"></a>  CMFCColorBar::CalcSize

Вызвано структурой в ходе процесса вычисления макета.

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>Параметры

*bVertDock*<br/>
[in] Значение TRUE, чтобы указать, что элемент управления панели Цвет закреплен по вертикали; Значение FALSE, чтобы указать, что элемент управления панели Цвет закреплена горизонтально.

### <a name="return-value"></a>Возвращаемое значение

Размер массива кнопок цвет в элементе управления цветовой полосы.

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

*Цвета*<br/>
[in] Массив цветов, отображаемых на цветовой панели управления структурой.

*Цвет*<br/>
[in] Изначально выбранного цвета.

*lpszAutoColor*<br/>
[in] Текстовая метка *автоматического* кнопка цвета (по умолчанию), или значение NULL.

Стандартную метку для автоматической кнопки — **автоматического**.

*lpszOtherColor*<br/>
[in] Текстовая метка *других* кнопка, отображающая более цвета, или значение NULL.

Стандартный метки другие кнопки **Дополнительные цвета...** .

*lpszDocColors*<br/>
[in] Текстовая подпись кнопки цветов документа. Палитра цветов документе перечислены все цвета, которые в настоящее время использует документ.

*lstDocColors*<br/>
[in] Список цветов, которые в настоящее время использует документ.

*nColumns*<br/>
[in] Число столбцов, к которым имеет массив цветов.

*nRowsDockHorz*<br/>
[in] Число строк, к которым имеет цветовой панели, когда она закреплена горизонтально.

*nColDockVert*<br/>
[in] Число столбцов, которые цветовой полосы при их закреплении по вертикали.

*colorAutomatic*<br/>
[in] Цвет по умолчанию, платформа применяется при нажатии кнопки автоматического.

*nCommandID*<br/>
[in] ИД команды управления цветовой полосы.

*pParentBtn*<br/>
[in] Указатель на родительский кнопки.

*src*<br/>
[in] Существующий `CMFCColorBar` объект, который необходимо скопировать в новый `CMFCColorBar` объекта.

*uiCommandID*<br/>
[in] Идентификатор команды.

##  <a name="contexttosize"></a>  CMFCColorBar::ContextToSize

Вычисляет вертикального и горизонтального поля, должны содержать кнопки на цветовой панели управления и корректирует положение этих кнопок.

```
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*bSquareButtons*|[in] Значение TRUE, чтобы указать, что фигуры кнопок на элементе управления полосы цвета квадрата; в противном случае — значение FALSE. Значение по умолчанию — TRUE.|
|*bCenterButtons*|[in] Значение TRUE, чтобы указать, что содержимое на поверхности нажимаемой кнопки управления цветовой полосы выравнивается по центру; в противном случае — значение FALSE. Значение по умолчанию — TRUE.|

### <a name="remarks"></a>Примечания

##  <a name="create"></a>  CMFCColorBar::Create

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

*pParentWnd*<br/>
[in] Указатель на родительское окно.

*dwStyle*<br/>
[in] Побитовое сочетание (OR) [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*nID*<br/>
[in] Идентификатор команды.

*pPalette*<br/>
[in] Указатель на палитру цветов. Значение по умолчанию имеет значение NULL.

*nColumns*<br/>
[in] Число столбцов в элементе управления цветовой полосы. Значение по умолчанию — 0.

*nRowsDockHorz*<br/>
[in] Число строк в элементе управления цветовой панели, когда она закреплена горизонтально. Значение по умолчанию — 0.

*nColDockVert*<br/>
[in] Число столбцов в элементе управления цветовой панели, когда она закреплена по вертикали. Значение по умолчанию — 0.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Для создания `CMFCColorBar` объекта, вызовите конструктор класса, а затем этот метод. `Create` Метод создает элемент управления Windows и инициализирует список цветов.

##  <a name="createcontrol"></a>  CMFCColorBar::CreateControl

Создает окно управления цветовой полосы, присоединяется к `CMFCColorBar` , а также изменяет размер окна элемента управления должен содержать указанный палитры цветов.

```
virtual BOOL CreateControl(
    CWnd* pParentWnd,
    const CRect& rect,
    UINT nID,
    int nColumns=-1,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
[in] Указатель на родительское окно. Не может принимать значение NULL.

*Rect*<br/>
[in] Ограничивающий прямоугольник, указывающий, куда нарисуйте элемент управления цветовой полосы.

*nID*<br/>
[in] Идентификатор элемента управления.

*nColumns*<br/>
[in] Оптимальное количество столбцов в элементе управления цветовой полосы. Этот метод изменяет это число в соответствии с указанным палитры цветов. Значение по умолчанию равно -1, это означает, что этот параметр не указан.

*pPalette*<br/>
[in] Указатель на палитру цветов, или значение NULL. Если этот параметр имеет значение NULL, этот метод вычисляет размер элемента управления цветовой полосы, как при указанном 20 цветов. Значение по умолчанию имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует *rect*, *nColumns*, и *pPalette* параметры, для которого требуется вычислить нужное количество или строки и столбцы в цветовой панели управления, а затем вызывает [CMFCColorBar::Create](#create) метод.

##  <a name="createpalette"></a>  CMFCColorBar::CreatePalette

Инициализирует палитры цветов в указанном массиве цветов.

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*arColors*|[in] Массив цветов.|
|*Палитра*|[in] Палитру цветов.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

##  <a name="enableautomaticbutton"></a>  CMFCColorBar::EnableAutomaticButton

Показывает или скрывает автоматической кнопки.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Текстовая метка *автоматического* кнопка цвета (по умолчанию), или значение NULL.

Стандартную метку для автоматической кнопки — **автоматического**.

*colorAutomatic*<br/>
[in] Цвет по умолчанию, платформа применяется при нажатии кнопки автоматического.

*bEnable*<br/>
[in] Значение TRUE для включения автоматической кнопки; Значение FALSE, чтобы отключить автоматическое кнопку. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Текстовая метка автоматической кнопки удаляется, если *lpszLabel* параметр имеет значение NULL или *bEnable* параметр имеет значение FALSE.

##  <a name="enableotherbutton"></a>  CMFCColorBar::EnableOtherButton

Включает или отключает отображение диалоговое окно, которое позволяет пользователю выбрать дополнительные цвета.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Текстовая метка *других* кнопка, отображающая более цвета, или значение NULL.

— Стандартную метку для данной кнопки **Дополнительные цвета...** .

*bAltColorDlg*<br/>
[in] True, если [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговом окне; Значение FALSE, чтобы отображать стандартный [CColorDialog](../../mfc/reference/ccolordialog-class.md) диалоговое окно. Значение по умолчанию — TRUE.

*bEnable*<br/>
[in] Значение TRUE, чтобы включить кнопку; Значение FALSE, чтобы отключить кнопку. Значение по умолчанию — TRUE.

##  <a name="getcolor"></a>  CMFCColorBar::GetColor

Извлекает выбранный цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Выбранный цвет.

##  <a name="getcolorgridsize"></a>  CMFCColorBar::GetColorGridSize

Вычисляет количество строк и столбцов в сетке, цветовая панель элемента управления.

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*bVertDock*|[in] Значение TRUE, чтобы выполнить вычисления для элемента управления по вертикали закрепленной цветовую шкалу; в противном случае выполните вычисления для горизонтально пристыкованного элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) которого `cx` компонент содержит количество столбцов и для которой `cy` компонент содержит количество строк.

##  <a name="getcommandid"></a>  CMFCColorBar::GetCommandID

Получает идентификатор команды текущего элемента управления цветовой полосы.

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды.

### <a name="remarks"></a>Примечания

Когда пользователь выбирает новый цвет, инфраструктура отправляет идентификатор команды в сообщении WM_COMMAND, чтобы уведомлять родительский `CMFCColorBar` объекта.

##  <a name="getextraheight"></a>  CMFCColorBar::GetExtraHeight

Вычисляет высоту дополнительных текущей цветовой полосы, необходимую для отображения элементов прочие пользовательского интерфейса, такие как **других** цвета кнопки или документа.

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*nNumColumns*|[in] Если элемент управления цветовой полосы содержит цвета документа, количество столбцов для отображения в сетке цветов документа. В противном случае это значение не используется.|

### <a name="return-value"></a>Возвращаемое значение

Дополнительный вычисленную, является обязательным.

##  <a name="gethighlightedcolor"></a>  CMFCColorBar::GetHighlightedColor

Получает цвет, который означает, что кнопка цвета имеет фокус; кнопка является *горячей*.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB.

### <a name="remarks"></a>Примечания

##  <a name="gethorzmargin"></a>  CMFCColorBar::GetHorzMargin

Извлекает горизонтального поля, которое представляет собой пространство между слева или ячейки правильный цвет и границы области клиента.

```
int GetHorzMargin();
```

### <a name="return-value"></a>Возвращаемое значение

Поля по горизонтали.

##  <a name="getvertmargin"></a>  CMFCColorBar::GetVertMargin

Получает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейки цвета и границы области клиента.

```
int GetVertMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Вертикальное поле.

##  <a name="initcolors"></a>  CMFCColorBar::InitColors

Инициализирует массив цветов, цвета в палитре указанного или с системной палитре по умолчанию.

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pPalette*|[in] Указатель на объект в палитре, или значение NULL. Если этот параметр имеет значение NULL, этот метод использует палитры по умолчанию операционной системы.|
|*arColors*|[in] Массив цветов.|

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве цветов.

##  <a name="istearoff"></a>  CMFCColorBar::IsTearOff

Указывает, является ли текущий цветовой полосы фиксируемого.

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущий элемент управления цветовой полосы фиксируемого; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если фиксируемый элемент управления цветовой полосы, его защита от разрыва off панель элементов управления и закреплено в другое расположение.

##  <a name="onkey"></a>  CMFCColorBar::OnKey

Вызывается платформой, когда пользователь нажимает кнопку клавиатуры.

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>Параметры

*NChar*<br/>
[in] Виртуальная клавиша код для ключа, который пользователь нажал клавиши.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод обрабатывает указанным ключом; в противном случае — значение FALSE.

##  <a name="onsendcommand"></a>  CMFCColorBar::OnSendCommand

Вызывается платформой для закрытия иерархию всплывающие элементы.

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pButton*|[in] Указатель на элемент управления, находящийся на панели инструментов.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

##  <a name="onupdatecmdui"></a>  CMFCColorBar::OnUpdateCmdUI

Вызывается платформой, чтобы включить или отключить элемент пользовательского интерфейса элемента управления цветовой шкалы перед отображением элемента.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
[in] Указатель на окно, содержащее элемент пользовательского интерфейса, чтобы обновить.

*bDisableIfNoHndler*<br/>
[in] Значение TRUE, чтобы отключить элемент пользовательского интерфейса, если обработчик не определен в схеме сообщений; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Когда пользователь приложения щелкает элемент пользовательского интерфейса, элемент необходимо знать ли он должен отображаться как включенная или отключена. Цель сообщение команды предоставляет эти сведения, реализация обработчика команды ON_UPDATE_COMMAND_UI. Используйте этот метод для обработки команды. Дополнительные сведения см. в разделе [класс CCmdUI](../../mfc/reference/ccmdui-class.md).

##  <a name="opencolordialog"></a>  CMFCColorBar::OpenColorDialog

Откроется диалоговое окно цвета.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Параметры

*colorDefault*<br/>
[in] Цвет, который выбран по умолчанию, когда откроется диалоговое окно «цвет».

*colorRes*<br/>
[out] Цвет, который пользователь выбрал.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если пользователь выбрал цвета; Значение FALSE, если пользователь отменил диалоговое окно «цвет».

### <a name="remarks"></a>Примечания

##  <a name="rebuild"></a>  CMFCColorBar::Rebuild

Полностью перерисовывает элемент управления цветовой полосы.

```
virtual void Rebuild();
```

##  <a name="selectpalette"></a>  CMFCColorBar::SelectPalette

Задает логическую палитру из указанного контекста устройства в палитру кнопки родительского текущего элемента управления цветовой полосы.

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pDC*|[in] Указатель на контекст устройства кнопки родительского текущего элемента управления цветовой полосы.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на палитру, которая заменяется палитры кнопки родительского текущего элемента управления цветовой полосы.

##  <a name="setcolor"></a>  CMFCColorBar::SetColor

Задает цвет, который выбран в данный момент.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
[in] Значение цвета RGB.

##  <a name="setcolorname"></a>  CMFCColorBar::SetColorName

Задает новое имя для выбранного цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
[in] Значение цвета RGB.

*strName*<br/>
[in] Новое имя для указанного цвета.

### <a name="remarks"></a>Примечания

Этот метод изменяет имя указанного цвета во всех `CMFCColorBar` объектов в приложении.

##  <a name="setcommandid"></a>  CMFCColorBar::SetCommandID

Задает новый идентификатор команды для элемента управления цветовой полосы.

```
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>Параметры

*nCommandID*<br/>
[in] Идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод для изменения идентификатор команды элемента управления цветовую шкалу и уведомлять родительское окно элемента управления, который был изменен идентификатор.

##  <a name="setdocumentcolors"></a>  CMFCColorBar::SetDocumentColors

Задает список цветов, используемых в текущем документе.

```
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>Параметры

*lpszCaption*<br/>
[in] Заголовок, отображаемый, когда элемент управления панели Цвет не прикреплен.

*lstDocColors*<br/>
[in] Список цветов, заменяющий цвета текущего документа.

*bShowWhenDocked*<br/>
[in] Значение TRUE для отображения цвета документа при присоединении цветовая панель управления; в противном случае — значение FALSE. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

*Цвета документа* цвета, которые в настоящее время используются в документе. Платформа автоматически ведет список цвета документа, но этот метод можно использовать для изменения списка.

##  <a name="sethorzmargin"></a>  CMFCColorBar::SetHorzMargin

Задает горизонтальное поле которого является расстояние между левой или правильный цвет ячейки и границей клиентской области.

```
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>Параметры

*nHorzMargin*<br/>
[in] Поля по горизонтали, в пикселях.

### <a name="remarks"></a>Примечания

По умолчанию [CMFCColorBar::CMFCColorBar](#cmfccolorbar) конструктор задает горизонтального поля для 4 точкам.

##  <a name="setproplist"></a>  CMFCColorBar::SetPropList

Наборы `m_pWndPropList` защищенный элемент данных в заданный указатель в сетке свойств.

```
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pWndList*|[in] Указатель на объект элемента управления сетки свойств.|

##  <a name="setvertmargin"></a>  CMFCColorBar::SetVertMargin

Задает вертикальное поле, которое представляет собой пространство между верхней или нижней ячейки цвета и границы области клиента.

```
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>Параметры

*nVertMargin*<br/>
[in] Вертикальное поле, в пикселях.

### <a name="remarks"></a>Примечания

По умолчанию [CMFCColorBar::CMFCColorBar](#cmfccolorbar) конструктор задает вертикальное поле для 4 точкам.

##  <a name="showcommandmessagestring"></a>  CMFCColorBar::ShowCommandMessageString

Запрашивает фрейма окна, которому принадлежит обновление строки сообщения в строке состояния управления цветовой полосы.

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
[in] Идентификатор команды. (Этот параметр учитывается).

### <a name="remarks"></a>Примечания

Этот метод отправляет сообщение WM_SETMESSAGESTRING владельца элемента цветовой полосы.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
