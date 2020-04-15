---
title: Класс CMFCColorButton
ms.date: 11/04/2016
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
ms.openlocfilehash: 21d05fd8e805467f1a7a77d20c81d5ba0401455e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367734"
---
# <a name="cmfccolorbutton-class"></a>Класс CMFCColorButton

Классы `CMFCColorButton` [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) используются вместе для реализации управления сборщиком цветов.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Создает новый объект `CMFCColorButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отстраняет "автоматическую" кнопку, расположенную над обычными цветными кнопками. (Стандартная автоматическая кнопка системы помечена **Как автоматическая**.)|
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Включает и отстраняет "другие" кнопки, которая расположена ниже обычных цветовых кнопок. (Стандартная кнопка системы "другие" помечена **больше цветов**.)|
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Извлекает текущий автоматический цвет.|
|[CMFCColorButton::GetColor](#getcolor)|Извлекает цвет кнопки.|
|[CMFCColorButton::SetColor](#setcolor)|Устанавливает цвет кнопки.|
|[CMFCColorButton::SetColorName](#setcolorname)|Устанавливает цветовое имя.|
|[CMFCColorButton::SetColumnsНомер](#setcolumnsnumber)|Устанавливает количество столбцов в поле диалогового сбора цветов.|
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Определяет список цветов, специфийных для документооборота, которые отображаются в диалоговом поле сборщика цветов.|
|[CMFCColorButton::SetPalette](#setpalette)|Определяет палитру стандартных цветов дисплея.|
|[CMFCColor Button::SizetoContent](#sizetocontent)|Изменяет размер управления кнопкой, в зависимости от ее текста и размера изображения.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorButton::IsdrawXPTheme](#isdrawxptheme)|Указывает, отображается ли текущая цветная кнопка в визуальном стиле Windows XP.|
|[CMFCColorButton::Ondraw](#ondraw)|Вызывается рамки для отображения изображения кнопки.|
|[CMFCColorButton::OndrawBorder](#ondrawborder)|Вызывается по фрейму для отображения границы кнопки.|
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Вызывается фреймворком для отображения прямоугольника фокусировки, когда кнопка имеет фокус.|
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Вызывается рамки, когда цвет сборщик диалоговые окна вот-вот будет отображаться.|
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Инициализирует защищенный `m_pPalette` участник данных в указанную палитру или палитру системы по умолчанию.|
|[CMFCColorButton::UpdateColor](#updatecolor)|Вызывается рамки, когда пользователь выбирает цвет из палитры цвет сборщика диалогового окна.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|`m_bAltColorDlg`|Логическое значение. Если true, рамка отображает [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) цвет диалоговая коробка, когда *другая* кнопка нажата, или, если FALSE, система цвет диалоговая коробка. Значение по умолчанию — TRUE. Для получения дополнительной информации, см [CMFCColorButton::EnableOtherButton](#enableotherbutton).|
|`m_bAutoSetFocus`|Логическое значение. Если истина, рамки устанавливает акцент на цветовое меню, когда меню отображается, или если FALSE, не меняет фокус. Значение по умолчанию — TRUE.|
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Указывает, включен режим настройки для кнопки цвета.|
|`m_Color`|Значение [COLORREF.](/windows/win32/gdi/colorref) Содержит выбранный в настоящее время цвет.|
|`m_ColorAutomatic`|Значение [COLORREF.](/windows/win32/gdi/colorref) Содержит выбранный в настоящее время цвет по умолчанию.|
|`m_Colors`|[CArray](../../mfc/reference/carray-class.md) значений [COLORREF.](/windows/win32/gdi/colorref) Содержит доступные в настоящее время цвета.|
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) значений [COLORREF.](/windows/win32/gdi/colorref) Содержит текущие цвета документа.|
|`m_nColumns`|Целое число. Содержит количество столбцов для отображения в сетке цветов в меню выбора цвета.|
|`m_pPalette`|Указатель на [CPalette](../../mfc/reference/cpalette-class.md). Содержит цвета, доступные в текущем меню выбора цвета.|
|`m_pPopup`|Указатель на объект [класса CMFCColorPopupMenu.](../../mfc/reference/cmfccolorpopupmenu-class.md) Меню выбора цвета, отображаемый при нажатии кнопки "Цвет".|
|`m_strAutoColorText`|Строка. Метка кнопки "автоматическая" в меню выбора цвета.|
|`m_strDocColorsText`|Строка. Метка кнопки в меню выбора цвета, отображающие цвета документа.|
|`m_strOtherText`|Строка. Метка кнопки "другая" в меню выбора цвета.|

## <a name="remarks"></a>Remarks

По умолчанию `CMFCColorButton` класс ведет себя как кнопка, открывающий поле диалога сборщика цветов. Коробка диалогов цветосборщика содержит массив малых цветовых кнопок и "другие" кнопки, которая отображает пользовательский сборщик цветов. (Стандартная кнопка системы "другие" помечена **больше цветов**.) Когда пользователь выбирает новый цвет, `CMFCColorButton` объект отражает изменение и отображает выбранный цвет.

Создайте управление кнопкой цвета либо непосредственно в коде, либо с помощью инструмента **ClassWizard** и шаблона диалогового окна. Если вы создаете управление кнопкой `CMFCColorButton` цвета непосредственно, добавьте переменную `Create` в приложение, `CMFCColorButton` а затем позвоните в конструктор и методы объекта. Если вы используете **ClassWizard,** добавьте переменную `CButton` в приложение, а `CButton` `CMFCColorButton`затем измените тип переменной от .

Коробка диалогов цветосборщика [(класс CMFCColorBar)](../../mfc/reference/cmfccolorbar-class.md)отображается методом [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) метод, когда фреймворк вызывает обработчик `OnLButtonDown` событий. [Метод CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) может быть отменен для поддержки пользовательского выбора цвета.

Объект `CMFCColorButton` уведомляет своего родителя о том, что цвет изменяется, отправив ему WM_COMMAND BN_CLICKED уведомление. Родитель использует [метод CMFCColorButton::GetColor](#getcolor) для получения текущего цвета.

## <a name="example"></a>Пример

В следующем примере показано, как настроить цветную кнопку `CMFCColorButton` с помощью различных методов в классе. Методы устанавливают цвет кнопки цвета и ее количество столбцов, а также включат автоматические и другие кнопки. Этот пример является частью [образца демо-версии status Bar.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxcolorbutton.h

## <a name="cmfccolorbuttoncmfccolorbutton"></a><a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton

Создает новый объект `CMFCColorButton`.

```
CMFCColorButton();
```

## <a name="cmfccolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton

Включите или отключите "автоматическую" кнопку управления сборщиком цветов и установите автоматический (по умолчанию) цвет.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Определяет текст автоматической кнопки.

*colorAutomatic*<br/>
(в) Значение RGB, которое определяет цвет автоматической кнопки по умолчанию.

*bEnable*<br/>
(в) Уточняется, включена ли или отключена автоматическая кнопка.

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton

Включите или отключите кнопку «другая», которая отображается ниже обычных цветовых кнопок.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Определяет текст кнопки.

*bAltColorDlg*<br/>
(в) Уточняется, открывается ли диалоговая будка [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) или окно диалогового диалога цвета системы при нажатии на кнопку.

*bEnable*<br/>
(в) Определяет, включена ли или отключена кнопка "другая".

### <a name="remarks"></a>Remarks

Нажмите кнопку "другая" для отображения цветного диалогового окна. Если параметр *bAltColorDlg* является правдой, отображается [класс CMFCColorDialog;](../../mfc/reference/cmfccolordialog-class.md) в противном случае отображается диалоговая коробка системы.

## <a name="cmfccolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor

Извлекает текущий автоматический (по умолчанию) цвет.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB, представляющее текущий автоматический цвет.

### <a name="remarks"></a>Remarks

Текущий автоматический цвет устанавливается методом [CMFCColorButton::EnableAutomaticButton.](#enableautomaticbutton)

## <a name="cmfccolorbuttongetcolor"></a><a name="getcolor"></a>CMFCColorButton::GetColor

Извлекает выбранный в настоящее время цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB.

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbuttonisdrawxptheme"></a><a name="isdrawxptheme"></a>CMFCColorButton::IsdrawXPTheme

Указывает, отображается ли текущая цветная кнопка в визуальном стиле Windows XP.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если визуальные стили поддерживаются и текущая кнопка цвета отображается в визуальном стиле Windows XP; в противном случае, FALSE.

## <a name="cmfccolorbuttonm_benabledincustomizemode"></a><a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode

Устанавливает кнопку цвета в режим настройки.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Remarks

Если вам нужно добавить кнопку цвета на страницу диалога настройки (или позволить пользователю сделать еще `m_bEnabledInCustomizeMode` один выбор цвета во время настройки), включите кнопку, установив член true. По умолчанию этот участник настроен на FALSE.

## <a name="cmfccolorbuttonondraw"></a><a name="ondraw"></a>CMFCColorButton::Ondraw

Вызывается фреймворком для визуализации изображения кнопки.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указывает на контекст устройства, который используется для визуализации изображения кнопки.

*rect*<br/>
(в) Прямоугольник, который граничит с кнопкой.

*uiState*<br/>
(в) Определяет визуальное состояние кнопки.

### <a name="remarks"></a>Remarks

Переопределить этот метод для настройки процесса визуализации.

## <a name="cmfccolorbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCColorButton::OndrawBorder

Вызывается рамки для отображения границы кнопки.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Точки контекста устройства, используемого для рисования границы.

*rectClient*<br/>
(в) Прямоугольник в контексте устройства, указанный параметром *pDC,* определяющим границы нарисованной кнопки.

*uiState*<br/>
(в) Определяет визуальное состояние кнопки.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы настроить внешний вид границы кнопки цвета.

## <a name="cmfccolorbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect

Вызывается фреймворком для отображения прямоугольника фокусировки, когда кнопка имеет фокус.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Точки контекста устройства, используемого для рисования прямоугольника фокуса.

*rectClient*<br/>
(в) Прямоугольник в контексте устройства, указанный параметром *pDC,* определяющим границы кнопки.

### <a name="remarks"></a>Remarks

Переопределить этот метод, чтобы настроить внешний вид прямоугольника фокуса.

## <a name="cmfccolorbuttononshowcolorpopup"></a><a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup

Вызывается до всплывающих цвет бар отображается.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbuttonrebuildpalette"></a><a name="rebuildpalette"></a>CMFCColorButton::RebuildPalette

Инициализирует защищенный `m_pPalette` участник данных в указанную палитру или палитру системы по умолчанию.

```
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pPal*|(в) Указатель на логическую палитру или NULL. Если NULL, используется палитра системы по умолчанию.|

