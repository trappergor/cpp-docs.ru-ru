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
ms.openlocfilehash: 58fddeef9cb0afe930af84b05e6a87871f729da4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752568"
---
# <a name="cmfccolorbar-class"></a>Класс CMFCColorBar

Класс `CMFCColorBar` представляет собой панель управления стыковкой, которая может выбирать цвета в документе или приложении.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Формирует объект `CMFCColorBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorBar::ContextToSize](#contexttosize)|Вычисляет вертикальные и горизонтальные поля, которые необходимы для хранения кнопок на управлении цветовой панелью, а затем регулирует расположение этих кнопок.|
|[CMFCColorBar::СозданиеКонтроль](#createcontrol)|Создает окно управления цветовой панелью, `CMFCColorBar` прикрепляет его к объекту и изменяет размер элемента управления, чтобы содержать указанную палитру цветов.|
|[CMFCColorBar::Создание](#create)|Создает окно управления цветовой панелью `CMFCColorBar` и прикрепляет его к объекту.|
|[CMFCColorBar:EnableAutomaticButton](#enableautomaticbutton)|Показывает или скрывает автоматическую кнопку.|
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Позволяет или отскакивает отображение диалогового окна, которое позволяет пользователю выбрать больше цветов.|
|[CMFCColorBar::GetColor](#getcolor)|Извлекает выбранный в настоящее время цвет.|
|[CMFCColorBar:GetCommandID](#getcommandid)|Извлекает идентификатор команды текущего управления цветовой полосой.|
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Получает цвет, который означает, что цветная кнопка имеет фокус; то есть, кнопка *горячая*.|
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Извлекает горизонтальную маржу, которая представляет собой пространство между левой или правой цветовой ячейкой и границей области клиента.|
|[CMFCColorBar:GetVertMargin](#getvertmargin)|Извлекает вертикальную маржу, которая представляет собой пространство между верхней или нижней цветовой ячейкой и границей области клиента.|
|[CMFCColorBar::IsTearOff](#istearoff)|Указывает, является ли текущая цветовая панель доковой.|
|[CMFCColorBar::SetColor](#setcolor)|Устанавливает выбранный в настоящее время цвет.|
|[CMFCColorBar::SetColorName](#setcolorname)|Устанавливает новое имя для указанного цвета.|
|[CMFCColorBar::SetCommandID](#setcommandid)|Устанавливает новый идентификатор команды для управления цветовой панелью.|
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Устанавливает список цветов, используемых в текущем документе.|
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Устанавливает горизонтальную маржу, которая представляет собой пространство между левой или правой цветовой ячейкой и границей области клиента.|
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Устанавливает вертикальную маржу, которая представляет собой пространство между верхней или нижней цветовой ячейкой и границей области клиента.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Регулирует положение цветовых кнопок на управлении цветовой панелью.|
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Указывает, может ли изменяться текстовая метка цветовых кнопок.|
|[CMFCColorbar::Allowshowonlist](#allowshowonlist)|Указывает, может ли объект управления цветовой панелью отображаться в списке панели инструментов в процессе настройки.|
|[CMFCColorBar::CalcSize](#calcsize)|Вызывается рамкой в рамках процесса расчета макета.|
|[CMFCColorBar::CreatePalette](#createpalette)|Инициализирует палитру с цветами в определенном массиве цветов.|
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Вычисляет количество строк и столбцов в сетке управления цветовой панелью.|
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Вычисляет дополнительную высоту, что текущая цветовая панель требует для отображения различных элементов пользовательского интерфейса, таких как **другие** кнопки, цвета документов, и так далее.|
|[CMFCColorBar::InitColors](#initcolors)|Инициализирует массив цветов с цветами в указанной палитре или палитре по умолчанию системы.|
|[CMFCColorBar::OnKey](#onkey)|Вызывается по системе, когда пользователь нажимает кнопку клавиатуры.|
|[CMFCColorBar::OnsendCommand](#onsendcommand)|Вызывается инфраструктурой, чтобы закрыть иерархию всплывающих элементов управления.|
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывается рамкой, чтобы включить или отключить элемент пользовательского интерфейса управления цветовой панелью перед отображением элемента.|
|[CMFCColorBar::OpenColorДиалог](#opencolordialog)|Открывает цветную коробку диалога.|
|[CMFCColorBar::Восстановление](#rebuild)|Полностью перерисовывает управление цветовой планки.|
|[CMFCColorBar::SelectPalette](#selectpalette)|Устанавливает логическую палитру заданного контекста устройства в палитру родительской кнопки текущего управления цветовой панелью.|
|[CMFCColorBar::SetPropList](#setproplist)|Устанавливает `m_pWndPropList` защищенный элемент данных в указанный указатель на управление сеткой свойств.|
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Запросы окна кадра, которому принадлежит элемент управления цветовой панели, для обновления строки сообщения в строке состояния.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|`m_bInternal`|Поле Boolean, определяющее, обрабатываются ли события мыши. Как правило, события мыши обрабатываются, когда это поле является правдой, а режим настройки FALSE.|
|`m_bIsEnabled`|Булеан, указывающий, включен ли элемент управления.|
|`m_bIsTearOff`|Boolean, который указывает, поддерживает ли управление цветовой панелью стыковку.|
|`m_BoxSize`|Объект [CSize,](../../atl-mfc-shared/reference/csize-class.md) который определяет размер ячейки в сетке цветовой панели.|
|`m_bShowDocColorsWhenDocked`|Boolean, который указывает, следует ли показывать цвета документов, когда цветовая панель пристыкована. Для получения дополнительной информации, см [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|
|`m_bStdColorDlg`|Boolean, который указывает, следует ли показывать стандартную систему цвет диалоговую коробку или диалоговое окно [CMFCColorDialog.](../../mfc/reference/cmfccolordialog-class.md) Для получения дополнительной информации [см. CMFCColorBar::EnableOtherButton](#enableotherbutton).|
|`m_ColorAutomatic`|[COLORREF,](/windows/win32/gdi/colorref) который хранит текущий автоматический цвет. Для получения дополнительной информации [см. CMFCColorBar::EnableOtherButton](#enableotherbutton).|
|`m_ColorNames`|Объект [CMap,](../../mfc/reference/cmap-class.md) который связывает набор цветов RGB с их именами.|
|`m_colors`|[CArray](../../mfc/reference/carray-class.md) [из COLORREF](/windows/win32/gdi/colorref) значения, которые содержат цвета, которые отображаются в управлении цветовой панели.|
|`m_ColorSelected`|Значение [COLORREF—](/windows/win32/gdi/colorref) это цвет, выбранный пользователем в настоящее время из элемента управления цветовой гаммы.|
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) значений [COLORREF,](/windows/win32/gdi/colorref) содержащий цвета, которые в настоящее время используются в документе.|
|`m_nCommandID`|Неподписанный ряд, который является идентификатором команды кнопки цвета.|
|`m_nHorzMargin`|Цель, которая является горизонтальной разницы между цветными кнопками в сетке цветов.|
|`m_nHorzOffset`|Цель, которая является горизонтальной смещения в центр кнопки цвета. Это значение является значительным, если кнопка отображает текст или изображение в дополнение к цвету.|
|`m_nNumColumns`|Целый ряд, который является число столбцов в сетке управления цветовой решеткой цветов.|
|`m_nNumColumnsVert`|Целый ряд, который является число столбцов в вертикально ориентированной сетке цветов.|
|`m_nNumRowsHorz`|Целый ряд, который является число столбцов в горизонтально ориентированной сетке цветов.|
|`m_nRowHeight`|Цель, которая является высота ряда цветовых кнопок в сетке цветов.|
|`m_nVertMargin`|Цель, которая представляет собой вертикальную разницу между цветными кнопками в сетке цветов.|
|`m_nVertOffset`|Цель, которая представляет собой вертикальное смещение к центру кнопки цвета. Это значение является значительным, если кнопка отображает текст или изображение в дополнение к цвету.|
|`m_Palette`|[CPalette](../../mfc/reference/cpalette-class.md) цветов, которые используются в управлении цветовой гаммы.|
|`m_pParentBtn`|Указатель на объект [CMFCColorButton,](../../mfc/reference/cmfccolorbutton-class.md) который является родителем текущей кнопки. Это значение является значительным, если цветная кнопка находится в иерархии элементов управления инструментами или находится в управлении сеткой свойств цвета.|
|`m_pParentRibbonBtn`|Указатель на объект [CMFCRibbonColorButton,](../../mfc/reference/cmfcribboncolorbutton-class.md) который находится на ленте и является родительской кнопкой текущей кнопки. Это значение является значительным, если цветная кнопка находится в иерархии элементов управления инструментами или находится в управлении сеткой свойств цвета.|
|`m_pWndPropList`|Указатель на объект [CMFCPropertyGridCtrl.](../../mfc/reference/cmfcpropertygridctrl-class.md)|
|`m_strAutoColor`|[CString,](../../atl-mfc-shared/reference/cstringt-class.md) который отображается на кнопке **Автоматическая.** Для получения дополнительной информации [см. CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|
|`m_strDocColors`|[CString,](../../atl-mfc-shared/reference/cstringt-class.md) который отображается на кнопке цвета документа. Для получения дополнительной информации, см [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|
|`m_strOtherColor`|[CString,](../../atl-mfc-shared/reference/cstringt-class.md) который отображается на *другой* кнопке. Для получения дополнительной информации [см. CMFCColorBar::EnableOtherButton](#enableotherbutton).|

## <a name="remarks"></a>Remarks

Как правило, вы `CMFCColorBar` не создаете объект напрямую. Вместо `CMFCColorBar` [этого, CMFCColorMenuButton класса](../../mfc/reference/cmfccolormenubutton-class.md) (используется в меню и панели инструментов) или [CMFCColorButton класса](../../mfc/reference/cmfccolorbutton-class.md) создает объект.

Класс `CMFCColorBar` предоставляет следующую функциональность:

- Автоматически настраивает список цветов документов.

- Сохраняет и восстанавливает его состояние вместе с состоянием документа.

- Управляет кнопкой "автоматическая".

- Использует элемент управления [cmFCColorPickerCtrl класса](../../mfc/reference/cmfccolorpickerctrl-class.md) для выбора пользовательского цвета.

- Поддерживает состояние «слезы» (если оно создано с помощью [класса CMFCColorMenuButton).](../../mfc/reference/cmfccolormenubutton-class.md)

Чтобы включить `CMFCColorBar` функциональность в приложение:

1. Создайте обычную кнопку меню и назначайте ей идентификатор, например, ID_CHAR_COLOR.

1. В классе окон кадра переопределить метод [CFrameWndEx:::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) и замените обычную кнопку меню объектом [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md) (позвонив в [CMFCToolBar::ReplaceButton).](../../mfc/reference/cmfctoolbar-class.md#replacebutton)

1. Установите все стили и включите `CMFCColorBar` или отключите функции объекта во время создания [cmFCColorMenuButton класса.](../../mfc/reference/cmfccolormenubutton-class.md) Объект `CMFCColorMenuButton` динамически создает `CMFCColorBar` объект после вызова `CreatePopupMenu` фреймворка.

Когда пользователь нажимает кнопку управления цветовой панелью, `ON_COMMAND` фреймворк использует макрос для уведомления родителя управления цветовой панелью. В макросе параметр идентификатора команды — это значение, назначенное кнопке управления цветовой панелью в шаге 1 (ID_CHAR_COLOR в этом примере). Для получения дополнительной информации, см [CMFCColorMenuButton класса](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton класса](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl класса](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx класса](../../mfc/reference/cframewndex-class.md), и [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md) классов.

## <a name="example"></a>Пример

Ниже приводится следующий пример, как настроить цветовую панель `CMFCColorBar` с помощью различных методов в классе. Методы устанавливают горизонтальные и вертикальные поля, включают другую кнопку, создают окно управления цветовой панелью и устанавливают выбранный в настоящее время цвет. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

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

## <a name="cmfccolorbaradjustlocations"></a><a name="adjustlocations"></a>CMFCColorBar::AdjustLocations

Регулирует положение цветовых кнопок на управлении цветовой панелью.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Remarks

Этот метод вызывается инфраструктурой во время WM_SIZE обработки сообщений.

## <a name="cmfccolorbarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>CMFCColorBar::AllowChangeTextLabels

Указывает, может ли изменяться текстовая метка цветовых кнопок.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда значение FALSE.

### <a name="remarks"></a>Remarks

По умолчанию этот метод всегда возвращает FALSE, что означает, что текстовые метки не могут быть изменены. Переопределить этот метод, чтобы изменить текстовые метки.

## <a name="cmfccolorbarallowshowonlist"></a><a name="allowshowonlist"></a>CMFCColorbar::Allowshowonlist

Указывает, может ли объект управления цветовой панелью отображаться в списке панели инструментов в процессе настройки.

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда TRUE.

### <a name="remarks"></a>Remarks

По умолчанию этот метод всегда возвращает TRUE, что означает, что фреймворк может отображать элемент управления цветовой панели в процессе настройки. Переопределить этот метод для реализации другого поведения.

## <a name="cmfccolorbarcalcsize"></a><a name="calcsize"></a>CMFCColorBar::CalcSize

Вызывается рамкой в рамках процесса расчета макета.

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>Параметры

*bVertDock*<br/>
(в) TRUE указать, что управление цветовой панелью пристыковано вертикально; FALSE указать, что управление цветовой панелью пристыковано горизонтально.

### <a name="return-value"></a>Возвращаемое значение

Размер массива цветных кнопок в управлении цветовой панелью.

## <a name="cmfccolorbarcmfccolorbar"></a><a name="cmfccolorbar"></a>CMFCColorBar::CMFCColorBar

Формирует объект `CMFCColorBar`.

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
(в) Массив цветов, отображается в элементе управления цветовой гаммы.

*Цвет*<br/>
(в) Первоначально выбранный цвет.

*lpszAutoColor*<br/>
(в) Текстовая метка *автоматической* (по умолчанию) цветной кнопки, или NULL.

Стандартная метка для автоматической кнопки **автоматическая**.

*lpszOtherColor*<br/>
(в) Текстовая метка *другой* кнопки, которая отображает больше цветов, или NULL.

Стандартная метка для другой кнопки **больше цветов ...**.

*lpszDocColors*<br/>
(в) Текстовая метка кнопки цветов документа. В документе цветовая палитра перечисляет все цвета, которые документ использует в настоящее время.

*lstDocColors*<br/>
(в) Список цветов, которые в настоящее время используется документом.

*nColumns*<br/>
(в) Количество столбцов, которые есть у массива цветов.

*nRowsDockHorz*<br/>
(в) Количество строк, которые имеет цветовая панель, когда она состыкована горизонтально.

*nColDockVert*<br/>
(в) Количество столбцов, которые имеет цветовая панель, когда она состыкована вертикально.

*colorAutomatic*<br/>
(в) Цвет по умолчанию, который применяется при нажатии кнопки автоматической.

*nCommandID*<br/>
(в) Идентификатор команды управления цветовой панелью.

*pParentBtn*<br/>
(в) Указатель на кнопку родительской кнопки.

*src*<br/>
(в) Существующий `CMFCColorBar` объект, который должен `CMFCColorBar` быть скопирован в новый объект.

*uiCommandID*<br/>
(в) Идентификатор команды.

## <a name="cmfccolorbarcontexttosize"></a><a name="contexttosize"></a>CMFCColorBar::ContextToSize

Вычисляет вертикальные и горизонтальные поля, которые необходимы для хранения кнопок на управлении цветовой панелью, и регулирует расположение этих кнопок.

```cpp
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*bSquareButtons*|(в) ПРАВДА указать, что форма кнопок на управлении цветовой панелью квадратная; в противном случае, FALSE. Значение по умолчанию — TRUE.|
|*bCenterButtons*|(в) TRUE указать, что содержимое на лице кнопки управления цветовой панелью центрируется; в противном случае, FALSE. Значение по умолчанию — TRUE.|

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbarcreate"></a><a name="create"></a>CMFCColorBar::Создание

