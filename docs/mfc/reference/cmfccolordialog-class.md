---
title: Класс Кмфкколордиалог
ms.date: 11/04/2016
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
ms.openlocfilehash: 9e018c122cded09e5366c3b349525fa7cc004897
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505342"
---
# <a name="cmfccolordialog-class"></a>Класс Кмфкколордиалог

`CMFCColorDialog` Класс представляет диалоговое окно выбора цвета.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфкколордиалог:: Кмфкколордиалог](#cmfccolordialog)|Создает объект `CMFCColorDialog`.|
|`CMFCColorDialog::~CMFCColorDialog`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфкколордиалог:: "Color"](#getcolor)|Возвращает текущий выбранный цвет.|
|[Кмфкколордиалог:: "Palette"](#getpalette)|Возвращает палитру цвета.|
|`CMFCColorDialog::PreTranslateMessage`|Преобразует сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . Синтаксис и дополнительные сведения см. в разделе [CWnd::P ретранслатемессаже](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CDialogEx::PreTranslateMessage`.)|
|[Кмфкколордиалог:: Ребуилдпалетте](#rebuildpalette)|Извлекает палитру из системной палитры.|
|[Кмфкколордиалог:: Сеткуррентколор](#setcurrentcolor)|Задает текущий выбранный цвет.|
|[Кмфкколордиалог:: Сетневколор](#setnewcolor)|Задает наиболее эквивалентный цвет для указанного значения RGB.|
|[CMFCColorDialog::SetPageOne](#setpageone)|Выбирает значение RGB для первой страницы свойств.|
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Выбирает значение RGB для второй страницы свойств.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|`m_bIsMyPalette`|Значение true, если диалоговое окно выбора цвета использует собственную цветовую палитру, или false, если диалоговое окно использует палитру, `CMFCColorDialog` указанную в конструкторе.|
|`m_bPickerMode`|Значение TRUE, если пользователь выбирает цвет из диалогового окна выбора; в противном случае — значение FALSE.|
|`m_btnColorSelect`|Кнопка цвета, выбранная пользователем.|
|`m_CurrentColor`|Выбранный в данный момент цвет.|
|`m_hcurPicker`|Курсор, используемый для выбора цвета.|
|`m_NewColor`|Выбранный потенциальный цвет, который можно навсегда выбрать или вернуть к исходному цвету.|
|`m_pColourSheetOne`|Указатель на первую страницу свойств на странице свойств выбора цвета.|
|`m_pColourSheetTwo`|Указатель на вторую страницу свойств на странице свойств выбора цвета.|
|`m_pPalette`|Текущая логическая палитра.|
|`m_pPropSheet`|Указатель на страницу свойств для диалогового окна "Выбор цвета".|
|`m_wndColors`|Управляющий объект палитры цветов.|
|`m_wndStaticPlaceHolder`|Статический элемент управления, являющийся заполнителем для вкладки свойств палитры цветов.|

## <a name="remarks"></a>Примечания

Диалоговое окно Выбор цвета отображается в виде страницы свойств с двумя страницами. На первой странице выбирается Стандартный цвет из системной палитры. на второй странице выберите пользовательский цвет.

Можно создать `CMFCColorDialog` объект в стеке, а затем вызвать `DoModal`, передав исходный цвет в `CMFCColorDialog` качестве параметра в конструктор. Затем диалоговое окно выбора цвета создает несколько объектов [класса кмфкколорпиккерктрл](../../mfc/reference/cmfccolorpickerctrl-class.md) для работы с каждой цветовой палитрой.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[кдиаложекс](../../mfc/reference/cdialogex-class.md)

[кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как настроить диалоговое окно цвета с помощью различных методов в `CMFCColorDialog` классе. В этом примере показано, как задать текущий и новые цвета диалогового окна, а также как установить красный, зеленый и синий компоненты выбранного цвета на двух страницах свойств диалогового окна цвет. Этот пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** афксколордиалог. h

##  <a name="cmfccolordialog"></a>Кмфкколордиалог:: Кмфкколордиалог

Создает объект `CMFCColorDialog`.

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>Параметры

*клринит*<br/>
окне Выбор цвета по умолчанию. Если значение не указано, по умолчанию используется RGB (0, 0, 0) (черный).

*dwFlags*<br/>
[in] Зарезервировано.

*ппарентвнд*<br/>
окне Указатель на родительский узел или окно-владелец диалогового окна.

*хпал*<br/>
окне Маркер цветовой палитры.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getcolor"></a>Кмфкколордиалог:: "Color"

Извлекает цвет, который пользователь выбирает в диалоговом окне выбора цвета.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , содержащее сведения о RGB для цвета, выбранного в диалоговом окне "цвет".

### <a name="remarks"></a>Примечания

Вызовите эту функцию после вызова `DoModal` метода.

##  <a name="getpalette"></a>Кмфкколордиалог:: "Palette"

Извлекает цветовую палитру, доступную в диалоговом окне текущий цвет.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CPalette` объект, указанный `CMFCColorDialog` в конструкторе.

### <a name="remarks"></a>Примечания

Цветовая палитра определяет цвета, которые может выбрать пользователь.

##  <a name="rebuildpalette"></a>Кмфкколордиалог:: Ребуилдпалетте

Извлекает палитру из системной палитры.

```
void RebuildPalette();
```

##  <a name="setcurrentcolor"></a>Кмфкколордиалог:: Сеткуррентколор

Задает текущий цвет диалогового окна.

```
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>Параметры

*rgb*<br/>
окне Значение цвета RGB

### <a name="remarks"></a>Примечания

##  <a name="setnewcolor"></a>Кмфкколордиалог:: Сетневколор

Задает текущий цвет в наиболее похожем цвете в текущей палитре.

```
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>Параметры

*rgb*<br/>
окне Объект [COLORREF](/windows/win32/gdi/colorref) , задающий цвет RGB.

### <a name="remarks"></a>Примечания

##  <a name="setpageone"></a>Кмфкколордиалог:: Сетпажеоне

Явно определяет красный, зеленый и синий компоненты выбранного цвета на первой странице свойств диалогового окна выбора цвета.

```
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Параметры

*R*<br/>
окне Задает красный компонент значения RGB.

*G*<br/>
окне Задает зеленый компонент значения RGB.

*B*<br/>
окне Указывает синий компонент значения RGB.

### <a name="remarks"></a>Примечания

##  <a name="setpagetwo"></a>Кмфкколордиалог:: Сетпажетво

Явно указывает красный, зеленый и синий компоненты выбранного цвета на второй странице свойств диалогового окна выбора цвета.

```
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Параметры

*R*<br/>
окне Задает красный компонент значения RGB

*G*<br/>
окне Задает зеленый компонент значения RGB

*B*<br/>
окне Задает синий компонент значения RGB

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)