## <a name="cmfccolorbuttonsetcolor"></a><a name="setcolor"></a>CMFCColorButton::SetColor

Определяет цвет кнопки.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение RGB.

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbuttonsetcolorname"></a><a name="setcolorname"></a>CMFCColorButton::SetColorName

Определяет название цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение RGB цвета.

*strName*<br/>
(в) Название цвета.

### <a name="remarks"></a>Remarks

Список цветовых имен является глобальным для одного приложения. Следовательно, этот метод передает свои параметры [cmFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).

## <a name="cmfccolorbuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsНомер

Определяет количество столбцов, отображаемых в таблице цветов, которые представлены пользователю в процессе выбора цвета пользователя.

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Параметры

*nColumns*<br/>
(в) Определяет количество столбцов.

### <a name="remarks"></a>Remarks

Пользователь может выбрать цвет из всплывающих цветовой панели, которая отображает таблицу предопределенных цветов. Используйте этот метод для определения количества столбцов в таблице.

## <a name="cmfccolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors

Определяет набор цветов и название набора. Набор цветов отображается с помощью объекта [класса CMFCColorBar.](../../mfc/reference/cmfccolorbar-class.md)

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Украсьте метку для отображения набором цветов документа.

*lstColors*<br/>
(в) Ссылка на список значений RGB.

