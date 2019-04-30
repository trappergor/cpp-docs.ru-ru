---
title: Класс CButton
ms.date: 11/04/2016
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
ms.openlocfilehash: b1a02d995594f5e079359151167ac970a3d1ab37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348696"
---
# <a name="cbutton-class"></a>Класс CButton

Предоставляет функциональные возможности кнопочных элементов управления Windows.

## <a name="syntax"></a>Синтаксис

```
class CButton : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CButton::CButton](#cbutton)|Создает объект `CButton`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CButton::Create](#create)|Создает элемент управления button в Windows и присоединяет его к `CButton` объекта.|
|[CButton::DrawItem](#drawitem)|Переопределение для рисования, рисуемый владельцем, `CButton` объекта.|
|[CButton::GetBitmap](#getbitmap)|Извлекает дескриптор растрового изображения, при помощи [SetBitmap](#setbitmap).|
|[CButton::GetButtonStyle](#getbuttonstyle)|Извлекает сведения о стиле элемента управления кнопки.|
|[CButton::GetCheck](#getcheck)|Возвращает состояние проверки элемента управления "Кнопка".|
|[CButton::GetCursor](#getcursor)|Извлекает дескриптор изображения курсора заданные ранее с помощью [SetCursor](#setcursor).|
|[CButton::GetIcon](#geticon)|Извлекает дескриптор значка, при помощи [SetIcon](#seticon).|
|[CButton::GetIdealSize](#getidealsize)|Извлекает идеальный размер элемента управления button.|
|[CButton::GetImageList](#getimagelist)|Извлекает список изображений элемента управления button.|
|[CButton::GetNote](#getnote)|Получает компонент Примечание текущий элемент управления command link.|
|[CButton::GetNoteLength](#getnotelength)|Получает длину текста Примечание для текущей команды управления ссылками.|
|[CButton::GetSplitGlyph](#getsplitglyph)|Получает глиф, связанный с текущей управления SplitButton.|
|[CButton::GetSplitImageList](#getsplitimagelist)|Извлекает список изображений для текущего управления SplitButton.|
|[CButton::GetSplitInfo](#getsplitinfo)|Извлекает сведения, определяющие текущего управления SplitButton.|
|[CButton::GetSplitSize](#getsplitsize)|Получает прямоугольник, ограничивающий компонента раскрывающегося списка для текущего управления SplitButton.|
|[CButton::GetSplitStyle](#getsplitstyle)|Получает стили кнопок разбиения, которые определяют текущего управления SplitButton.|
|[CButton::GetState](#getstate)|Получает состояние флажка, состояние выделения и состояние фокуса для управления "Кнопка".|
|[CButton::GetTextMargin](#gettextmargin)|Извлекает поле текст элемента управления button.|
|[CButton::SetBitmap](#setbitmap)|Указывает растровое изображение, чтобы отображаться на кнопке.|
|[CButton::SetButtonStyle](#setbuttonstyle)|Изменяет стиль кнопки.|
|[CButton::SetCheck](#setcheck)|Задает состояние пометки элемента управления "Кнопка".|
|[CButton::SetCursor](#setcursor)|Задает изображение курсор, отображаемый на кнопке.|
|[CButton::SetDropDownState](#setdropdownstate)|Задает состояние текущего управления SplitButton раскрывающегося списка.|
|[CButton::SetIcon](#seticon)|Задает значок, отображаемый на кнопке.|
|[CButton::SetImageList](#setimagelist)|Задает список изображений элемента управления button.|
|[CButton::SetNote](#setnote)|Задает примечание на текущий элемент управления command link.|
|[CButton::SetSplitGlyph](#setsplitglyph)|Связывает указанного глифа с текущего управления SplitButton.|
|[CButton::SetSplitImageList](#setsplitimagelist)|Связывает список изображений с текущего управления SplitButton.|
|[CButton::SetSplitInfo](#setsplitinfo)|Указывает сведения, определяющие текущего управления SplitButton.|
|[CButton::SetSplitSize](#setsplitsize)|Задает прямоугольник привязки компонента раскрывающегося списка для текущего управления SplitButton.|
|[CButton::SetSplitStyle](#setsplitstyle)|Задает стиль текущего управления SplitButton.|
|[CButton::SetState](#setstate)|Задает состояние выделения элемента управления "Кнопка".|
|[CButton::SetTextMargin](#settextmargin)|Задает поле текст элемента управления button.|

## <a name="remarks"></a>Примечания

Элемент управления button — Мелкая "," прямоугольная дочернее окно, можно нажать кнопку включения и отключения. Кнопки можно использовать отдельно или в группах и либо может называться или не содержат текст. Кнопка обычно изменяет внешний вид, когда пользователь щелкает его.

Обычные кнопки являются "флажок", "переключатель" и кнопка. Объект `CButton` объект может быть любой из них, согласно [кнопку стиля](../../mfc/reference/styles-used-by-mfc.md#button-styles) указано при его инициализации с [создать](#create) функция-член.

Кроме того [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) класс, производный от `CButton` поддерживает создание элементов управления с меткой с растровыми изображениями, а не текст. Объект `CBitmapButton` может иметь отдельные растровые изображения для кнопки элемента, вниз, с фокусом ввода и отключении.

Элемент управления можно создать из шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CButton` для создания `CButton` объект; затем вызвать `Create` функция-член для создания Windows управления "Кнопка" и присоединить его к `CButton` объекта.