Создает окно управления цветовой панелью `CMFCColorBar` и прикрепляет его к объекту.

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
(в) Указатель на родительское окно.

*dwStyle*<br/>
(в) Битовая комбинация (OR) [оконных стилей.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*nID*<br/>
(в) Идентификатор команды.

*pPalette*<br/>
(в) Указатель на палитру цветов. Значение по умолчанию — NULL.

*nColumns*<br/>
(в) Количество столбцов в управлении цветовой панели. Значение по умолчанию равно 0.

*nRowsDockHorz*<br/>
(в) Количество строк в управлении цветовой панели, когда она состыкована горизонтально. Значение по умолчанию равно 0.

*nColDockVert*<br/>
(в) Количество столбцов в управлении цветовой панели, когда она пристыкована по вертикали. Значение по умолчанию равно 0.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Чтобы построить `CMFCColorBar` объект, позвоните в конструктор класса, затем этот метод. Метод `Create` создает управление Windows и инициализирует список цветов.

## <a name="cmfccolorbarcreatecontrol"></a><a name="createcontrol"></a>CMFCColorBar::СозданиеКонтроль

Создает окно управления цветовой панелью, `CMFCColorBar` прикрепляет его к объекту и изменяет размер окна управления, чтобы содержать указанную палитру цветов.

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
(в) Указатель на родительское окно. Не может быть NULL.

*rect*<br/>
(в) Ограничивающий прямоугольник, который определяет, где нарисовать управление цветовой полосой.

*nID*<br/>
(в) Идентификатор управления.

*nColumns*<br/>
(в) Идеальное количество столбцов в управлении цветовой панели. Этот метод изменяет это число в соответствии с указанной палитрой цветов. По умолчанию -1, что означает, что этот параметр не указан.

*pPalette*<br/>
(в) Указатель на палитру цветов, или NULL. Если этот параметр NULL, этот метод вычисляет размер управления цветовой панели, как если бы 20 цветов были указаны. Значение по умолчанию — NULL.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод удается; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Этот метод использует параметры *rect,* *nColumns*и *pPalette* для расчета соответствующего числа или строк и столбцов в управлении цветовой панелью, а затем вызывает [CMFCColorBar::Create](#create) method.

## <a name="cmfccolorbarcreatepalette"></a><a name="createpalette"></a>CMFCColorBar::CreatePalette

Инициализирует палитру с цветами в определенном массиве цветов.

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*arColors*|(в) Массив цветов.|
|*палитра*|(в) Палитра цветов.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

## <a name="cmfccolorbarenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorBar:EnableAutomaticButton

Показывает или скрывает автоматическую кнопку.

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Текстовая метка *автоматической* (по умолчанию) цветной кнопки, или NULL.

Стандартная метка для автоматической кнопки **автоматическая**.

*colorAutomatic*<br/>
(в) Цвет по умолчанию, который применяется при нажатии кнопки автоматической.

*bEnable*<br/>
(в) TRUE для включения автоматической кнопки; FALSE отключить автоматическую кнопку. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Remarks

Текстовая метка автоматической кнопки удаляется, если параметр *lpszLabel* является NULL или параметр *bEnable* FALSE.

## <a name="cmfccolorbarenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorBar::EnableOtherButton

Позволяет или отскакивает отображение диалогового окна, которое позволяет пользователю выбрать больше цветов.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Текстовая метка *другой* кнопки, которая отображает больше цветов, или NULL.

Стандартная метка для этой кнопки **больше цветов ...**.

*bAltColorDlg*<br/>
(в) TRUE для отображения диалогового ящика [CMFCColorDialog;](../../mfc/reference/cmfccolordialog-class.md) FALSE для отображения стандартного диалогового ящика [CColorDialog.](../../mfc/reference/ccolordialog-class.md) Значение по умолчанию — TRUE.

*bEnable*<br/>
(в) TRUE для включения кнопки; FALSE отключить кнопку. Значение по умолчанию — TRUE.

## <a name="cmfccolorbargetcolor"></a><a name="getcolor"></a>CMFCColorBar::GetColor

Извлекает выбранный в настоящее время цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Выбранный в настоящее время цвет.

## <a name="cmfccolorbargetcolorgridsize"></a><a name="getcolorgridsize"></a>CMFCColorBar::GetColorGridSize

Вычисляет количество строк и столбцов в сетке управления цветовой панелью.

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*bVertDock*|(в) TRUE для выполнения расчета для вертикально пристыкованного управления цветовой панелью; в противном случае выполните расчет для горизонтально пристыкованного управления.|

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize,](../../atl-mfc-shared/reference/csize-class.md) компонент которого `cx` содержит количество `cy` столбцов и компонент которого содержит количество строк.

## <a name="cmfccolorbargetcommandid"></a><a name="getcommandid"></a>CMFCColorBar:GetCommandID

Извлекает идентификатор команды текущего управления цветовой полосой.

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды.

### <a name="remarks"></a>Remarks

Когда пользователь выбирает новый цвет, фреймворк отправляет идентификатор `CMFCColorBar` команды в WM_COMMAND сообщение, чтобы уведомить родителя объекта.

## <a name="cmfccolorbargetextraheight"></a><a name="getextraheight"></a>CMFCColorBar::GetExtraHeight

Вычисляет дополнительную высоту, необходимую текущей цветовой панели для отображения различных элементов пользовательского интерфейса, таких как **другие** кнопки или цвета документа.

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*nNumКолонки*|(в) Если элемент управления цветовой панели содержит цвета документов, количество столбцов отображается в сетке цветов документа. В противном случае это значение не используется.|

### <a name="return-value"></a>Возвращаемое значение

Рассчитанная дополнительная высота, которая требуется.

## <a name="cmfccolorbargethighlightedcolor"></a><a name="gethighlightedcolor"></a>CMFCColorBar::GetHighlightedColor

Получает цвет, который означает, что цветная кнопка имеет фокус; то есть, кнопка *горячая*.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB.

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbargethorzmargin"></a><a name="gethorzmargin"></a>CMFCColorBar::GetHorzMargin

Извлекает горизонтальную маржу, которая представляет собой пространство между левой или правой цветовой ячейкой и границей области клиента.

```
int GetHorzMargin();
```

### <a name="return-value"></a>Возвращаемое значение

Горизонтальная маржа.

## <a name="cmfccolorbargetvertmargin"></a><a name="getvertmargin"></a>CMFCColorBar:GetVertMargin

Извлекает вертикальную маржу, которая представляет собой пространство между верхней или нижней цветовой ячейкой и границей области клиента.

```
int GetVertMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Вертикальная маржа.

## <a name="cmfccolorbarinitcolors"></a><a name="initcolors"></a>CMFCColorBar::InitColors

Инициализирует массив цветов с цветами в указанной палитре или с палитрой по умолчанию системы.

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pPalette*|(в) Указатель на объект палитры, или NULL. Если этот параметр NULL, этот метод использует палитру по умолчанию операционной системы.|
|*arColors*|(в) Массив цветов.|

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве цветов.

## <a name="cmfccolorbaristearoff"></a><a name="istearoff"></a>CMFCColorBar::IsTearOff

Указывает, является ли текущая цветовая панель доковой.

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если текущий контроль панели цвета является док-станции; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Если управление цветовой панелью пристыковано, его можно оторвать от панели управления и пристыковать в другом месте.

## <a name="cmfccolorbaronkey"></a><a name="onkey"></a>CMFCColorBar::OnKey

Вызывается по системе, когда пользователь нажимает кнопку клавиатуры.

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>Параметры

*Nchar*<br/>
(в) Код виртуального ключа для ключа, который пользователь нажал.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод обрабатывает указанный ключ; в противном случае, FALSE.

## <a name="cmfccolorbaronsendcommand"></a><a name="onsendcommand"></a>CMFCColorBar::OnsendCommand

Вызывается инфраструктурой, чтобы закрыть иерархию всплывающих элементов управления.

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pButton*|(в) Указатель на элемент управления, который находится на панели инструментов.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

## <a name="cmfccolorbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCColorBar::OnUpdateCmdUI

Вызывается рамкой, чтобы включить или отключить элемент пользовательского интерфейса управления цветовой панелью перед отображением элемента.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
(в) Указатель на окно, содержащее элемент пользовательского интерфейса для обновления.

*bDisableIfNoHndler*<br/>
(в) TRUE для отработки элемента пользовательского интерфейса, если на карте сообщений не определен обработчик; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Когда пользователь приложения нажимает на элемент пользовательского интерфейса, элемент должен знать, следует ли его отображать как включенное или отключенное. Цель сообщения команды предоставляет эту информацию путем реализации ON_UPDATE_COMMAND_UI обработчика команд. Используйте этот метод, чтобы помочь обработать команду. Для получения дополнительной [CCmdUI Class](../../mfc/reference/ccmdui-class.md)информации см.

## <a name="cmfccolorbaropencolordialog"></a><a name="opencolordialog"></a>CMFCColorBar::OpenColorДиалог

Открывает цветную коробку диалога.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Параметры

*colorDefault*<br/>
(в) Цвет, выбранный по умолчанию при открытии цветного диалогового окна.

*colorRes*<br/>
(ваут) Цвет, выбранный пользователем.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если пользователь выбрал цвет; FALSE, если пользователь отменил цвет диалоговые окна.

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbarrebuild"></a><a name="rebuild"></a>CMFCColorBar::Восстановление

Полностью перерисовывает управление цветовой планки.

```
virtual void Rebuild();
```

## <a name="cmfccolorbarselectpalette"></a><a name="selectpalette"></a>CMFCColorBar::SelectPalette

Устанавливает логическую палитру заданного контекста устройства в палитру родительской кнопки текущего управления цветовой панелью.

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pDC*|(в) Указатель на контекст устройства родительской кнопки текущего управления цветовой панелью.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на палитру, которая заменяется палитрой родительской кнопки текущего управления цветовой панелью.

## <a name="cmfccolorbarsetcolor"></a><a name="setcolor"></a>CMFCColorBar::SetColor

Устанавливает выбранный в настоящее время цвет.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение цвета RGB.

## <a name="cmfccolorbarsetcolorname"></a><a name="setcolorname"></a>CMFCColorBar::SetColorName

Устанавливает новое имя для указанного цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение RGB цвета.

*strName*<br/>
(в) Новое название для указанного цвета.

### <a name="remarks"></a>Remarks

Этот метод изменяет имя указанного `CMFCColorBar` цвета во всех объектах приложения.

## <a name="cmfccolorbarsetcommandid"></a><a name="setcommandid"></a>CMFCColorBar::SetCommandID

Устанавливает новый идентификатор команды для управления цветовой панелью.

```cpp
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>Параметры

*nCommandID*<br/>
(в) Идентификатор команды.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы изменить идентификатор команды управления цветовой панелью и уведомить родительское окно элемента управления об изменении идентификатора.

## <a name="cmfccolorbarsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFCColorBar::SetDocumentColors

Устанавливает список цветов, используемых в текущем документе.

```cpp
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>Параметры

*lpszCaption*<br/>
(в) Подпись, которая отображается, когда управление цветовой панелью не пристыковано.

*lstDocColors*<br/>
(в) Список цветов, заменяющие текущие цвета документа.

*bShowWhenDocked*<br/>
(в) TRUE, чтобы показать цвета документов, когда управление цветовой панелью пристыковано; в противном случае, FALSE. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Remarks

*Цвета документов* являются цветами, которые в настоящее время используются в документе. Платформа автоматически поддерживает список цветов документов, но этот метод можно использовать для изменения списка.

## <a name="cmfccolorbarsethorzmargin"></a><a name="sethorzmargin"></a>CMFCColorBar::SetHorzMargin

Устанавливает горизонтальную маржу, которая представляет собой пространство между левой или правой цветовой ячейкой и границей области клиента.

```cpp
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>Параметры

*nHorzMargin*<br/>
(в) Горизонтальная маржа, в пикселях.

### <a name="remarks"></a>Remarks

По умолчанию конструктор [CMFCColorBar::CMFCColorBar](#cmfccolorbar) устанавливает горизонтальную маржу до 4 пикселей.

## <a name="cmfccolorbarsetproplist"></a><a name="setproplist"></a>CMFCColorBar::SetPropList

Устанавливает `m_pWndPropList` защищенный элемент данных в указанный указатель на управление сеткой свойств.

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pWndList*|(в) Указатель на объект управления сеткой свойств.|

## <a name="cmfccolorbarsetvertmargin"></a><a name="setvertmargin"></a>CMFCColorBar::SetVertMargin

Устанавливает вертикальную маржу, которая представляет собой пространство между верхней или нижней цветовой ячейкой и границей области клиента.

```cpp
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>Параметры

*nVertMargin*<br/>
(в) Вертикальная маржа, в пикселях.

### <a name="remarks"></a>Remarks

По умолчанию конструктор [CMFCColorBar::CMFCColorBar](#cmfccolorbar) устанавливает вертикальную маржу до 4 пикселей.

## <a name="cmfccolorbarshowcommandmessagestring"></a><a name="showcommandmessagestring"></a>CMFCColorBar::ShowCommandMessageString

Запросы окна кадра, которому принадлежит элемент управления цветовой панели, для обновления строки сообщения в строке состояния.

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
(в) Идентификатор команды. (Этот параметр игнорируется.)

### <a name="remarks"></a>Remarks

Этот метод отправляет WM_SETMESSAGESTRING сообщение владельцу управления цветовой панели.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
