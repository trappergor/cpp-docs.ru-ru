---
title: Класс CMFCColorMenuButton
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 64d61cc9464ef0877baad33a8685cee1482f240d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301341"
---
# <a name="cmfccolormenubutton-class"></a>Класс CMFCColorMenuButton

`CMFCColorMenuButton` Класс поддерживает команды меню или панели инструментов кнопку, которая запускает диалоговое окно выбора цвета.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Создает объект `CMFCColorMenuButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отключает кнопка «автоматически», расположенный над кнопками регулярных цвет. (Кнопка автоматического стандартная система называется **автоматического**.)|
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Позволяет отображать конкретного документа цвета вместо цветов системы.|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Включает и отключает «other» кнопка, расположенный ниже регулярных цвет кнопок. (Стандартной системы, кнопка «other» называется **Дополнительные цвета**.)|
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Позволяют вам создать области цвета.|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Получает текущий цвет автоматической.|
|[CMFCColorMenuButton::GetColor](#getcolor)|Получает цвет текущей кнопки.|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Получает цвет, соответствующий указанному идентификатору команды.|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при изменении родительского окна.|
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Откроется диалоговое окно выбора цвета.|
|[CMFCColorMenuButton::SetColor](#setcolor)|Задает цвет кнопок цвет.|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Задает цвет кнопки меню указанного цвета.|
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Задает новое имя для указанного цвета.|
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов, которые отображаются по `CMFCColorBar` объекта.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Копирует текущий кнопки другую кнопку панели инструментов.|
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Создает диалоговое окно выбора цвета.|
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Указывает, поддерживается ли пустое меню.|
|[CMFCColorMenuButton::OnDraw](#ondraw)|Вызвано структурой для отображения изображения на кнопке.|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызвано структурой перед `CMFCColorMenuButton` объект отображается в списке в диалоговом окне настройки панели инструментов.|

## <a name="remarks"></a>Примечания

Для замены исходной команды меню или панели инструментов кнопки с `CMFCColorMenuButton` следует создать `CMFCColorMenuButton` объекта, задайте все необходимые [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) стили, а затем вызовите `ReplaceButton` метод [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) класса. Если настроить панель инструментов, вызовите [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) метод.

Диалоговое окно палитры создается во время обработки [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) обработчик событий. Обработчик событий уведомляет родительского фрейма сообщение WM_COMMAND. `CMFCColorMenuButton` Объект отправляет идентификатор элемента управления, присвоенный исходной команды меню или панели инструментов кнопки.

## <a name="example"></a>Пример

Следующий пример демонстрирует создание и настройка кнопка меню цвета с помощью различных методов в `CMFCColorMenuButton` класса. В примере `CPalette` объекта сначала создается и затем используется для создания объекта `CMFCColorMenuButton` класса. `CMFCColorMenuButton` Объект затем настраивается, включение его автоматическое и другие кнопки и настроив его цвет и число столбцов. Этот код является частью [примера Word Pad](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcolormenubutton.h

##  <a name="cmfccolormenubutton"></a>  CMFCColorMenuButton::CMFCColorMenuButton

Создает объект `CMFCColorMenuButton`.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
[in] Идентификатор кнопки команды.

*lpszText*<br/>
[in] Текст кнопки.

*pPalette*<br/>
[in] Указатель на кнопки цветовую палитру.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Первый конструктор является конструктором по умолчанию. Текущий цвет объекта и автоматической цветовой инициализируются черный цвет (RGB (0, 0, 0)).

Второй конструктор инициализирует кнопку, чтобы цвет, соответствующий указанному идентификатору команды.

##  <a name="copyfrom"></a>  CMFCColorMenuButton::CopyFrom

Копирует один [класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)-объекта, производного от другой.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
[in] Кнопка источника для копирования.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы копировать объекты, которые являются производными от `CMFCColorMenuButton` объекта.

##  <a name="createpopupmenu"></a>  CMFCColorMenuButton::CreatePopupMenu

Создает диалоговое окно выбора цвета.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, представляющий диалоговое окно выбора цвета.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда пользователь нажимает кнопку меню цвета.

##  <a name="enableautomaticbutton"></a>  CMFCColorMenuButton::EnableAutomaticButton

Включает и отключает кнопка «автоматически», расположенный над кнопками регулярных цвет. (Кнопка автоматического стандартная система называется **автоматического**.)

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Задает текст кнопки, отображаемый, когда кнопка становится автоматическим.

*colorAutomatic*<br/>
[in] Указывает автоматический цвет.

*bEnable*<br/>
[in] Указывает, является ли кнопка автоматического.

### <a name="remarks"></a>Примечания

Автоматической кнопки применяется текущий цвет по умолчанию.

##  <a name="enabledocumentcolors"></a>  CMFCColorMenuButton::EnableDocumentColors

Позволяет отображать конкретного документа цвета вместо цветов системы.

```
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Задает текст кнопки.