Построение может быть задачей в класс, производный от `CButton`. Создание конструктора для производного класса, а также вызова `Create` из в конструкторе.

Если вы хотите обрабатывать посылается кнопкой элемента управления своему родителю сообщения уведомлений Windows (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавить схему сообщений входа и обработчик сообщений функцию-член в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

**ON\_**_уведомления_ **(** _идентификатор_, _memberFxn_ **)**

где *идентификатор* указывает идентификатор дочернего окна элемента управления, отправляющего уведомление и *memberFxn* имя функции-члена родительской вы написали для обработки уведомления.

Родительский прототип функции выглядит следующим образом:

`afx_msg void memberFxn();`

Ниже приведены возможные записей карты.

|Запись сопоставления|Отправлено в качестве родительского, если...|
|---------------|----------------------------|
|ON_BN_CLICKED|Пользователь нажимает кнопку.|
|ON_BN_DOUBLECLICKED|Пользователь дважды щелкает кнопку.|

Если вы создаете `CButton` из ресурса диалогового окна, `CButton` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

Если вы создаете `CButton` объекта в окне, необходимо уничтожить его. При создании `CButton` объект в куче с помощью **новый** функцию, необходимо вызвать **удалить** в объекте уничтожить его, когда пользователь закрывает Windows управления "Кнопка". Если вы создаете `CButton` объект в стеке, или он внедрен в родительский объект диалогового окна, он будет удален автоматически.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cbutton"></a>  CButton::CButton

Создает объект `CButton`.

```
CButton();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

##  <a name="create"></a>  CButton::Create

Создает элемент управления button в Windows и присоединяет его к `CButton` объекта.

```
virtual BOOL Create(
    LPCTSTR lpszCaption,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*lpszCaption*<br/>
Задает текст элемента управления button.

*dwStyle*<br/>
Задает стиль элемента управления button. Применить любое сочетание [кнопку Стили](../../mfc/reference/styles-used-by-mfc.md#button-styles) к кнопке.

*rect*<br/>
Задает размер и положение элемента управления button. Может быть либо `CRect` объекта или `RECT` структуры.

*pParentWnd*<br/>
Указывает родительского окна элемента управления button, обычно `CDialog`. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления button.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CButton` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает элемент управления button в Windows и присоединяет его к `CButton` объекта.

Если стиль WS_VISIBLE, Windows отправляет элемент управления button все сообщения, необходимые для активации и Показывать кнопку.

Примените следующий [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления кнопки:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_GROUP для группировки элементов управления

- WS_TABSTOP для включения кнопки в порядок следования

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

##  <a name="drawitem"></a>  CButton::DrawItem

Вызывается платформой при изменении вида определяемая владельцем кнопка.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) структуры. Структура содержит сведения о рисуемого элемента и типа требуется рисование.

### <a name="remarks"></a>Примечания

Определяемая владельцем кнопка имеет набор стилей BS_OWNERDRAW. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CButton` объекта. Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* до элемента завершении функции.

Также см. в разделе [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) стиля значения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

##  <a name="getbitmap"></a>  CButton::GetBitmap

Эта функция-член получить дескриптор растрового изображения, при помощи вызова [SetBitmap](#setbitmap), то есть связанный с кнопкой.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор к растровому изображению. Имеет значение NULL, если точечный рисунок отсутствует задан ранее.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="getbuttonstyle"></a>  CButton::GetButtonStyle

Извлекает сведения о стиле элемента управления кнопки.

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает стили кнопок для этого `CButton` объекта. Эта функция возвращает только [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) значения стиля, не любой другой стиль окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="getcheck"></a>  CButton::GetCheck

Извлекает состояние флажка, переключателя или флажка.

```
int GetCheck() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение из элемента управления кнопки, созданных с помощью BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON или стиль BS_3STATE является одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|BST_UNCHECKED|Состояние кнопки не установлен.|
|BST_CHECKED|Проверяется состояние кнопки.|
|BST_INDETERMINATE|Состояние кнопки не определен (применяется только в том случае, если кнопка имеет стиль BS_3STATE или BS_AUTO3STATE).|

Если кнопка имеет любой другой стиль, возвращаемое значение является BST_UNCHECKED.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="getcursor"></a>  CButton::GetCursor

Вызывайте эту функцию члена, чтобы получить дескриптор курсора, при помощи [SetCursor](#setcursor), то есть связанный с кнопкой.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор изображения курсора. Значение NULL, если ранее указано без курсора.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="geticon"></a>  CButton::GetIcon

Эта функция-член получить дескриптор значка, при помощи вызова [SetIcon](#seticon), то есть связанный с кнопкой.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для значка. Значение NULL, если значок не задан ранее.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="getidealsize"></a>  CButton::GetIdealSize

Получает наилучший размер элемента управления button.

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>Параметры

*psize*<br/>
Указатель на текущий размер кнопки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности BCM_GETIDEALSIZE сообщения, как описано в разделе [кнопки](/windows/desktop/controls/buttons) разделе пакета Windows SDK.

##  <a name="getimagelist"></a>  CButton::GetImageList

Этот метод используется для получения списка изображений из элемента управления button.

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Параметры

*pbuttonImagelist*<br/>
Указатель на список изображений из `CButton` объекта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности BCM_GETIMAGELIST сообщения, как описано в разделе [кнопки](/windows/desktop/controls/buttons) разделе пакета Windows SDK.

##  <a name="getnote"></a>  CButton::GetNote

Извлекает текст заметки, связанный с текущей элемент управления command link.

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszNote*|[out] Указатель на буфер, который вызывающий объект отвечает за выделение и освобождение. Если возвращаемое значение равно TRUE, буфер содержит текст примечаний, который связан с текущий элемент управления command link; в противном случае буфера не изменяется.|
|*cchNote*|[in, out] Указатель на переменную целого числа без знака.<br /><br /> При вызове этого метода, переменная содержит размер буфера, заданного *lpszNote* параметра.<br /><br /> Если этого метода завершается, если возвращаемое значение равно TRUE переменной содержит размер заметки, связанные с текущей элемент управления command link. Если возвращаемое значение равно FALSE, переменная содержит размер буфера, необходимый для размещения заметки.|

### <a name="return-value"></a>Возвращаемое значение

В первой перегрузке [CString](../../atl-mfc-shared/using-cstring.md) объекта, содержащего текст заметки, связанные с текущей элемент управления command link.

-или-

Во второй перегрузке значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_COMMANDLINK или BS_DEFCOMMANDLINK.

Этот метод отправляет [BCM_GETNOTE](/windows/desktop/Controls/bcm-getnote) сообщения, который описан в пакете Windows SDK.

##  <a name="getnotelength"></a>  CButton::GetNoteLength

Получает длину текста Примечание для текущей команды управления ссылками.

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина текста заметки, в 16-разрядных символов Юникода, для текущей команды управления ссылками.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_COMMANDLINK или BS_DEFCOMMANDLINK.

Этот метод отправляет [BCM_GETNOTELENGTH](/windows/desktop/Controls/bcm-getnotelength) сообщения, который описан в пакете Windows SDK.

##  <a name="getsplitglyph"></a>  CButton::GetSplitGlyph

Получает глиф, связанный с текущей управления SplitButton.

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>Возвращаемое значение

Символ глиф, связанный с текущей управления SplitButton.

### <a name="remarks"></a>Примечания

Глиф является физическое представление символа в определенном шрифте. Например, элемент управления split button может быть снабжен атрибутом глифа флажка символа Юникода (U + 2713).

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флагом BCSIF_GLYPH, а затем отправляет, которые структурируются в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, которое описано в Windows SDK. При возврате функции сообщения, этот метод получает глиф из `himlGlyph` член структуры.

##  <a name="getsplitimagelist"></a>  CButton::GetSplitImageList

Извлекает [список изображений](../../mfc/reference/cimagelist-class.md) для текущего управления SplitButton.

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флагом BCSIF_IMAGE, а затем отправляет, которые структурируются в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, которое описано в Windows SDK. При возврате функции сообщения, этот метод возвращает список изображений из `himlGlyph` член структуры.

##  <a name="getsplitinfo"></a>  CButton::GetSplitInfo

Извлекает параметры, определяющие, каким образом Windows выводит текущий элемент управления SplitButton.

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pInfo*|[out] Указатель на [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуры, который получает сведения о текущем управления SplitButton. Вызывающий объект отвечает за распределение структуры.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод отправляет [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщения, который описан в пакете Windows SDK.

##  <a name="getsplitsize"></a>  CButton::GetSplitSize

Получает прямоугольник, ограничивающий компонента раскрывающегося списка для текущего управления SplitButton.

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pSize*|[out] Указатель на [размер](/windows/desktop/api/windef/ns-windef-tagsize) структуру, которая получает описание прямоугольника.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Когда элемент управления split button развернута, ее можно отобразить компонент раскрывающегося списка, например элемент управления списка или элемента управления страничного навигатора. Этот метод извлекает ограничивающий прямоугольник, содержащий компонент раскрывающегося списка.

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флагом BCSIF_SIZE, а затем отправляет, которые структурируются в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, которое описано в Windows SDK. При возврате функции сообщения, этот метод извлекает ограничивающий прямоугольник из `size` член структуры.

##  <a name="getsplitstyle"></a>  CButton::GetSplitStyle

Получает стили кнопок разбиения, которые определяют текущего управления SplitButton.

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Побитовое сочетание стили кнопок разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуры.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Стили кнопок разбиения укажите выравнивание, пропорции и графическом формате, с которым Windows рисует значок кнопки разбиения.

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флагом BCSIF_STYLE, а затем отправляет, которые структурируются в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, которое описано в Windows SDK. При возврате функции сообщения, этот метод возвращает стили кнопок разбиения из `uSplitStyle` член структуры.

##  <a name="getstate"></a>  CButton::GetState

Возвращает состояние элемента управления "Кнопка".

```
UINT GetState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Битовое поле, которое содержит комбинацию значений, которые указывают текущее состояние элемента управления "Кнопка". В следующей таблице перечислены возможные значения.

|Состояние кнопки|Значение|Описание|
|------------------|-----------|-----------------|
|BST_UNCHECKED|0x0000|Начальное состояние.|
|BST_CHECKED|0x0001|Элемент управления button проверяется.|
|BST_INDETERMINATE|0x0002|Состояние — неопределенное (возможно только если элемент управления button имеет три состояния).|
|BST_PUSHED|0x0004|Кнопка нажата.|
|BST_FOCUS|0x0008|Элемент управления button в фокусе.|

### <a name="remarks"></a>Примечания

Элемент управления button с стиль кнопки BS_3STATE или BS_AUTO3STATE создает флажок, который имеет для третьего состояния, которая называется неопределенное состояние. Неопределенное состояние указывает, что флажок не установлен, и не снят флажок.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="gettextmargin"></a>  CButton::GetTextMargin

Этот метод возвращает отступ текста `CButton` объекта.

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Параметры

*pmargin*<br/>
Указатель на размер текстового поля `CButton` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает текстовое поле.

### <a name="remarks"></a>Примечания

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности BCM_GETTEXTMARGIN сообщения, как описано в разделе [кнопки](/windows/desktop/controls/buttons) разделе пакета Windows SDK.

##  <a name="setbitmap"></a>  CButton::SetBitmap

Вызовите эту функцию-член должен быть сопоставлен новое растровое изображение кнопки.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Дескриптор точечного рисунка.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор точечного рисунка, связанный с кнопкой.

### <a name="remarks"></a>Примечания

Растровое изображение будет автоматически помещено на кнопке, по центру по умолчанию. Если растровое изображение слишком велико для кнопки, то он будет обрезан с обеих сторон. Можно выбрать другие параметры выравнивания, включая следующие:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), которая использует четыре растровые изображения для кнопки, `SetBitmap` использует только одно растровое изображение на кнопке. При нажатии кнопки, точечный рисунок отображается необходимо сдвинуть вниз и вправо.

Вы несете ответственность за освобождение растрового изображения, когда вы закончите с ним.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="setbuttonstyle"></a>  CButton::SetButtonStyle

Изменяет стиль кнопки.

```
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
Указывает [кнопку стиля](../../mfc/reference/styles-used-by-mfc.md#button-styles).

*bRedraw*<br/>
Указывает, является ли кнопка перерисовку. Ненулевое значение перерисовывает кнопки. Значение 0 не перерисовки кнопки. Кнопки перерисовывается по умолчанию.

### <a name="remarks"></a>Примечания

Используйте `GetButtonStyle` функция-член для извлечения стиля кнопки. Младшее слово стиля "Завершить" является стиль кнопками.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="setcheck"></a>  CButton::SetCheck

Задает или сбрасывает состояние флажка, переключателя или флажка.

```
void SetCheck(int nCheck);
```

### <a name="parameters"></a>Параметры

*Проверьте*<br/>
Указывает состояние проверки. Этот параметр может принимать одно из следующих:

|Значение|Значение|
|-----------|-------------|
|BST_UNCHECKED|Задайте состояние кнопки, снимите флажок.|
|BST_CHECKED|Задайте состояние кнопки для проверки.|
|BST_INDETERMINATE|Значение неопределенное состояние кнопки. Это значение может использоваться только в том случае, если кнопка имеет стиль BS_3STATE или BS_AUTO3STATE.|

### <a name="remarks"></a>Примечания

Эта функция-член не влияет на кнопки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="setcursor"></a>  CButton::SetCursor

Вызовите эту функцию-член должен быть сопоставлен кнопки нового курсора.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Параметры

*hCursor*<br/>
Дескриптор курсора.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор курсора, связанный с кнопкой.

### <a name="remarks"></a>Примечания

Курсор автоматически помещается на кнопке, по центру по умолчанию. Если курсор находится слишком велик для кнопки, то он будет обрезан с обеих сторон. Можно выбрать другие параметры выравнивания, включая следующие:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), которая использует четыре растровые изображения для кнопки, `SetCursor` использует только один курсора на кнопку. При нажатии кнопки, курсор появляется необходимо сдвинуть вниз и вправо.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="setdropdownstate"></a>  CButton::SetDropDownState

Задает состояние текущего управления SplitButton раскрывающегося списка.

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*fDropDown*|[in] Значение TRUE, чтобы задать состояние BST_DROPDOWNPUSHED; в противном случае — значение FALSE.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Элемент управления split button стиль BS_SPLITBUTTON или BS_DEFSPLITBUTTON и состоит из кнопки и стрелку раскрывающегося списка справа от нее. Дополнительные сведения см. в разделе [стили кнопок](/windows/desktop/Controls/button-styles). Как правило когда пользователь щелкает стрелку раскрывающегося списка установлено состояние раскрывающегося списка. Этот метод позволяет программно задать состояние раскрывающегося списка элемента управления. Затененный для указания состояния отображаются стрелку раскрывающегося списка.

Этот метод отправляет [BCM_SETDROPDOWNSTATE](/windows/desktop/Controls/bcm-setdropdownstate) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная *m_splitButton*, который используется для программного доступа к элемент управления split button. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

В следующем примере кода задает состояние элемент управления split button, чтобы указать, что помещается стрелку раскрывающегося списка.

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

##  <a name="setelevationrequired"></a>  CButton::SetElevationRequired

Задает состояние текущего элемента управления кнопки для `elevation required`, который необходим для элемента управления для отображения значка повышенных привилегий.

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*fElevationRequired*|[in] Значение true, чтобы набор `elevation required` состояния; в противном случае — значение FALSE.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если элемент управления связями кнопки или команды требуется полномочие безопасности с повышенными правами для выполнения действия, значение элемента управления `elevation required` состояние. Как следствие Windows отображает значок щита контроля учетных записей (UAC) в элементе управления. Дополнительные сведения см. в разделе «Контроль учетных записей пользователей» в [MSDN](http://go.microsoft.com/fwlink/p/?linkid=18507).

Этот метод отправляет [BCM_SETSHIELD](/windows/desktop/Controls/bcm-setshield) сообщения, который описан в пакете Windows SDK.

##  <a name="seticon"></a>  CButton::SetIcon

Вызовите эту функцию-член должен быть сопоставлен новый значок кнопки.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
Дескриптор значка.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор значка, связанный с кнопкой.

### <a name="remarks"></a>Примечания

Значок автоматически помещаются на кнопке, по центру по умолчанию. Если значок слишком велико для кнопки, то он будет обрезан с обеих сторон. Можно выбрать другие параметры выравнивания, включая следующие:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), которая использует четыре растровые изображения для кнопки, `SetIcon` использует только один значок на кнопке. При нажатии кнопки, значок отображается необходимо сдвинуть вниз и вправо.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="setimagelist"></a>  CButton::SetImageList

Вызовите этот метод для установки образа список `CButton` объекта.

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Параметры

*pbuttonImagelist*<br/>
Указатель на новый список изображений.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности BCM_SETIMAGELIST сообщения, как описано в разделе [кнопки](/windows/desktop/controls/buttons) разделе пакета Windows SDK.

##  <a name="setnote"></a>  CButton::SetNote

Задает текст заметки для текущий элемент управления command link.

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszNote*|[in] Указатель на строку Unicode, заданную в качестве текст заметки для элемент управления command link.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_COMMANDLINK или BS_DEFCOMMANDLINK.

Этот метод отправляет [BCM_SETNOTE](/windows/desktop/Controls/bcm-setnote) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная *m_cmdLink*, который используется для программного доступа к элемент управления command link. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

В следующем примере кода задает текст заметки для элемент управления command link.

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

##  <a name="setsplitglyph"></a>  CButton::SetSplitGlyph

Связывает указанного глифа с текущего управления SplitButton.

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*chGlyph*|[in] Символ, который указывает глиф для использования в качестве стрелку раскрывающегося списка кнопки разбиения.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с помощью элементов управления, имеющих стиль кнопки BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Глиф является физическое представление символа в определенном шрифте. *ChGlyph* параметр не используется в качестве глифа, но вместо этого используется для выбора глифа набор глифов, определенная системой. Глиф стрелку раскрывающегося списка по умолчанию задается символ "6" и напоминает символ Юникода ЧЕРНЫЙ вниз ТРЕУГОЛЬНИК (U + 25BC).

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флажком BCSIF_GLYPH и `himlGlyph` член с *chGlyph* параметра, а затем отправляет, Структура в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, описанное в пакете Windows SDK.

##  <a name="setsplitimagelist"></a>  CButton::SetSplitImageList

Связывает [список изображений](../../mfc/reference/cimagelist-class.md) с текущего управления SplitButton.

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pSplitImageList*|[in] Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) для присваивания для текущего управления SplitButton.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флажком BCSIF_IMAGE и `himlGlyph` член с *pSplitImageList* параметра, а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, описанное в пакете Windows SDK.

##  <a name="setsplitinfo"></a>  CButton::SetSplitInfo

Указывает параметры, определяющие, каким образом Windows выводит текущий элемент управления SplitButton.

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pInfo*|[in] Указатель на [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структура, определяющая текущего управления SplitButton.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод отправляет [BCM_SETSPLITINFO](/windows/desktop/Controls/bcm-setsplitinfo) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_splitButton`, который используется для программного доступа к элемент управления split button.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

В следующем примере кода изменяется глифа, который используется для разбиения стрелку раскрывающегося списка. В примере подставляются направленный вверх треугольник глиф в виде глифа направленный вниз треугольник по умолчанию. Отображаемый глиф зависит от символа, указываемое в `himlGlyph` членом `BUTTON_SPLITINFO` структуры. Глиф направленный вниз треугольник указаны с символом "6"и глиф направленный вверх треугольник с символом "5". Для сравнения, см. в разделе удобного метода [CButton::SetSplitGlyph](#setsplitglyph).

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

##  <a name="setsplitsize"></a>  CButton::SetSplitSize

Задает прямоугольник привязки компонента раскрывающегося списка для текущего управления SplitButton.

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pSize*|[in] Указатель на [размер](/windows/desktop/api/windef/ns-windef-tagsize) структура, описывающая ограничивающего прямоугольника.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Когда элемент управления split button развернута, ее можно отобразить компонент раскрывающегося списка, например элемент управления списка или элемента управления страничного навигатора. Этот метод задает размер ограничивающего прямоугольника, который содержит компонент раскрывающегося списка.

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флажком BCSIF_SIZE и `size` член с *pSize* параметра, а затем отправляет, чтобы структура в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, описанное в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_splitButton`, который используется для программного доступа к элемент управления split button. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

В следующем примере удваивается размер стрелку раскрывающегося списка кнопки разбиения.

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

##  <a name="setsplitstyle"></a>  CButton::SetSplitStyle

Задает стиль текущего управления SplitButton.

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*uSplitStyle*|[in] Побитовое сочетание стили кнопок разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуры.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте только с элементами управления, чьи стиль кнопки является BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Стили кнопок разбиения укажите выравнивание, пропорции и графическом формате, с которым Windows рисует значок кнопки разбиения. Дополнительные сведения см. в разделе `uSplitStyle` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуры.

Этот метод инициализирует `mask` членом [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) структуру с флажком BCSIF_STYLE и `uSplitStyle` член с *uSplitStyle* параметра, а затем отправляет, Структура в [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) сообщение, описанное в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_splitButton`, который используется для программного доступа к элемент управления split button.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

В следующем примере кода задает стиль стрелки раскрывающегося списка кнопки разбиения. Стиль BCSS_ALIGNLEFT отображает стрелку слева от кнопки и стиль BCSS_STRETCH сохраняет пропорции стрелку раскрывающегося списка, при изменении размера кнопки.

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

##  <a name="setstate"></a>  CButton::SetState

Задает ли элемент управления выделен, или нет.

```
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>Параметры

*bHighlight*<br/>
Указывает, является ли кнопка отображаться. Ненулевое значение выделение кнопок; значение 0 удаляет все выделение.

### <a name="remarks"></a>Примечания

Влияет на внешней стороне управления "Кнопка". Он не влияет на состояние флажка, переключателя или флажка.

Элемент управления button автоматически выделяется, когда пользователь нажимает и удерживает левую кнопку мыши. Выделение удаляется, когда пользователь отпускает кнопку мыши.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="settextmargin"></a>  CButton::SetTextMargin

Вызовите этот метод, чтобы задать размер текстового поля `CButton` объекта.

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Параметры

*pmargin*<br/>
Указатель на новое значение текста.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности BCM_SETTEXTMARGIN сообщения, как описано в разделе [кнопки](/windows/desktop/controls/buttons) разделе пакета Windows SDK.

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)<br/>
[Класс CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
