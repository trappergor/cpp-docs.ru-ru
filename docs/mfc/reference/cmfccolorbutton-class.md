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
ms.openlocfilehash: c0c9ad79342f2013aa071240c684fce168e55c9e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780006"
---
# <a name="cmfccolorbutton-class"></a>Класс CMFCColorButton

`CMFCColorButton` И [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) классы используются совместно для реализации управление палитрой.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Создает новый `CMFCColorButton` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отключает кнопка «автоматически», расположенный над кнопками регулярных цвет. (Кнопка автоматического стандартная система называется **автоматического**.)|
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Включает и отключает «other» кнопка, расположенный ниже регулярных цвет кнопок. (Стандартной системы, кнопка «other» называется **Дополнительные цвета**.)|
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Получает текущий цвет автоматической.|
|[CMFCColorButton::GetColor](#getcolor)|Получает цвет кнопки.|
|[CMFCColorButton::SetColor](#setcolor)|Задает цвета кнопки.|
|[CMFCColorButton::SetColorName](#setcolorname)|Задает имя цвета.|
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов, отображаемых в диалоговом окне выбора цвета.|
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Задает список цветов конкретного документа, которые отображаются в диалоговом окне выбора цвета.|
|[CMFCColorButton::SetPalette](#setpalette)|Палитра цветов стандартные отображаемые данные.|
|[CMFCColorButton::SizeToContent](#sizetocontent)|Изменяет размер элемента управления button, в зависимости от размера текста и изображений.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Указывает, отображается ли кнопка текущего цвета в визуальном стиле Windows XP.|
|[CMFCColorButton::OnDraw](#ondraw)|Вызвано структурой для отображения изображения кнопки.|
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Вызывается платформой для отображения границы кнопки.|
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Вызвано структурой для отображения прямоугольник фокуса, когда кнопка имеет фокус.|
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Вызывается платформой при отображением диалогового окна выбора цвета.|
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Инициализирует `m_pPalette` защищенный элемент данных указанного палитру или системной палитре по умолчанию.|
|[CMFCColorButton::UpdateColor](#updatecolor)|Вызывается платформой, когда пользователь выбирает цвет в палитре диалогового окна выбора цвета.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|`m_bAltColorDlg`|Логическое значение. Если значение равно TRUE, платформа отображает [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) цвет-диалоговое окно при *других* кнопки, или если значение равно FALSE, система цвета диалоговое окно. Значение по умолчанию — TRUE. Дополнительные сведения см. в разделе [CMFCColorButton::EnableOtherButton](#enableotherbutton).|
|`m_bAutoSetFocus`|Логическое значение. Значение TRUE, если framework устанавливает фокус на меню «цвет», когда меню отображается, или если значение равно FALSE, не изменяет фокус. Значение по умолчанию — TRUE.|
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Указывает, включен ли режим настройки для «цвет».|
|`m_Color`|Объект [COLORREF](/windows/desktop/gdi/colorref) значение. Содержит выбранный цвет.|
|`m_ColorAutomatic`|Объект [COLORREF](/windows/desktop/gdi/colorref) значение. Содержит цвет выбранного по умолчанию.|
|`m_Colors`|Объект [CArray](../../mfc/reference/carray-class.md) из [COLORREF](/windows/desktop/gdi/colorref) значения. Содержит в настоящее время доступных цветов.|
|`m_lstDocColors`|Объект [CList](../../mfc/reference/clist-class.md) из [COLORREF](/windows/desktop/gdi/colorref) значения. Содержит цвета для текущего документа.|
|`m_nColumns`|Значение типа integer. Содержит количество столбцов для отображения в сетке цветов в меню выбора цвета.|
|`m_pPalette`|Указатель на [CPalette](../../mfc/reference/cpalette-class.md). Содержит цвета, которые доступны в меню выбора цвета.|
|`m_pPopup`|Указатель на [класс CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md) объекта. Меню выбора цвета, который отображается при нажатии кнопки цвет.|
|`m_strAutoColorText`|Строка. Метка «автоматически» кнопок в меню выбора цвета.|
|`m_strDocColorsText`|Строка. Подпись кнопки в меню выбора цвета, который отображает цвета документа.|
|`m_strOtherText`|Строка. Метка «other» кнопки в меню выбора цвета.|

## <a name="remarks"></a>Примечания

По умолчанию `CMFCColorButton` класс ведет себя как кнопка, которая открывает диалоговое окно выбора цвета. Диалоговое окно палитры содержит массив небольшой цвет кнопок и «other» кнопку, отображает пользовательские палитру. (Стандартной системы, кнопка «other» называется **Дополнительные цвета**.) Когда пользователь выбирает новый цвет, `CMFCColorButton` объект отражается изменение и отображает выбранный цвет.

Создать элемент управления button цвет непосредственно в коде или с помощью **ClassWizard** средство и шаблон диалогового окна. При создании элемента управления button в цвет напрямую добавить `CMFCColorButton` переменных для вашего приложения, а затем вызовите конструктор и `Create` методы `CMFCColorButton` объекта. При использовании **ClassWizard**, добавить `CButton` переменной для вашего приложения, а затем измените тип переменной из `CButton` для `CMFCColorButton`.

Диалоговое окно выбора цвета ( [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)) отображается по [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) метод, когда платформа вызывает `OnLButtonDown` обработчик событий. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) метод может быть переопределен для выбора пользовательский цвет.

`CMFCColorButton` Объект уведомляет родительского цвет меняется, отправляя ему WM_COMMAND | Уведомление о BN_CLICKED. В родительском объекте используются [CMFCColorButton::GetColor](#getcolor) метод для извлечения текущего цвета.

## <a name="example"></a>Пример

Следующий пример демонстрирует настройку кнопку цвета с помощью различных методов в `CMFCColorButton` класса. Методы задать цвет «цвет» и его число столбцов и включите автоматическое и другие кнопки. Этот пример является частью [состояние панели демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxcolorbutton.h

##  <a name="cmfccolorbutton"></a>  CMFCColorButton::CMFCColorButton

Создает новый `CMFCColorButton` объекта.

```
CMFCColorButton();
```

##  <a name="enableautomaticbutton"></a>  CMFCColorButton::EnableAutomaticButton

Включить или отключить кнопки «автоматически», элемент управления выбора цвета и задать цвет автоматически (по умолчанию).

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Указывает текст автоматической кнопки.

*colorAutomatic*<br/>
[in] Возвращает значение RGB, указывающее цвет автоматической кнопки по умолчанию.

*bEnable*<br/>
[in] Указывает, включена ли автоматическая кнопка.

### <a name="remarks"></a>Примечания

##  <a name="enableotherbutton"></a>  CMFCColorButton::EnableOtherButton

Включение или отключение «other» кнопку, которая показана ниже регулярных цвет кнопок.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Задает текст кнопки.

*bAltColorDlg*<br/>
[in] Указывает, является ли [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно Цвет системы открыт или когда пользователь нажимает кнопку.

*bEnable*<br/>
[in] Указывает, включена ли кнопки «other».

### <a name="remarks"></a>Примечания

Нажмите кнопку «other» для отображения диалоговое окно цвета. Если *bAltColorDlg* параметр имеет значение TRUE, [класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) отображается; в противном случае отображается диалоговое окно системы цвет.

##  <a name="getautomaticcolor"></a>  CMFCColorButton::GetAutomaticColor

Получает текущий цвет автоматически (по умолчанию).

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB, представляющий текущий цвет автоматической.

### <a name="remarks"></a>Примечания

Текущий цвет автоматической задается [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) метод.

##  <a name="getcolor"></a>  CMFCColorButton::GetColor

Извлекает выбранный цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB.

### <a name="remarks"></a>Примечания

##  <a name="isdrawxptheme"></a>  CMFCColorButton::IsDrawXPTheme

Указывает, отображается ли кнопка текущего цвета в визуальном стиле Windows XP.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если визуальные стили поддерживаются и кнопкой текущий цвет отображается в визуальном стиле Windows XP; в противном случае — значение FALSE.

##  <a name="m_benabledincustomizemode"></a>  CMFCColorButton::m_bEnabledInCustomizeMode

Задает кнопку цвета в режим настройки.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Примечания

Если вам нужно добавить кнопку цвета на странице диалогового окна настройки (или разрешите пользователю выбрать другую цвет во время настройки), включить кнопку, задав `m_bEnabledInCustomizeMode` член значение true. По умолчанию этот элемент имеет значение FALSE.

##  <a name="ondraw"></a>  CMFCColorButton::OnDraw

Вызывается платформой для отрисовки рисунка кнопки.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указывает контекст устройства, который используется для отрисовки изображения кнопки.

*rect*<br/>
[in] Ограничивающий прямоугольник для этого кнопку.

*uiState*<br/>
[in] Задает визуальное состояние кнопки.

### <a name="remarks"></a>Примечания

Переопределите этот метод для настройки процесса подготовки к просмотру.

##  <a name="ondrawborder"></a>  CMFCColorButton::OnDrawBorder

Вызывается платформой для отображения границы кнопки.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указывает контекст устройства, используемый для рисования границы.

*rectClient*<br/>
[in] Прямоугольник в контексте устройства, который задается параметром *pDC* параметр, который определяет границы кнопки для отрисовки.

*uiState*<br/>
[in] Задает визуальное состояние кнопки.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для настройки внешнего вида кнопка цвета границы.

##  <a name="ondrawfocusrect"></a>  CMFCColorButton::OnDrawFocusRect

Вызвано структурой для отображения прямоугольник фокуса, когда кнопка имеет фокус.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указывает контекст устройства, используемый для рисования прямоугольника фокуса.

*rectClient*<br/>
[in] Прямоугольник в контексте устройства, заданном *pDC* параметр, который определяет границы кнопки.

### <a name="remarks"></a>Примечания

Переопределите этот метод для настройки внешнего вида прямоугольника фокуса.

##  <a name="onshowcolorpopup"></a>  CMFCColorButton::OnShowColorPopup

Вызывается перед отображением всплывающей цветовой панели.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Примечания

##  <a name="rebuildpalette"></a>  CMFCColorButton::RebuildPalette

Инициализирует `m_pPalette` защищенный элемент данных указанного палитру или системной палитре по умолчанию.

```
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pPal*|[in] Указатель на логическую палитру или значение NULL. Если значение равно NULL, используется в Системная палитра по умолчанию.|

##  <a name="setcolor"></a>  CMFCColorButton::SetColor

Задает цвет кнопки.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Значение RGB.

### <a name="remarks"></a>Примечания

##  <a name="setcolorname"></a>  CMFCColorButton::SetColorName

Задает имя цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Значение цвета RGB.

*strName*<br/>
[in] Имя цвета.

### <a name="remarks"></a>Примечания

Список названий цветов глобальными для каждого приложения. Следовательно, этот метод передает параметры [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).

##  <a name="setcolumnsnumber"></a>  CMFCColorButton::SetColumnsNumber

Определяет количество столбцов, отображаемых в таблице цветов, представленные пользователю во время процесса выбора цвета для пользователя.

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Параметры

*nColumns*<br/>
[in] Указывает количество столбцов.

### <a name="remarks"></a>Примечания

Пользователь может выбрать цвет из цветовой полосе всплывающее окно, отображается таблица предопределенных цветов. Этот метод позволяет определить количество столбцов в таблице.

##  <a name="setdocumentcolors"></a>  CMFCColorButton::SetDocumentColors

Задает набор цветов и имя набора. Набор цветов, отображается с использованием [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Указывает метку для отображения с набором цвета документа.

*lstColors*<br/>
[in] Ссылка на список значений RGB.

### <a name="remarks"></a>Примечания

Объект `CMFCColorButton` объект ведет список значений RGB, которые передаются [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта. При отображении цветовой полосы, эти цвета отображаются в специальном разделе, метка которого задается *lpszLabel* параметра.

##  <a name="setpalette"></a>  CMFCColorButton::SetPalette

Указывает стандартные цвета для отображения на всплывающей панели цветов.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Параметры

*pPalette*<br/>
[in] Указатель на цветовую палитру.

### <a name="remarks"></a>Примечания

##  <a name="sizetocontent"></a>  CMFCColorButton::SizeToContent

Изменяет размер кнопки в соответствии с его текст и изображения.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Параметры

*bCalcOnly*<br/>
[in] Если значение ненулевое, вычисляется новый размер элемента управления button, но фактический размер не изменяется.

### <a name="return-value"></a>Возвращаемое значение

Объект `CSize` объект, который указывает новый размер элемента управления кнопки.

### <a name="remarks"></a>Примечания

##  <a name="updatecolor"></a>  CMFCColorButton::UpdateColor

Вызывается платформой, когда пользователь выбирает цвет из цветовой полосы, которая отображается, когда пользователь нажимает кнопку цвета.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Цвет, выбранный пользователем.

### <a name="remarks"></a>Примечания

`UpdateColor` Функция изменяет цвет выбранного кнопки и уведомляет родительского, отправив сообщение WM_COMMAND с уведомлением BN_CLICKED standard. Используйте [CMFCColorButton::GetColor](#getcolor) метод для извлечения выбранного цвета.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)<br/>
[Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[Класс CPalette](../../mfc/reference/cpalette-class.md)<br/>
[Класс CArray](../../mfc/reference/carray-class.md)<br/>
[Класс CList](../../mfc/reference/clist-class.md)<br/>
[CString](../../atl-mfc-shared/reference/cstringt-class.md)