### <a name="remarks"></a>Remarks

Объект `CMFCColorButton` поддерживает список значений RGB, которые передаются объекту [класса CMFCColorBar.](../../mfc/reference/cmfccolorbar-class.md) При отображении цветов эти цвета отображаются в специальном разделе, метка которого указана параметром *lpszLabel.*

## <a name="cmfccolorbuttonsetpalette"></a><a name="setpalette"></a>CMFCColorButton::SetPalette

Определяет стандартные цвета для отображения на всплывающем цветовом баре.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Параметры

*pPalette*<br/>
(в) Указатель на цветовую палитру.

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbuttonsizetocontent"></a><a name="sizetocontent"></a>CMFCColor Button::SizetoContent

Изображки управления кнопкой, чтобы соответствовать его текст и изображение.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Параметры

*bCalcТолько*<br/>
(в) Если ненулевой, новый размер управления кнопкой рассчитывается, но фактический размер не изменяется.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CSize` опознававательный новый размер управления кнопками.

### <a name="remarks"></a>Remarks

## <a name="cmfccolorbuttonupdatecolor"></a><a name="updatecolor"></a>CMFCColorButton::UpdateColor

Вызывается по фреймворку, когда пользователь выбирает цвет из цветовой панели, отображаемый при нажатии кнопки цвета.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Цвет, выбранный пользователем.

### <a name="remarks"></a>Remarks

Функция `UpdateColor` изменяет цвет выбранной в настоящее время кнопки и уведомляет своего родителя, отправляя WM_COMMAND сообщение с BN_CLICKED стандартным уведомлением. Используйте [метод CMFCColor Button::GetColor](#getcolor) для получения выбранного цвета.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)<br/>
[Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[Класс CPalette](../../mfc/reference/cpalette-class.md)<br/>
[Класс CArray](../../mfc/reference/carray-class.md)<br/>
[Класс CList](../../mfc/reference/clist-class.md)<br/>
[CString](../../atl-mfc-shared/reference/cstringt-class.md)