*bEnable*<br/>
[in] Значение TRUE для отображения цвета конкретного документа или значение FALSE для отображения системных цветов.

### <a name="remarks"></a>Примечания

Используйте этот метод для отображения цвета текущего документа или системные цвета палитры, при нажатии кнопки меню цвета.

##  <a name="enableotherbutton"></a>  CMFCColorMenuButton::EnableOtherButton

Включает и отключает «other» кнопка, расположенный ниже регулярных цвет кнопок. (Стандартной системы, кнопка «other» называется **Дополнительные цвета**.)

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
[in] Укажите значение TRUE, чтобы отобразить `CMFCColorDialog` диалогового окна, или значение FALSE, чтобы отобразить диалоговое окно стандартных системных цветов.

*bEnable*<br/>
[in] Укажите значение TRUE для отображения кнопки «other»; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

##  <a name="enabletearoff"></a>  CMFCColorMenuButton::EnableTearOff

Позволяют вам создать области цвета.

```
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
[in] Указывает идентификатор для области перемещаемой.

*nVertDockColumns*<br/>
[in] Задает число столбцов в области по вертикали закрепленной цвет в состоянии перемещения.

*nHorzDockRows*<br/>
[in] Указывает количество строк для области по горизонтали закрепленной цвет в состоянии перемещения.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы включить функцию «перемещаемой» для области цвета, возникающего при `CMFCColorMenuButton` нажатии кнопки.

##  <a name="getautomaticcolor"></a>  CMFCColorMenuButton::GetAutomaticColor

Получает текущий цвет автоматической.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB, представляющий текущий цвет автоматической.

### <a name="remarks"></a>Примечания

Вызовите этот метод для получения автоматическое цвет, который задается параметром [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).

##  <a name="getcolor"></a>  CMFCColorMenuButton::GetColor

Получает цвет текущей кнопки.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет кнопки.

### <a name="remarks"></a>Примечания

##  <a name="getcolorbycmdid"></a>  CMFCColorMenuButton::GetColorByCmdID

Получает цвет, соответствующий указанному идентификатору команды.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
[in] Идентификатор команды.

### <a name="return-value"></a>Возвращаемое значение

Цвет, соответствующий указанному идентификатору команды.

### <a name="remarks"></a>Примечания

Этот метод следует используйте, когда у вас есть несколько кнопок цвет в приложении. Когда пользователь нажимает кнопку цвета, кнопки отправляет его идентификатор команды в сообщении WM_COMMAND с родительским. `GetColorByCmdID` Метод использует идентификатор команды для получения соответствующий цвет.

##  <a name="isemptymenuallowed"></a>  CMFCColorMenuButton::IsEmptyMenuAllowed

Указывает, поддерживается ли пустое меню.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если допускается существование пустое меню. в противном случае — нуль.

### <a name="remarks"></a>Примечания

Пустое меню поддерживаются по умолчанию. Переопределите этот метод, чтобы изменить это поведение в производном классе.

##  <a name="onchangeparentwnd"></a>  CMFCColorMenuButton::OnChangeParentWnd

Вызывается платформой при изменении родительского окна.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Указатель на нового родительского окна.

### <a name="remarks"></a>Примечания

##  <a name="ondraw"></a>  CMFCColorMenuButton::OnDraw

Вызвано структурой для отображения изображения на кнопке.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rect*<br/>
[in] Прямоугольник, ограничивающий область перерисовку.

*pImages*<br/>
[in] Указывает на список изображений панели инструментов.

*bHorz*<br/>
[in] Значение TRUE, чтобы указать, что панель инструментов находится в горизонтальной закрепленного состояния; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

*bCustomizeMode*<br/>
[in] Значение TRUE, чтобы указать, что приложение находится в режиме настройки; в противном случае — значение FALSE. Значение по умолчанию — FALSE.

*bHighlight*<br/>
[in] Значение TRUE, чтобы указать, что кнопка выделена; в противном случае — значение FALSE. Значение по умолчанию — FALSE.

*bDrawBorder*<br/>
[in] Значение TRUE, чтобы указать, что отображается граница кнопки; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

*bGrayDisabledButtons*<br/>
[in] Значение TRUE, чтобы указать, что кнопки затененный (серым цветом) в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

##  <a name="ondrawoncustomizelist"></a>  CMFCColorMenuButton::OnDrawOnCustomizeList

Вызвано структурой перед `CMFCColorMenuButton` объект отображается в списке в диалоговом окне настройки панели инструментов.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rect*<br/>
[in] Ограничивающий прямоугольник для этого кнопки для отрисовки.

*bSelected*<br/>
[in] Значение TRUE указывает, что кнопка находится в выбранном состоянии; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Ширина кнопки.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при `CMFCColorMenuButton` объект отображается в поле со списком во время процесса настройки панели инструментов.

##  <a name="opencolordialog"></a>  CMFCColorMenuButton::OpenColorDialog

Откроется диалоговое окно выбора цвета.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Параметры

*colorDefault*<br/>
[in] Цвет по умолчанию, который выбран в диалоговом окне цвет.

*colorRes*<br/>
[out] Возвращает цвет, который пользователь выбирает в диалоговом окне цвет.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь выбирает новый цвет; в противном случае — нуль.

### <a name="remarks"></a>Примечания

При нажатии кнопки меню, вызовите этот метод, чтобы открыть диалоговое окно цвета. Если возвращаемое значение имеет ненулевое значение, цвет, который пользователь выбирает значение сохраняется в *colorRes* параметра. Используйте [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) метод для переключения между диалоговом окне стандартный цвет и [класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно.

##  <a name="setcolor"></a>  CMFCColorMenuButton::SetColor

Задает цвет кнопок цвет.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>Параметры

*clr*<br/>
[in] Значение цвета RGB.

*bNotify*<br/>
[in] Значение TRUE, чтобы применить *clr* параметр цвет для любого связанного кнопку меню или кнопки панели инструментов; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод используется для изменения цвета кнопки текущий цвет. Если *bNotify* параметр имеет ненулевое значение, цвет соответствующую кнопку на любой связанный всплывающего меню или панели инструментов изменяется цвет, определенный по *clr* параметра.

##  <a name="setcolorbycmdid"></a>  CMFCColorMenuButton::SetColorByCmdID

Задает цвет кнопки меню указанного цвета.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
[in] Идентификатор ресурса, цвет кнопки меню.

*color*<br/>
[in] Значение цвета RGB.

##  <a name="setcolorname"></a>  CMFCColorMenuButton::SetColorName

Задает новое имя для указанного цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] RGB-значение цвета, имя которого изменяется.

*strName*<br/>
[in] Новое имя цвета.

### <a name="remarks"></a>Примечания

##  <a name="setcolumnsnumber"></a>  CMFCColorMenuButton::SetColumnsNumber

Задает число столбцов для отображения в элементе управления выбора цвета ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта).

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Параметры

*nColumns*<br/>
[in] Число столбцов для отображения.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)
