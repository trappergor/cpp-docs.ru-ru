---
title: класс CMFCRibbonColorButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
ms.openlocfilehash: ceb686a9aca4ac126c4d61dd45975c65a9376ce9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769982"
---
# <a name="cmfcribboncolorbutton-class"></a>класс CMFCRibbonColorButton

Класс `CMFCRibbonColorButton` реализует кнопку цвета, которую можно добавить на панель ленты. Кнопка цвета ленты отображает раскрывающееся меню, содержащее одну или несколько палитр.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Добавляет группу цветов в стандартную область цветов.|
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Указывает, нажата ли кнопка **Автоматически** .|
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Активирует кнопку **Другие** .|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton::GetColor](#getcolor)|Возвращает выбранный в данный момент цвет.|
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Возвращает размер цветовых элементов, отображаемых на цветовой панели.|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Возвращает цвет элемента, выбранного в данный момент во всплывающей цветовой палитре.|
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Удаляет все группы цветов из стандартной области цветов.|
|[CMFCRibbonColorButton::SetColor](#setcolor)|Выбирает цвет в стандартной области цветов.|
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Задает размер всех цветовых элементов, отображаемых на цветовой панели.|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Задает список значений RGB, которые должны отображаться в области цветов документа.|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>Примечания

Когда пользователь нажимает кнопку цвета на ленте, отображается цветовая панель. По умолчанию эта панель содержит палитру выбора цвета, называемую стандартной областью цветов. Помимо этого, цветовая панель может содержать кнопку **Автоматически** , которая позволяет пользователю выбрать цвет по умолчанию, и кнопку **Другие** , которая позволяет открыть всплывающую цветовую палитру с дополнительными цветами.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonColorButton` . В нем показано, как создать объект `CMFCRibbonColorButton` , задать большое изображение, активировать кнопку **Автоматически** , активировать кнопку **Другие** , задать число столбцов, задать размер всех цветовых элементов, отображаемых на цветовой панели, добавить группу цветов в стандартную область цветов и указать список значений RGB, которые должны отображаться в области цветов документа. Этот фрагмент кода входит в состав [примера Draw Client](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncolorbutton.h

##  <a name="addcolorsgroup"></a>  CMFCRibbonColorButton::AddColorsGroup

Добавляет группу цветов в стандартную область цветов.

```
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
[in] Имя группы.

*lstColors*<br/>
[in] Список цветов.

*bContiguousColumns*<br/>
[in] Управляет отображением цвет элементов в группе. Значение TRUE, если цвет элементы отображаются без интервалы по вертикали. Если значение равно FALSE, элементы цвета отображаются с интервалы по вертикали.

### <a name="remarks"></a>Примечания

Воспользовавшись этой функцией, чтобы сделать цвет всплывающее отображать несколько групп цветов. Можно управлять как цвета отображаются в группе.

##  <a name="cmfcribboncolorbutton"></a>  CMFCRibbonColorButton::CMFCRibbonColorButton

Создает объект `CMFCRibbonColorButton`.

```
CMFCRibbonColorButton();

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>Параметры

*nID*<br/>
[in] Указывает идентификатор команды выполнения, когда пользователь нажимает кнопку команды.

*lpszText*<br/>
[in] Задает текст, отображаемый на кнопке.

*nSmallImageIndex*<br/>
[in] Отсчитываемый от нуля индекс небольшое изображение, отображаемый на кнопке.

*color*<br/>
[in] Цвет кнопки (по умолчанию используется черный).

*bSimpleButtonLook*<br/>
[in] Значение TRUE, если кнопки отображенный в виде простого прямоугольника.

*nLargeImageIndex*<br/>
[in] Отсчитываемый от нуля индекс большого изображения, отображаемый на кнопке.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="enableautomaticbutton"></a>  CMFCRibbonColorButton::EnableAutomaticButton

Указывает, нажата ли кнопка **Автоматически** .

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Метка для **автоматического** кнопки.

*colorAutomatic*<br/>
[in] RGB-значение, указывающее **автоматического** цвет кнопки по умолчанию.

*bEnable*<br/>
[in] Значение TRUE, если **автоматического** кнопка доступна; Значение FALSE, если она отключена.

*lpszToolTip*<br/>
[in] Подсказку **автоматического** кнопки.

*bOnTop*<br/>
[in] Указывает ли **автоматического** кнопку стоит первым в списке, прежде чем цветовую палитру.

*bDrawBorder*<br/>
[in] Значение TRUE, если приложение рисует границу вокруг цветовой полосы на кнопку цвета на ленте. Цветовая панель отображает выбранный цвет. Значение FALSE, если приложение не создает обрамление

##  <a name="enableotherbutton"></a>  CMFCRibbonColorButton::EnableOtherButton

Активирует кнопку **Другие** .

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
Надпись на этой кнопке.

*lpszToolTip*<br/>
Текст подсказки для **других** кнопки.

### <a name="remarks"></a>Примечания

**Других** кнопка является кнопкой, который отображается ниже группы цветов. Когда пользователь щелкает **других** кнопки, он отображает диалоговое окно цвета.

##  <a name="getautomaticcolor"></a>  CMFCRibbonColorButton::GetAutomaticColor

Получает текущий цвет кнопки автоматически.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB, представляющий текущий цвет кнопки автоматически.

### <a name="remarks"></a>Примечания

Цвет кнопки автоматически задается `colorAutomatic` параметр, передаваемый `CMFCRibbonColorButton::EnableAutomaticButton` метод.

##  <a name="getcolor"></a>  CMFCRibbonColorButton::GetColor

Возвращает выбранный в данный момент цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет, выбранный, нажав кнопку.

##  <a name="getcolorboxsize"></a>  CMFCRibbonColorButton::GetColorBoxSize

Возвращает размер цветовых элементов, отображаемых на цветовой панели.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер кнопок цвет в раскрывающемся списке цветовой палитре.

##  <a name="getcolumns"></a>  CMFCRibbonColorButton::GetColumns

Возвращает количество элементов в строке коллекции отображения кнопка цвета ленты.

```
int GetColumns() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество значков в каждой строке.

### <a name="remarks"></a>Примечания

##  <a name="gethighlightedcolor"></a>  CMFCRibbonColorButton::GetHighlightedColor

Возвращает цвет для выбранного элемента на всплывающее цветовую палитру.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет выбранного элемента на всплывающее цветовую палитру.

##  <a name="removeallcolorgroups"></a>  CMFCRibbonColorButton::RemoveAllColorGroups

Удаляет все группы цветов из стандартной области цветов.

```
void RemoveAllColorGroups();
```

##  <a name="setcolor"></a>  CMFCRibbonColorButton::SetColor

Выбирает цвет в стандартной области цветов.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Чтобы задать цвет.

##  <a name="setcolorboxsize"></a>  CMFCRibbonColorButton::SetColorBoxSize

Задает размер всех цветовых элементов, отображаемых на цветовой панели.

```
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>Параметры

*sizeBox*<br/>
[in] Новый размер кнопок цвет в палитре цветов.

##  <a name="setcolorname"></a>  CMFCRibbonColorButton::SetColorName

Задает новое имя для выбранного цвета.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Значение цвета RGB.

*strName*<br/>
[in] Новое имя для указанного цвета.

### <a name="remarks"></a>Примечания

Так как он вызывает `CMFCColorBar::SetColorName`, этот метод изменяет имя указанного цвета во всех `CMFCColorBar` объектов в приложении.

##  <a name="setcolumns"></a>  CMFCRibbonColorButton::SetColumns

Задает число столбцов, отображаемых в таблице цветов, представленные пользователю во время процесса выбора цвета для пользователя.

```
void SetColumns(int nColumns);
```

### <a name="parameters"></a>Параметры

*nColumns*<br/>
[in] Количество цветных значков для отображения в каждой строке.

### <a name="remarks"></a>Примечания

##  <a name="setdocumentcolors"></a>  CMFCRibbonColorButton::SetDocumentColors

Задает список значений RGB, которые должны отображаться в области цветов документа.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Текст, отображаемый с цветами документа.

*lstColors*<br/>
[in] Ссылка на список значений RGB.

##  <a name="setpalette"></a>  CMFCRibbonColorButton::SetPalette

Указывает стандартные цвета для отображения в таблице цветов, который отображает кнопку цвета.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Параметры

*pPalette*<br/>
[in] Указатель на цветовую палитру.

### <a name="remarks"></a>Примечания

##  <a name="updatecolor"></a>  CMFCRibbonColorButton::UpdateColor

Вызывается платформой, когда пользователь выбирает цвет из цветовой таблицы отображается, когда пользователь нажимает кнопку цвета.

```
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Цвет, выбранный пользователем.

### <a name="remarks"></a>Примечания

`CMFCRibbonColorButton::UpdateColor` Метод изменяет цвет выбранного кнопки и уведомляет родительского, отправив сообщение WM_COMMAND с уведомлением BN_CLICKED standard. Используйте [CMFCRibbonColorButton::GetColor](#getcolor) метод для извлечения выбранного цвета.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)
