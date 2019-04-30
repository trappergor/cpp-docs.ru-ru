---
title: Класс CMFCButton
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
ms.openlocfilehash: 0659e5335e1ebc495280a4e0cb5c0167f3b45e1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403832"
---
# <a name="cmfcbutton-class"></a>Класс CMFCButton

`CMFCButton` Класс расширяет его функциональные возможности [CButton](../../mfc/reference/cbutton-class.md) класс, например выравнивание текста кнопки, объединение текста кнопки и изображения, выбор курсора и задание подсказки.

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
|[CMFCButton::CleanUp](#cleanup)|Сбрасывает внутренних переменных и высвобождает выделенные ресурсы, такие как изображения, точечные рисунки и значки.|
|`CMFCButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCButton::DrawItem`|Вызывается платформой при изменении вида определяемая владельцем кнопка. (Переопределяет [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Указывает, следует ли отображать полный текст всплывающей подсказки в окно всплывающей подсказки больших или используется сокращенная версия текста в окно небольшой всплывающей подсказки.|
|[CMFCButton::EnableMenuFont](#enablemenufont)|Указывает, является ли шрифт текста кнопки так же, как шрифт меню приложения.|
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Указывает, соответствует ли стиль границы кнопки текущей темы Windows.|
|`CMFCButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Возвращает ссылку на базовый элемент управления tooltip.|
|[CMFCButton::IsAutoCheck](#isautocheck)|Указывает, является ли флажок или переключатель автоматической кнопки.|
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Показывает, задан ли кнопки в режим автоматического повтора.|
|[CMFCButton::IsCheckBox](#ischeckbox)|Указывает, является ли кнопки кнопки "флажок".|
|[CMFCButton::IsChecked](#ischecked)|Указывает, проверяется ли текущей кнопки.|
|[CMFCButton::IsHighlighted](#ishighlighted)|Указывает, выделена ли кнопки.|
|[CMFCButton::IsPressed](#ispressed)|Указывает ли кнопка отправлено и выделены.|
|[CMFCButton::IsPushed](#ispushed)|Указывает, помещается ли кнопки.|
|[CMFCButton::IsRadioButton](#isradiobutton)|Указывает, является ли кнопка типа "переключатель".|
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Указывает, соответствует ли стиль границы кнопки текущей темы Windows.|
|`CMFCButton::OnDrawParentBackground`|Рисует фон родительского объекта в заданной области. (Переопределяет [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Задает кнопку в режим автоматического повтора.|
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Задает изображение для нажатой кнопки.|
|[CMFCButton::SetFaceColor](#setfacecolor)|Задает цвет фона для текста кнопки.|
|[CMFCButton::SetImage](#setimage)|Задает изображение для кнопки.|
|[CMFCButton::SetMouseCursor](#setmousecursor)|Задает изображение курсора.|
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|Задает курсор к образу руки.|
|[CMFCButton::SetStdImage](#setstdimage)|Использует `CMenuImages` объекта, чтобы задать изображение кнопки.|
|[CMFCButton::SetTextColor](#settextcolor)|Задает цвет текста кнопки для кнопки, которая не выбрана.|
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Задает цвет текста кнопки для кнопки, который выбран.|
|[CMFCButton::SetTooltip](#settooltip)|Связывает всплывающей подсказки с кнопкой.|
|[CMFCButton::SizeToContent](#sizetocontent)|Изменение размера кнопки должен содержать текст кнопки и изображения.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CMFCButton::OnDraw](#ondraw)|Вызвано структурой для отображения кнопки.|
|[CMFCButton::OnDrawBorder](#ondrawborder)|Вызывается платформой для рисования границы кнопки.|
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Вызывается платформой для отрисовки прямоугольника фокуса для кнопки.|
|[CMFCButton::OnDrawText](#ondrawtext)|Вызывается платформой для рисования текста кнопки.|
|[CMFCButton::OnFillBackground](#onfillbackground)|Вызывается платформой для рисования фона текста кнопки.|
|[CMFCButton::SelectFont](#selectfont)|Получает шрифт, который связан с помощью заданного контекста устройств.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Задает выравнивание текста кнопки.|
|[CMFCButton::m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Указывает, следует ли использовать темы Windows XP.|
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Указывает, следует ли нарисовать прямоугольник фокуса вокруг кнопки.|
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Задает стиль кнопки, например без рамки, плоский, с плоского или 3D.|
|[CMFCButton::m_bGrayDisabled](#m_bGrayDisabled)|Если значение равно TRUE, включает кнопку в отключенном состоянии которые изображаются в виде закрашены серым.|
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Указывает, следует ли выделять BS_CHECKBOX-стиль кнопки при наведении курсора.|
|[CMFCButton::m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|Указывает, следует ли реагировать на события нажатия кнопки.|
|[CMFCButton::m_bRightImage](#m_brightimage)|Указывает, следует ли отображать изображение справа от кнопки.|
|[CMFCButton::m_bTopImage](#m_bTopImage)| Указывает, является ли изображение поверх кнопки.|
|[CMFCButton::m_bTransparent](#m_btransparent)|Указывает, является ли кнопка прозрачным.|
|[CMFCButton::m_bWasDblClk](#m_bWasDblClk)| Указывает, было ли последний щелкните событие двойным щелчком.|

## <a name="remarks"></a>Примечания

Другие типы кнопок являются производными от `CMFCButton` класс, например [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) класс, который поддерживает гиперссылки, и `CMFCColorButton` класс, который поддерживает диалоговое окно выбора цвета.

Стиль `CMFCButton` объект может быть *3D*, *неструктурированный*, *точка с фиксированной* или *граница не*. Текст кнопки могут быть выровнены в левой, верхней или center кнопки. Во время выполнения вы можете управлять ли кнопка отображает текст, изображения, или текст и изображения. Можно также указать отображение образ конкретного курсора при наведении курсора на кнопку.

Создание элемента управления кнопки, либо непосредственно в коде, либо с помощью **мастер классов MFC** средство и шаблон диалогового окна. При создании непосредственно управления "Кнопка" Добавить `CMFCButton` переменных для вашего приложения, а затем вызовите конструктор и `Create` методы `CMFCButton` объекта. Если вы используете **мастер классов MFC**, добавьте `CButton` переменных для вашего приложения и измените тип переменной из `CButton` для `CMFCButton`.

Для обработки сообщений уведомления в приложении поле диалогового окна необходимо добавьте запись сопоставления сообщения и обработчик событий для каждого уведомления. Уведомления, отправленные `CMFCButton` имеют такие же, как отправленные `CButton` объекта.

## <a name="example"></a>Пример

Следующий пример демонстрирует настройку свойств кнопки с помощью различных методов в `CMFCButton` класса. Пример является частью [пример новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbutton.h

##  <a name="cleanup"></a>  CMFCButton::CleanUp

Сбрасывает внутренних переменных и высвобождает выделенные ресурсы, такие как изображения, точечные рисунки и значки.

```
virtual void CleanUp();
```

##  <a name="enablefulltexttooltip"></a>  CMFCButton::EnableFullTextTooltip

Указывает, следует ли отображать полный текст всплывающей подсказки в окно всплывающей подсказки больших или используется сокращенная версия текста в окно небольшой всплывающей подсказки.

```
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>Параметры

*bOn*<br/>
[in] Значение TRUE, чтобы отобразить весь текст; Значение FALSE, чтобы усечены отображаемый текст.

### <a name="remarks"></a>Примечания

##  <a name="enablemenufont"></a>  CMFCButton::EnableMenuFont

Указывает, является ли шрифт текста кнопки так же, как шрифт меню приложения.

```
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*bOn*<br/>
[in] Значение TRUE, чтобы использовать шрифт меню приложения в качестве шрифта текста кнопки; Значение FALSE, чтобы использовать системный шрифт. Значение по умолчанию — TRUE.

*bRedraw*<br/>
[in] Значение TRUE, чтобы немедленно перерисовывает экрана; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Если вы не используете этот метод указание шрифта текста кнопки, можно указать шрифт с [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) метод. Если вы не укажете шрифта вообще, платформа присваивает шрифт по умолчанию.

##  <a name="enablewindowstheming"></a>  CMFCButton::EnableWindowsTheming

Указывает, соответствует ли стиль границы кнопки текущей темы Windows.

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE, чтобы использовать текущую тему Windows для рисования границы кнопки; Значение FALSE, чтобы не использовать тему Windows. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Этот метод влияет на все кнопки приложения, которые являются производными от `CMFCButton` класса.

##  <a name="gettooltipctrl"></a>  CMFCButton::GetToolTipCtrl

Возвращает ссылку на базовый элемент управления tooltip.

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на базовый элемент управления tooltip.

### <a name="remarks"></a>Примечания

##  <a name="isautocheck"></a>  CMFCButton::IsAutoCheck

Указывает, является ли флажок или переключатель автоматической кнопки.

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка имеет стиль BS_AUTOCHECKBOX или BS_AUTORADIOBUTTON; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="isautorepeatcommandmode"></a>  CMFCButton::IsAutorepeatCommandMode

Показывает, задан ли кнопки в режим автоматического повтора.

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопки будет переведена в режим auto-repeat; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте [CMFCButton::SetAutorepeatMode](#setautorepeatmode) метод Установка режима auto-repeat кнопки.

##  <a name="ischeckbox"></a>  CMFCButton::IsCheckBox

Указывает, является ли кнопки кнопки "флажок".

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка имеет BS_CHECKBOX или BS_AUTOCHECKBOX стиля; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="ischecked"></a>  CMFCButton::IsChecked

Указывает, проверяется ли текущей кнопки.

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если установлен параметр текущей кнопки; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Инфраструктура использует различные способы указания, что возвращены различные виды кнопок. Например типа "переключатель" проверяется, если он содержит точку; Когда в ней установлен флажок **X**.

##  <a name="ishighlighted"></a>  CMFCButton::IsHighlighted

Указывает, выделена ли кнопки.

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка выделена; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Кнопка выделяется при наведении указателя мыши на кнопку.

##  <a name="ispressed"></a>  CMFCButton::IsPressed

Указывает ли кнопка отправлено и выделены.

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если при нажатии кнопки; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="ispushed"></a>  CMFCButton::IsPushed

Указывает, помещается ли кнопки.

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопки помещается; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="isradiobutton"></a>  CMFCButton::IsRadioButton

Указывает, является ли кнопка типа "переключатель".

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если стиль кнопки BS_RADIOBUTTON или BS_AUTORADIOBUTTON; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="iswindowsthemingenabled"></a>  CMFCButton::IsWindowsThemingEnabled

Указывает, соответствует ли стиль границы кнопки текущей темы Windows.

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если стиль границы кнопки соответствует текущей темы Windows; в противном случае — значение FALSE.

## <a name="a-namembdontusewinxptheme-cmfcbuttonmbdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/> CMFCButton::m_bDontUseWinXPTheme

Указывает, следует ли использовать темы Windows XP при рисовании кнопки.

```
BOOL m_bDontUseWinXPTheme;
```

##  <a name="m_bdrawfocus"></a>  CMFCButton::m_bDrawFocus

Указывает, следует ли нарисовать прямоугольник фокуса вокруг кнопки.

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>Примечания

Задайте `m_bDrawFocus` член значение TRUE, чтобы указать, что платформа будет прямоугольник фокуса вокруг текст кнопки и изображения, если кнопка получает фокус.

`CMFCButton` Конструктор инициализирует этот член значение true.

##  <a name="m_bGrayDisabled"></a>  CMFCButton::m_bGrayDisabled

Если значение равно TRUE, включает кнопку в отключенном состоянии которые изображаются в виде закрашены серым.

```
BOOL m_bGrayDisabled;
```

##  <a name="m_bhighlightchecked"></a>  CMFCButton::m_bHighlightChecked

Указывает, следует ли выделять BS_CHECKBOX-стиль кнопки при наведении курсора.

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>Примечания

Задайте `m_bHighlightChecked` член значение true, чтобы указать, что платформа будет выделено BS_CHECKBOX-стиль кнопки при наведении указателя мыши.

##  <a name="m_bResponseOnButtonDown"></a> CMFCButton::m_bResponseOnButtonDown

Указывает, следует ли реагировать на события нажатия кнопки.

```
BOOL m_bResponseOnButtonDown;
```

##  <a name="m_brightimage"></a>  CMFCButton::m_bRightImage

Указывает, следует ли отображать изображение справа от кнопки.

```
BOOL m_bRightImage;
```

##  <a name="m_bTopImage"></a>  CMFCButton::m_bTopImage](#m_bTopImage)

Указывает, является ли изображение поверх кнопки.

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>Примечания

Задайте `m_bRightImage` член значение true, чтобы указать, что платформа будет отображаться изображение кнопки справа от кнопки текстовую метку.

##  <a name="m_btransparent"></a>  CMFCButton::m_bTransparent

Указывает, является ли кнопка прозрачным.

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>Примечания

Задайте `m_bTransparent` член значение true, чтобы указать, что платформа будет прозрачной кнопки. `CMFCButton` Конструктор инициализирует этот элемент, значение false.

##  <a name="m_nalignstyle"></a>  CMFCButton::m_nAlignStyle

Задает выравнивание текста кнопки.

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>Примечания

Используйте один из следующих `CMFCButton::AlignStyle` значений перечисления, чтобы задать выравнивание текста кнопки:

|Значение|Описание|
|-----------|-----------------|
|ALIGN_CENTER|(По умолчанию) Выравнивание текста кнопки в центр кнопки.|
|ALIGN_LEFT|Кнопка текст выравнивается по левой кнопки.|
|ALIGN_RIGHT|Кнопка текст выравнивается по правой части кнопки.|

`CMFCButton` Конструктор инициализирует этот член для ALIGN_CENTER.

##  <a name="m_bWasDblClk"></a>  CMFCButton::m_bWasDblClk](#m_bWasDblClk) |

Указывает, была ли последний щелкните событие двойным щелчком. |

```
BOOL m_bWasDblClk;
```

##  <a name="m_nflatstyle"></a>  CMFCButton::m_nFlatStyle

Задает стиль кнопки, например без рамки, плоский, с плоского или 3D.

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>Примечания

В следующей таблице перечислены `CMFCButton::m_nFlatStyle` значений перечисления, определяющих внешний вид кнопки.

|Значение|Описание|
|-----------|-----------------|
|BUTTONSTYLE_3D|(По умолчанию) Кнопка для высокого уровня, трехмерного стороны. При нажатии кнопки, кнопка нажимаемые в глубокого отступа.|
|BUTTONSTYLE_FLAT|Когда указатель мыши не задержите кнопки, кнопки кажется двухмерной и не имеет вызванное сторон. Когда указатель мыши находится над кнопкой, кнопка на низкий, трехмерного стороны. При нажатии кнопки, кнопка нажимаемые в неполную отступа.|
|BUTTONSTYLE_SEMIFLAT|По-видимому, низкий, трехмерного стороны кнопки. При нажатии кнопки, кнопка нажимаемые в глубокого отступа.|
|BUTTONSTYLE_NOBORDERS|Кнопка не сообщили сторон и всегда отображается двухмерный. Нажатие в отступ при нажатии кнопки не отображается.|

`CMFCButton` Конструктор инициализирует этот член для BUTTONSTYLE_3D.

### <a name="example"></a>Пример

Следующий пример демонстрирует задайте значения свойств `m_nFlatStyle` переменную-член в `CMFCButton` класса. Этот пример является частью [пример новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

##  <a name="ondraw"></a>  CMFCButton::OnDraw

Вызвано структурой для отображения кнопки.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rect*<br/>
[in] Ссылка на прямоугольник, ограничивающий кнопки.

*uiState*<br/>
[in] Текущее состояние кнопки. Дополнительные сведения см. в разделе `itemState` членом [drawitemstruct-структура](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) раздела.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для отображения кнопки.

##  <a name="ondrawborder"></a>  CMFCButton::OnDrawBorder

Вызывается платформой для рисования границы кнопки.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rectClient*<br/>
[in] Ссылка на прямоугольник, ограничивающий кнопки.

*uiState*<br/>
[in] Текущее состояние кнопки. Дополнительные сведения см. в разделе `itemState` членом [drawitemstruct-структура](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) раздела.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования границы.

##  <a name="ondrawfocusrect"></a>  CMFCButton::OnDrawFocusRect

Вызывается платформой для отрисовки прямоугольника фокуса для кнопки.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rectClient*<br/>
[in] Ссылка на прямоугольник, ограничивающий кнопки.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования прямоугольника фокуса.

##  <a name="ondrawtext"></a>  CMFCButton::OnDrawText

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
[in] Указатель на контекст устройства.

*rect*<br/>
[in] Ссылка на прямоугольник, ограничивающий кнопки.

*strText*<br/>
[in] Текст для рисования.

*uiDTFlags*<br/>
[in] Флаги, определяющие способ форматирования текста. Дополнительные сведения см. в разделе *nFormat* параметр [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) метод.

*uiState*<br/>
[in] Зарезервировано.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования текста кнопки.

##  <a name="onfillbackground"></a>  CMFCButton::OnFillBackground

Вызывается платформой для рисования фона текста кнопки.

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rectClient*<br/>
[in] Ссылка на прямоугольник, ограничивающий кнопки.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы использовать собственный код для рисования фона кнопки.

##  <a name="selectfont"></a>  CMFCButton::SelectFont

Получает шрифт, который связан с помощью заданного контекста устройств.

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

### <a name="return-value"></a>Возвращаемое значение

Переопределите этот метод, чтобы использовать собственный код для получения шрифта.

### <a name="remarks"></a>Примечания

##  <a name="setautorepeatmode"></a>  CMFCButton::SetAutorepeatMode

Задает кнопку в режим автоматического повтора.

```
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>Параметры

*nTimeDelay*<br/>
[in] Неотрицательное число, задающее интервал между сообщений, отправленных в родительское окно. Интервал измеряется в миллисекундах, и значение по умолчанию — 500 миллисекунд. Укажите ноль, чтобы отключить режим auto-repeat сообщений.

### <a name="remarks"></a>Примечания

Этот метод приводит к постоянно отправлять сообщения WM_COMMAND родительского окна, пока не освобождается кнопки, кнопки или *nTimeDelay* параметра, равным нулю.

##  <a name="setcheckedimage"></a>  CMFCButton::SetCheckedImage

Задает изображение для нажатой кнопки.

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
[in] Дескриптор значок, который содержит растровое изображение и маску для нового образа.

*bAutoDestroy*<br/>
[in] Значение TRUE, чтобы указать, что точечный рисунок ресурсы будут уничтожены автоматически. в противном случае — значение FALSE. Значение по умолчанию — TRUE.

*hIconHot*<br/>
[in] Дескриптор значок, который содержит изображение, чтобы выбранном состоянии.

*hBitmap*<br/>
[in] Дескриптор точечного рисунка, который содержит изображение для его состояние не выбран.

*hBitmapHot*<br/>
[in] Дескриптор точечного рисунка, который содержит изображение, чтобы выбранном состоянии.

*bMap3dColors*<br/>
[in] Указывает прозрачный цвет для фона кнопки; то есть поверхности кнопки. Значение TRUE, чтобы использовать значение цвета RGB (192, 192, 192); Значение FALSE, чтобы использовать значение цвета, определяемые `AFX_GLOBAL_DATA::clrBtnFace`.

*uiBmpResId*<br/>
[in] Идентификатор ресурса для невыбранным изображением.

*uiBmpHotResId*<br/>
[in] Идентификатор ресурса для выбранного образа.

*hIconDisabled*<br/>
[in] Дескриптор значка для отключенного рисунка.

*hBitmapDisabled*<br/>
[in] Дескриптор точечного рисунка, который содержит изображение отключено.

*uiBmpDsblResID*<br/>
[in] Идентификатор ресурса точечного рисунка, отключено.

*bAlphaBlend*<br/>
[in] Значение true, чтобы использовать только 32-разрядные образы, использующие альфа-канала; Значение равно FALSE, чтобы не использовать образы только альфа-канала. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

##  <a name="setfacecolor"></a>  CMFCButton::SetFaceColor

Задает цвет фона для текста кнопки.

```
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*crFace*<br/>
[in] Значение цвета RGB.

*bRedraw*<br/>
[in] Значение TRUE, чтобы обновить экран немедленно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод позволяет определить новый цвет заливки для фона кнопки (лиц). Обратите внимание, что фон не будет заполнен при [CMFCButton::m_bTransparent](#m_btransparent) переменной-члена имеет значение TRUE.

##  <a name="setimage"></a>  CMFCButton::SetImage

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
[in] Дескриптор значок, который содержит растровое изображение и маску для нового образа.

*bAutoDestroy*<br/>
[in] Значение TRUE, чтобы указать, что точечный рисунок ресурсы будут уничтожены автоматически. в противном случае — значение FALSE. Значение по умолчанию — TRUE.

*hIconHot*<br/>
[in] Дескриптор значок, который содержит изображение, чтобы выбранном состоянии.

*hBitmap*<br/>
[in] Дескриптор точечного рисунка, который содержит изображение для его состояние не выбран.

*hBitmapHot*<br/>
[in] Дескриптор точечного рисунка, который содержит изображение, чтобы выбранном состоянии.

*uiBmpResId*<br/>
[in] Идентификатор ресурса для невыбранным изображением.

*uiBmpHotResId*<br/>
[in] Идентификатор ресурса для выбранного образа.

*bMap3dColors*<br/>
[in] Указывает прозрачный цвет для фона кнопки; то есть поверхности кнопки. Значение TRUE, чтобы использовать значение цвета RGB (192, 192, 192); Значение FALSE, чтобы использовать значение цвета, определяемые `AFX_GLOBAL_DATA::clrBtnFace`.

*hIconDisabled*<br/>
[in] Дескриптор значка для отключенного рисунка.

*hBitmapDisabled*<br/>
[in] Дескриптор точечного рисунка, который содержит изображение отключено.

*uiBmpDsblResID*<br/>
[in] Идентификатор ресурса точечного рисунка, отключено.

*bAlphaBlend*<br/>
[in] Значение true, чтобы использовать только 32-разрядные образы, использующие альфа-канала; Значение равно FALSE, чтобы не использовать образы только альфа-канала. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

Следующий пример демонстрирует способы использования различных версий `SetImage` метод в `CMFCButton` класса. Пример является частью [пример новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

##  <a name="setmousecursor"></a>  CMFCButton::SetMouseCursor

Задает изображение курсора.

```
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>Параметры

*hcursor*<br/>
[in] Дескриптор курсора.

### <a name="remarks"></a>Примечания

Этот метод позволяет связать изображение курсора, такие как курсор в виде руки, с помощью кнопки. Курсор загружается из ресурсов приложения.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `SetMouseCursor` метод в `CMFCButton` класса. Пример является частью кода в [пример новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

##  <a name="setmousecursorhand"></a>  CMFCButton::SetMouseCursorHand

Задает курсор к образу руки.

```
void SetMouseCursorHand();
```

### <a name="remarks"></a>Примечания

Этот метод позволяет связать изображение курсора руки с помощью кнопки. Курсор загружается из ресурсов приложения.

##  <a name="setstdimage"></a>  CMFCButton::SetStdImage

Использует `CMenuImages` объекта, чтобы задать изображение кнопки.

```
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>Параметры

*id*<br/>
[in] Один из идентификаторов изображение кнопки, которые определены в `CMenuImage::IMAGES_IDS` перечисления. Изображения значения укажите изображения, например стрелки, ПИН-кодов и переключателей.

*state*<br/>
[in] Один из идентификаторов состояния изображение кнопки, которые определены в `CMenuImages::IMAGE_STATE` перечисления. Изображение состояния укажите цвета кнопок, такие как черный, серую, светло-серый белого и темно-серого цвета. Значение по умолчанию — `CMenuImages::ImageBlack`.

*idDisabled*<br/>
[in] Один из идентификаторов изображение кнопки, которые определены в `CMenuImage::IMAGES_IDS` перечисления. Изображения указывает, что кнопка отключена. Значение по умолчанию — первое изображение кнопки ( `CMenuImages::IdArrowDown`).

### <a name="remarks"></a>Примечания

##  <a name="settextcolor"></a>  CMFCButton::SetTextColor

Задает цвет текста кнопки для кнопки, которая не выбрана.

```
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>Параметры

*clrText*<br/>
[in] Значение цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="settexthotcolor"></a>  CMFCButton::SetTextHotColor

Задает цвет текста кнопки для кнопки, который выбран.

```
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>Параметры

*clrTextHot*<br/>
[in] Значение цвета RGB.

### <a name="remarks"></a>Примечания

##  <a name="settooltip"></a>  CMFCButton::SetTooltip

Связывает всплывающей подсказки с кнопкой.

```
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>Параметры

*lpszToolTipText*<br/>
[in] Указатель на текст подсказки для панели. Укажите значение NULL, чтобы отключить подсказки.

### <a name="remarks"></a>Примечания

##  <a name="sizetocontent"></a>  CMFCButton::SizeToContent

Изменение размера кнопки должен содержать текст кнопки и изображения.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Параметры

*bCalcOnly*<br/>
[in] Значение TRUE, чтобы вычислить, но не изменять новый размер кнопки; Значение FALSE, чтобы изменить размер кнопки. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Объект `CSize` , содержащий новый размер кнопки.

### <a name="remarks"></a>Примечания

По умолчанию этот метод вычисляет новый размер, включающий горизонтального поля 10 пикселей и вертикальное поле 5 пикселей.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[Класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)
