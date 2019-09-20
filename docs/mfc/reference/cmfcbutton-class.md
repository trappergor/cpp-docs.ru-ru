---
title: Класс Кмфкбуттон
ms.date: 08/28/2018
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
helpviewer_keywords:
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
ms.openlocfilehash: 7628ac353d01c2a6853e35a35bd1f702d3bb041e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505857"
---
# <a name="cmfcbutton-class"></a>Класс Кмфкбуттон

Класс `CMFCButton` добавляет к классу [CButton](../../mfc/reference/cbutton-class.md) функциональные возможности, такие как выровняйте текст кнопки, объединение текста кнопки и изображения, выбор курсора и указание всплывающей подсказки.

## <a name="syntax"></a>Синтаксис

```
class CMFCButton : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CMFCButton::CMFCButton`|Конструктор по умолчанию.|
|`CMFCButton::~CMFCButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфкбуттон:: CleanUp](#cleanup)|Сбрасывает внутренние переменные и освобождает выделенные ресурсы, такие как изображения, точечные рисунки и значки.|
|`CMFCButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCButton::DrawItem`|Вызывается структурой при изменении визуального аспекта рисуемой владельцем кнопки. (Переопределяет [кбуттон::D равитем](../../mfc/reference/cbutton-class.md#drawitem).)|
|[Кмфкбуттон:: Енаблефуллтексттултип](#enablefulltexttooltip)|Указывает, следует ли отображать весь текст подсказки в большом окне подсказки или усеченной версии текста в маленьком окне подсказки.|
|[Кмфкбуттон:: Енаблеменуфонт](#enablemenufont)|Указывает, совпадает ли шрифт текста кнопки с шрифтом меню приложения.|
|[Кмфкбуттон:: Енаблевиндовссеминг](#enablewindowstheming)|Указывает, соответствует ли стиль границы кнопки текущей теме Windows.|
|`CMFCButton::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфкбуттон:: Жеттултипктрл](#gettooltipctrl)|Возвращает ссылку на базовый элемент управления ToolTip.|
|[Кмфкбуттон:: Исауточекк](#isautocheck)|Указывает, является ли флажок или переключатель автоматическим.|
|[Кмфкбуттон:: Исауторепеаткоммандмоде](#isautorepeatcommandmode)|Указывает, настроена ли для кнопки режим автоматического повтора.|
|[Кмфкбуттон:: "CheckBox"](#ischeckbox)|Указывает, является ли кнопка флажком.|
|[Кмфкбуттон:: Check](#ischecked)|Указывает, выбрана ли текущая кнопка.|
|[Кмфкбуттон:: выделять](#ishighlighted)|Указывает, выделяется ли кнопка.|
|[Кмфкбуттон:: нажимает](#ispressed)|Указывает, была ли кнопка нажата и выделена.|
|[Кмфкбуттон:: Push](#ispushed)|Указывает, отправлена ли кнопка.|
|[Кмфкбуттон:: RadioButton](#isradiobutton)|Указывает, является ли кнопка переключателем.|
|[Кмфкбуттон:: Исвиндовссеминженаблед](#iswindowsthemingenabled)|Указывает, соответствует ли стиль границы кнопки текущей теме Windows.|
|`CMFCButton::OnDrawParentBackground`|Рисует фон родителя кнопки в указанной области. (Переопределяет [AFX_GLOBAL_DATA::D равпарентбаккграунд](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|Преобразует сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[Кмфкбуттон:: Сетауторепеатмоде](#setautorepeatmode)|Задает для кнопки режим автоматического повтора.|
|[Кмфкбуттон:: Сетчеккедимаже](#setcheckedimage)|Задает изображение для кнопки с флажком.|
|[Кмфкбуттон:: Сетфацеколор](#setfacecolor)|Задает цвет фона для текста кнопки.|
|[Кмфкбуттон:: Сетимаже](#setimage)|Задает изображение для кнопки.|
|[Кмфкбуттон:: Сетмаусекурсор](#setmousecursor)|Задает изображение курсора.|
|[Кмфкбуттон:: Сетмаусекурсорханд](#setmousecursorhand)|Задает курсор на изображение руки.|
|[Кмфкбуттон:: Сетстдимаже](#setstdimage)|`CMenuImages` Использует объект для задания изображения кнопки.|
|[Кмфкбуттон:: Сеттекстколор](#settextcolor)|Задает цвет текста кнопки для кнопки, которая не выбрана.|
|[Кмфкбуттон:: Сеттекссотколор](#settexthotcolor)|Задает цвет текста кнопки для выбранной кнопки.|
|[Кмфкбуттон:: Сеттултип](#settooltip)|Связывает подсказку с кнопкой.|
|[Кмфкбуттон:: SizeToContent](#sizetocontent)|Изменяет размер кнопки, чтобы она содержала текст и изображение кнопки.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[Кмфкбуттон:: OnDraw](#ondraw)|Вызывается платформой для рисования кнопки.|
|[Кмфкбуттон:: Ондравбордер](#ondrawborder)|Вызывается платформой для рисования границы кнопки.|
|[Кмфкбуттон:: Ондравфокусрект](#ondrawfocusrect)|Вызывается структурой для рисования прямоугольника фокуса для кнопки.|
|[Кмфкбуттон:: Ондравтекст](#ondrawtext)|Вызывается платформой для рисования текста кнопки.|
|[Кмфкбуттон:: Онфиллбаккграунд](#onfillbackground)|Вызывается платформой для отрисовки фона текста кнопки.|
|[Кмфкбуттон:: Селектфонт](#selectfont)|Извлекает шрифт, связанный с указанным контекстом устройства.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[Кмфкбуттон:: m_nAlignStyle](#m_nalignstyle)|Задает выравнивание текста кнопки.|
|[Кмфкбуттон:: m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Указывает, следует ли использовать темы Windows XP.|
|[Кмфкбуттон:: m_bDrawFocus](#m_bdrawfocus)|Указывает, следует ли нарисовать прямоугольник фокуса вокруг кнопки.|
|[Кмфкбуттон:: m_nFlatStyle](#m_nflatstyle)|Задает стиль кнопки, например без рамки, плоской, плоской или трехмерной.|
|[Кмфкбуттон:: m_bGrayDisabled](#m_bGrayDisabled)|Если значение равно TRUE, позволяет рисовать отключенную кнопку как выделенную серым цветом.|
|[Кмфкбуттон:: m_bHighlightChecked](#m_bhighlightchecked)|Указывает, следует ли выделять кнопку в стиле BS_CHECKBOX при наведении на нее курсора.|
|[Кмфкбуттон:: m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|Указывает, следует ли реагировать на события нажатия кнопки.|
|[Кмфкбуттон:: m_bRightImage](#m_brightimage)|Указывает, следует ли отображать изображение с правой стороны кнопки.|
|[Кмфкбуттон:: m_bTopImage](#m_bTopImage)| Указывает, находится ли изображение в верхней части кнопки.|
|[Кмфкбуттон:: m_bTransparent](#m_btransparent)|Указывает, является ли кнопка прозрачной.|
|[Кмфкбуттон:: m_bWasDblClk](#m_bWasDblClk)| Указывает, является ли Последнее событие щелчка двойным щелчком.|

## <a name="remarks"></a>Примечания

Другие типы кнопок являются производными от `CMFCButton` класса, например класса [кмфкурллинкбуттон](../../mfc/reference/cmfclinkctrl-class.md) , который поддерживает гиперссылки, и `CMFCColorButton` класса, поддерживающего диалоговое окно палитры цветов.

Стиль `CMFCButton` объекта может быть *объемным*, *плоским*, *плоским* или не имеющим *границы*. Текст кнопки можно выровнять слева, вверху или в центре кнопки. Во время выполнения можно контролировать, отображает ли кнопка текст, изображение или текст и изображение. Можно также указать, что изображение курсора должно отображаться при наведении курсора мыши на кнопку.

Создайте элемент управления Button либо непосредственно в коде, либо с помощью средства **мастера классов MFC** и шаблона диалогового окна. Если вы создаете элемент управления Button напрямую, добавьте `CMFCButton` переменную в приложение, а затем вызовите конструктор и `Create` методы `CMFCButton` объекта. Если используется **мастер классов MFC**, добавьте `CButton` переменную в приложение, а затем измените тип переменной с `CButton` на `CMFCButton`.

Для обработки сообщений уведомления в приложении диалогового окна Добавьте запись схемы сообщений и обработчик событий для каждого уведомления. Уведомления, отправленные `CMFCButton` объектом, совпадают с отправленными `CButton` объектом.

## <a name="example"></a>Пример

В следующем примере показано, как настроить свойства кнопки с помощью различных методов в `CMFCButton` классе. Пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[кмфкбуттон](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксбуттон. h

##  <a name="cleanup"></a>Кмфкбуттон:: CleanUp

Сбрасывает внутренние переменные и освобождает выделенные ресурсы, такие как изображения, точечные рисунки и значки.

```
virtual void CleanUp();
```

##  <a name="enablefulltexttooltip"></a>Кмфкбуттон:: Енаблефуллтексттултип

Указывает, следует ли отображать весь текст подсказки в большом окне подсказки или усеченной версии текста в маленьком окне подсказки.

```
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>Параметры

*Системе*<br/>
окне Значение TRUE для вывода всего текста; Значение FALSE для вывода усеченного текста.

### <a name="remarks"></a>Примечания

##  <a name="enablemenufont"></a>Кмфкбуттон:: Енаблеменуфонт

Указывает, совпадает ли шрифт текста кнопки с шрифтом меню приложения.

```
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*Системе*<br/>
окне Значение TRUE, чтобы использовать шрифт меню приложения в качестве текстового шрифта кнопки; FALSE для использования системного шрифта. Значение по умолчанию — TRUE.

*bRedraw*<br/>
окне Значение TRUE, чтобы немедленно перерисовывать экран; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Если этот метод не используется для указания шрифта текста кнопки, можно указать шрифт с помощью метода [CWnd:: сетфонт](../../mfc/reference/cwnd-class.md#setfont) . Если шрифт вообще не указан, платформа устанавливает шрифт по умолчанию.

##  <a name="enablewindowstheming"></a>Кмфкбуттон:: Енаблевиндовссеминг

Указывает, соответствует ли стиль границы кнопки текущей теме Windows.

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Значение TRUE, чтобы использовать текущую тему Windows для рисования границ кнопок; Значение FALSE, чтобы не использовать тему Windows. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Этот метод влияет на все кнопки в приложении, которые являются производными `CMFCButton` от класса.

##  <a name="gettooltipctrl"></a>Кмфкбуттон:: Жеттултипктрл

Возвращает ссылку на базовый элемент управления ToolTip.

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на базовый элемент управления ToolTip.

### <a name="remarks"></a>Примечания

##  <a name="isautocheck"></a>Кмфкбуттон:: Исауточекк

Указывает, является ли флажок или переключатель автоматическим.

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если у кнопки есть стиль BS_AUTOCHECKBOX или BS_AUTORADIOBUTTON; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="isautorepeatcommandmode"></a>Кмфкбуттон:: Исауторепеаткоммандмоде

Указывает, настроена ли для кнопки режим автоматического повтора.

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если для кнопки задан режим автоматического повтора; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте метод [кмфкбуттон:: сетауторепеатмоде](#setautorepeatmode) , чтобы задать для кнопки режим автоматического повтора.

##  <a name="ischeckbox"></a>Кмфкбуттон:: "CheckBox"

Указывает, является ли кнопка флажком.

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка имеет стиль BS_CHECKBOX или BS_AUTOCHECKBOX; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="ischecked"></a>Кмфкбуттон:: Check

Указывает, выбрана ли текущая кнопка.

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущая кнопка отмечена флажком; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Платформа использует различные способы для указания того, что проверяются различные виды кнопок. Например, переключатель проверяется, если он содержит точку; установлен флажок, если он содержит значение **X**.

##  <a name="ishighlighted"></a>Кмфкбуттон:: выделять

Указывает, выделяется ли кнопка.

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка выделена; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Кнопка будет выделена при наведении указателя мыши на кнопку.

##  <a name="ispressed"></a>Кмфкбуттон:: нажимает

Указывает, была ли кнопка нажата и выделена.

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка нажата; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="ispushed"></a>Кмфкбуттон:: Push

Указывает, отправлена ли кнопка.

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка нажата; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="isradiobutton"></a>Кмфкбуттон:: RadioButton

Указывает, является ли кнопка переключателем.

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если стиль кнопки — BS_RADIOBUTTON или BS_AUTORADIOBUTTON; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="iswindowsthemingenabled"></a>Кмфкбуттон:: Исвиндовссеминженаблед

Указывает, соответствует ли стиль границы кнопки текущей теме Windows.

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если стиль границы кнопки соответствует текущей теме Windows; в противном случае — значение FALSE.

## <a name="a-namem_bdontusewinxptheme-cmfcbuttonm_bdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/>Кмфкбуттон:: m_bDontUseWinXPTheme

Указывает, следует ли использовать темы Windows XP при рисовании кнопки.

```
BOOL m_bDontUseWinXPTheme;
```

##  <a name="m_bdrawfocus"></a>Кмфкбуттон:: m_bDrawFocus

Указывает, следует ли нарисовать прямоугольник фокуса вокруг кнопки.

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>Примечания

Установите для `m_bDrawFocus` элемента значение true, чтобы указать, что платформа будет рисовать прямоугольник фокуса вокруг текста кнопки и изображения, если кнопка получает фокус.

`CMFCButton` Конструктор инициализирует этот элемент значением true.

##  <a name="m_bGrayDisabled"></a>Кмфкбуттон:: m_bGrayDisabled

Если значение равно TRUE, позволяет рисовать отключенную кнопку как выделенную серым цветом.

```
BOOL m_bGrayDisabled;
```

##  <a name="m_bhighlightchecked"></a>Кмфкбуттон:: m_bHighlightChecked

Указывает, следует ли выделять кнопку в стиле BS_CHECKBOX при наведении на нее курсора.

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>Примечания

Присвойте `m_bHighlightChecked` элементу значение true, чтобы указать, что платформа выделит кнопку BS_CHECKBOX-Style при наведении на нее указателя мыши.

##  <a name="m_bResponseOnButtonDown"></a>Кмфкбуттон:: m_bResponseOnButtonDown

Указывает, следует ли реагировать на события нажатия кнопки.

```
BOOL m_bResponseOnButtonDown;
```

##  <a name="m_brightimage"></a>Кмфкбуттон:: m_bRightImage

Указывает, следует ли отображать изображение с правой стороны кнопки.

```
BOOL m_bRightImage;
```

##  <a name="m_bTopImage"></a>Кмфкбуттон:: m_bTopImage] (#m_bTopImage)

Указывает, находится ли изображение в верхней части кнопки.

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>Примечания

Присвойте `m_bRightImage` элементу значение true, чтобы указать, что платформа будет отображать изображение кнопки справа от текстовой метки кнопки.

##  <a name="m_btransparent"></a>Кмфкбуттон:: m_bTransparent

Указывает, является ли кнопка прозрачной.

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>Примечания

Присвойте `m_bTransparent` элементу значение true, чтобы указать, что платформа сделает эту кнопку прозрачной. `CMFCButton` Конструктор инициализирует этот элемент значением false.

##  <a name="m_nalignstyle"></a>Кмфкбуттон:: m_nAlignStyle

Задает выравнивание текста кнопки.

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>Примечания

Используйте одно из следующих `CMFCButton::AlignStyle` значений перечисления, чтобы указать выравнивание текста кнопки:

|Значение|Описание|
|-----------|-----------------|
|ALIGN_CENTER|Параметры Выравнивает текст кнопки по центру кнопки.|
|ALIGN_LEFT|Выровняйте текст кнопки по левой стороне кнопки.|
|ALIGN_RIGHT|Выровняйте текст кнопки по правой стороне кнопки.|

`CMFCButton` Конструктор инициализирует этот элемент как ALIGN_CENTER.

##  <a name="m_bWasDblClk"></a>Кмфкбуттон:: m_bWasDblClk] (#m_bWasDblClk) |

Указывает, является ли Последнее событие щелчка двойным щелчком. |

```
BOOL m_bWasDblClk;
```

##  <a name="m_nflatstyle"></a>Кмфкбуттон:: m_nFlatStyle

Задает стиль кнопки, например без рамки, плоской, плоской или трехмерной.

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>Примечания

В следующей таблице перечислены `CMFCButton::m_nFlatStyle` значения перечисления, определяющие внешний вид кнопки.

|Значение|Описание|
|-----------|-----------------|
|BUTTONSTYLE_3D|Параметры Кнопка имеет высокую трехмерную сторону. При нажатии кнопки появляется кнопка, которая была нажата на более глубокий отступ.|
|BUTTONSTYLE_FLAT|Когда мышь не задерживается над кнопкой, она выглядит как двухмерная и не имеет призываемых сторон. При наведении указателя мыши на кнопку появляется кнопка с низкими трехмерными сторонами. При нажатии кнопки кнопка отображается в неполном отступе.|
|BUTTONSTYLE_SEMIFLAT|Кнопка имеет низкую трехмерную сторону. При нажатии кнопки появляется кнопка, которая была нажата на более глубокий отступ.|
|BUTTONSTYLE_NOBORDERS|У кнопки нет призываемых сторон и всегда отображается двухмерный. Кнопка не отображается при нажатии на отступ.|

`CMFCButton` Конструктор инициализирует этот элемент как BUTTONSTYLE_3D.

### <a name="example"></a>Пример

В следующем примере показано, как задать значения `m_nFlatStyle` переменной члена `CMFCButton` в классе. Этот пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

##  <a name="ondraw"></a>Кмфкбуттон:: OnDraw

Вызывается платформой для рисования кнопки.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

*rect*<br/>
окне Ссылка на прямоугольник, ограничивающий кнопку.

*уистате*<br/>
окне Текущее состояние кнопки. Дополнительные сведения см. в `itemState` разделе, посвященном элементу [структуры дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) .

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования кнопки.

##  <a name="ondrawborder"></a>Кмфкбуттон:: Ондравбордер

Вызывается платформой для рисования границы кнопки.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

*ректклиент*<br/>
окне Ссылка на прямоугольник, ограничивающий кнопку.

*уистате*<br/>
окне Текущее состояние кнопки. Дополнительные сведения см. в `itemState` разделе, посвященном элементу [структуры дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) .

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования границы.

##  <a name="ondrawfocusrect"></a>Кмфкбуттон:: Ондравфокусрект

Вызывается структурой для рисования прямоугольника фокуса для кнопки.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

*ректклиент*<br/>
окне Ссылка на прямоугольник, ограничивающий кнопку.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования прямоугольника фокуса.

##  <a name="ondrawtext"></a>Кмфкбуттон:: Ондравтекст

Вызывается платформой для рисования текста кнопки.

```
virtual void OnDrawText(
    CDC* pDC,
    const CRect& rect,
    const CString& strText,
    UINT uiDTFlags,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

*rect*<br/>
окне Ссылка на прямоугольник, ограничивающий кнопку.

*стртекст*<br/>
окне Текст для рисования.

*уидтфлагс*<br/>
окне Флаги, определяющие способ форматирования текста. Дополнительные сведения см. в описании параметра *нформат* метода [CDC::D равтекст](../../mfc/reference/cdc-class.md#drawtext) .

*уистате*<br/>
[in] Зарезервировано.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для отрисовки текста кнопки.

##  <a name="onfillbackground"></a>Кмфкбуттон:: Онфиллбаккграунд

Вызывается платформой для отрисовки фона текста кнопки.

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

*ректклиент*<br/>
окне Ссылка на прямоугольник, ограничивающий кнопку.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования фона кнопки.

##  <a name="selectfont"></a>Кмфкбуттон:: Селектфонт

Извлекает шрифт, связанный с указанным контекстом устройства.

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

### <a name="return-value"></a>Возвращаемое значение

Переопределите этот метод, чтобы использовать собственный код для получения шрифта.

### <a name="remarks"></a>Примечания

##  <a name="setautorepeatmode"></a>Кмфкбуттон:: Сетауторепеатмоде

Задает для кнопки режим автоматического повтора.

```
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>Параметры

*нтимеделай*<br/>
окне Неотрицательное число, указывающее интервал между сообщениями, отправляемыми родительскому окну. Интервал измеряется в миллисекундах, а его значение по умолчанию — 500 миллисекунд. Укажите ноль, чтобы отключить режим автоматического повторного сообщения.

### <a name="remarks"></a>Примечания

Этот метод заставляет кнопку постоянно отсылать сообщения WM_COMMAND в родительское окно, пока кнопка не будет выпущена, или параметр *нтимеделай* имеет значение 0.

##  <a name="setcheckedimage"></a>Кмфкбуттон:: Сетчеккедимаже

Задает изображение для кнопки с флажком.

```
void SetCheckedImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetCheckedImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetCheckedImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
окне Обработчик значка, который содержит точечный рисунок и маску для нового изображения.

*баутодестрой*<br/>
окне Значение TRUE, чтобы указать, что ресурсы растрового изображения уничтожаются автоматически; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

*хиконхот*<br/>
окне Обработчик значка, который содержит изображение для выбранного состояния.

*хбитмап*<br/>
окне Обрабатывайте точечный рисунок, содержащий изображение для невыбранного состояния.

*хбитмафот*<br/>
окне Маркер для растрового изображения, содержащего изображение для выбранного состояния.

*bMap3dColors*<br/>
окне Задает прозрачный цвет для фона кнопки; то есть, лицевой кнопкой. Значение TRUE, чтобы использовать значение цвета RGB (192, 192, 192); Значение FALSE, чтобы использовать значение цвета, `AFX_GLOBAL_DATA::clrBtnFace`определенное параметром.

*уибмпресид*<br/>
окне Идентификатор ресурса для невыбранного изображения.

*уибмфотресид*<br/>
окне Идентификатор ресурса для выбранного образа.

*хикондисаблед*<br/>
окне Обработчик значка для отключенного изображения.

*хбитмапдисаблед*<br/>
окне Обрабатывайте точечный рисунок, содержащий отключенный образ.

*уибмпдсблресид*<br/>
окне Идентификатор ресурса отключенного точечного рисунка.

*балфабленд*<br/>
окне Значение TRUE, чтобы использовать только 32-битные изображения, использующие альфа-канал; Значение FALSE, чтобы не использовать только изображения альфа-канала. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

##  <a name="setfacecolor"></a>Кмфкбуттон:: Сетфацеколор

Задает цвет фона для текста кнопки.

```
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*крфаце*<br/>
окне Значение цвета RGB.

*bRedraw*<br/>
окне Значение TRUE, чтобы перерисовать экран немедленно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы определить новый цвет заливки для фона кнопки (лицевой стороны). Обратите внимание, что фон не заполняется, когда переменная-член [кмфкбуттон:: m_bTransparent](#m_btransparent) имеет значение true.

##  <a name="setimage"></a>Кмфкбуттон:: Сетимаже

Задает изображение для кнопки.

```
void SetImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
окне Обработчик значка, который содержит точечный рисунок и маску для нового изображения.

*баутодестрой*<br/>
окне Значение TRUE, чтобы указать, что ресурсы растрового изображения уничтожаются автоматически; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

*хиконхот*<br/>
окне Обработчик значка, который содержит изображение для выбранного состояния.

*хбитмап*<br/>
окне Обрабатывайте точечный рисунок, содержащий изображение для невыбранного состояния.

*хбитмафот*<br/>
окне Маркер для растрового изображения, содержащего изображение для выбранного состояния.

*уибмпресид*<br/>
окне Идентификатор ресурса для невыбранного изображения.

*уибмфотресид*<br/>
окне Идентификатор ресурса для выбранного образа.

*bMap3dColors*<br/>
окне Задает прозрачный цвет для фона кнопки; то есть, лицевой кнопкой. Значение TRUE, чтобы использовать значение цвета RGB (192, 192, 192); Значение FALSE, чтобы использовать значение цвета, `AFX_GLOBAL_DATA::clrBtnFace`определенное параметром.

*хикондисаблед*<br/>
окне Обработчик значка для отключенного изображения.

*хбитмапдисаблед*<br/>
окне Обрабатывайте точечный рисунок, содержащий отключенный образ.

*уибмпдсблресид*<br/>
окне Идентификатор ресурса отключенного точечного рисунка.

*балфабленд*<br/>
окне Значение TRUE, чтобы использовать только 32-битные изображения, использующие альфа-канал; Значение FALSE, чтобы не использовать только изображения альфа-канала. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере показано, как использовать различные версии `SetImage` метода `CMFCButton` в классе. Пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

##  <a name="setmousecursor"></a>Кмфкбуттон:: Сетмаусекурсор

Задает изображение курсора.

```
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>Параметры

*хкурсор*<br/>
окне Указатель курсора.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы связать изображение курсора, например курсор руки, с кнопкой. Курсор загружается из ресурсов приложения.

### <a name="example"></a>Пример

В следующем примере показано, `SetMouseCursor` как использовать метод `CMFCButton` в классе. Пример является частью кода в [примере New Controls](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

##  <a name="setmousecursorhand"></a>Кмфкбуттон:: Сетмаусекурсорханд

Задает курсор на изображение руки.

```
void SetMouseCursorHand();
```

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы связать изображение руки с кнопкой. Курсор загружается из ресурсов приложения.

##  <a name="setstdimage"></a>Кмфкбуттон:: Сетстдимаже

`CMenuImages` Использует объект для задания изображения кнопки.

```
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>Параметры

*id*<br/>
окне Один из идентификаторов изображения кнопки, определенный в `CMenuImage::IMAGES_IDS` перечислении. В значениях изображения указываются изображения, такие как стрелки, ПИН-коды и переключатели.

*state*<br/>
окне Один из идентификаторов состояния изображения кнопки, определенный в `CMenuImages::IMAGE_STATE` перечислении. Изображение указывает цвета кнопки: черный, серый, светло-серый, белый и темно-серый. Значение по умолчанию — `CMenuImages::ImageBlack`.

*иддисаблед*<br/>
окне Один из идентификаторов изображения кнопки, определенный в `CMenuImage::IMAGES_IDS` перечислении. Изображение указывает, что кнопка отключена. Значение по умолчанию — изображение первой кнопки ( `CMenuImages::IdArrowDown`).

### <a name="remarks"></a>Примечания

##  <a name="settextcolor"></a>Кмфкбуттон:: Сеттекстколор

Задает цвет текста кнопки для кнопки, которая не выбрана.

```
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>Параметры

*клртекст*<br/>
окне Значение цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="settexthotcolor"></a>Кмфкбуттон:: Сеттекссотколор

Задает цвет текста кнопки для выбранной кнопки.

```
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>Параметры

*клртекссот*<br/>
окне Значение цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="settooltip"></a>Кмфкбуттон:: Сеттултип

Связывает подсказку с кнопкой.

```
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>Параметры

*лпсзтултиптекст*<br/>
окне Указатель на текст подсказки. Укажите значение NULL, чтобы отключить подсказку.

### <a name="remarks"></a>Примечания

##  <a name="sizetocontent"></a>Кмфкбуттон:: SizeToContent

Изменяет размер кнопки, чтобы она содержала текст и изображение кнопки.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Параметры

*бкалконли*<br/>
окне Значение TRUE, чтобы вычислить, но не изменять новый размер кнопки; Значение FALSE, чтобы изменить размер кнопки. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

`CSize` Объект, содержащий новый размер кнопки.

### <a name="remarks"></a>Примечания

По умолчанию этот метод вычисляет новый размер, включающий горизонтальное поле размером 10 пикселей, и вертикальное поле размером 5 пикселей.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[Класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)
