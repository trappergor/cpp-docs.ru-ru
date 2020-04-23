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
ms.openlocfilehash: 74b07dc8144e853714ea73c8235f1259538a0c12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752751"
---
# <a name="cbutton-class"></a>Класс CButton

Предоставляет функциональные возможности кнопочных элементов управления Windows.

## <a name="syntax"></a>Синтаксис

```
class CButton : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кнопка::Кнопка](#cbutton)|Формирует объект `CButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кнопка::Создание](#create)|Создает управление кнопкой Windows и `CButton` прикрепляет его к объекту.|
|[CButton::DrawItem](#drawitem)|Переопределение для рисования `CButton` нарисованного владельцем объекта.|
|[CButton:GetBitmap](#getbitmap)|Извлекает ручку бит-карты, ранее установленной [setBitmap.](#setbitmap)|
|[Кнопка:GetButtonStyle](#getbuttonstyle)|Извлекает информацию о стиле управления кнопками.|
|[Кнопка::GetCheck](#getcheck)|Извлекает контрольное состояние управления кнопкой.|
|[CButton::GetCursor](#getcursor)|Извлекает ручку изображения курсора, ранее установленного set with [SetCursor.](#setcursor)|
|[Кнопка:GetIcon](#geticon)|Извлекает ручку значка, ранее установленную [SetIcon.](#seticon)|
|[Кнопка:GetIdealSize](#getidealsize)|Получает идеальный размер управления кнопками.|
|[Кнопка:GetImageList](#getimagelist)|Извлекает список изображений управления кнопкой.|
|[Кнопка:GetNote](#getnote)|Извлекает компонент заметок текущего управления командной ссылкой.|
|[Кнопка:GetNoteДлина](#getnotelength)|Извлекает длину текста заметок для текущего управления ссылкой команды.|
|[Кнопка:GetSplitGlyph](#getsplitglyph)|Извлекает глиф, связанный с текущим управлением кнопки разделения.|
|[Кнопка:GetSplitImageList](#getsplitimagelist)|Извлекает список изображений для текущего управления кнопкой разделения.|
|[Кнопка:GetSplitInfo](#getsplitinfo)|Извлекает информацию, определяющую текущее управление кнопкой разделения.|
|[Кнопка::GetSplitSize](#getsplitsize)|Извлекает прямоугольник ограничивающего сядка компонента текущего управления кнопкой разделения.|
|[Кнопка:GetSplitStyle](#getsplitstyle)|Извлекает стили сплит-кнопки, определяющие текущее управление кнопкой разделения.|
|[CButton:GetState](#getstate)|Извлекает состояние проверки, выделяет состояние состояния и фокусирует состояние управления кнопками.|
|[Кнопка:GetTextMargin](#gettextmargin)|Извлекает текстовый запас кнопки управления.|
|[CButton::SetBitmap](#setbitmap)|Упоняет битную карту для отображения на кнопке.|
|[Кнопка::SetButtonStyle](#setbuttonstyle)|Изменяет стиль кнопки.|
|[Кнопка::SetCheck](#setcheck)|Устанавливает состояние проверки управления кнопкой.|
|[CButton::SetCursor](#setcursor)|Определяет изображение курсора для отображения на кнопке.|
|[Кнопка CButton::SetDropDownState](#setdropdownstate)|Устанавливает состояние выпадающих вниз текущего управления кнопкой разделения.|
|[Кнопка::SetIcon](#seticon)|Упогоняет значок для отображения на кнопке.|
|[Кнопка:SetImageList](#setimagelist)|Устанавливает список изображений управления кнопками.|
|[Кнопка::SetNote](#setnote)|Устанавливает примечание на текущем управлении командной ссылкой.|
|[CButton::SetSplitGlyph](#setsplitglyph)|Связывает указанный глиф с текущим управлением кнопки разделения.|
|[Кнопка::SetSplitImageList](#setsplitimagelist)|Связывает список изображений с текущим управлением кнопки разделения.|
|[Кнопка:SetSplitInfo](#setsplitinfo)|Определяет информацию, определяющую текущее управление кнопкой разделения.|
|[Кнопка CButton::SetSplitSize](#setsplitsize)|Устанавливает прямоугольник выпадающего компонента текущего управления кнопкой разделения.|
|[Кнопка::SetSplitStyle](#setsplitstyle)|Устанавливает стиль текущего управления кнопкой разделения.|
|[CButton::SetState](#setstate)|Устанавливает состояние выделения кнопки управления.|
|[Кнопка::SetTextMargin](#settextmargin)|Устанавливает текстовый запас кнопки управления.|

## <a name="remarks"></a>Remarks

Управление кнопками представляет собой небольшое прямоугольное детское окно, которое можно нажать и выключить. Кнопки могут использоваться в одиночку или в группах и могут быть помечены или отображаться без текста. Кнопка обычно изменяет внешний вид, когда пользователь нажимает на нее.

Типичными кнопками являются флажок, радиокнопка и кнопка. Объект `CButton` может стать любым из них, в соответствии со [стилем кнопки,](../../mfc/reference/styles-used-by-mfc.md#button-styles) указанным при его инициализации функцией члена [Create.](#create)

Кроме того, класс [CBitmapButton,](../../mfc/reference/cbitmapbutton-class.md) полученный из `CButton` поддерживает создание элементов управления кнопками, помеченных изображениями биткарты вместо текста. Может `CBitmapButton` иметь отдельные бит-карты для состояния кнопки вверх, вниз, сфокусировано и отключено.

Вы можете создать кнопку управления либо из шаблона диалога или непосредственно в коде. В обоих случаях сначала `CButton` позвоните `CButton` в конструктор, чтобы построить объект; затем позвоните функции `Create` участника для создания управления `CButton` кнопкой Windows и прикрепите ее к объекту.

Строительство может быть одноступенчатый процесс в `CButton`классе, полученных из . Напишите конструктор для производного класса и позвоните `Create` изнутри конструктора.

Если вы хотите обрабатывать сообщения уведомлений Windows, отправленные элементом управления кнопками, своему родителю (обычно класс, полученный из [CDialog),](../../mfc/reference/cdialog-class.md)добавьте запись на карту сообщений и функцию обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись на карту сообщений принимает следующую форму:

**НА\_**_Уведомление_ **(id** _id_, _memberFxn_ **)**

где *идентификатор* определяет идентификатор окна ребенка элемента управления, отправляющий уведомление, и *memberFxn* — это имя функции родительского члена, написанной для обработки уведомления.

Прототип функции родителя:

`afx_msg void memberFxn();`

Потенциальные записи на карту сообщений следующие:

|Запись на карту|Отправлено родителям, когда...|
|---------------|----------------------------|
|ON_BN_CLICKED|Пользователь нажимает кнопку.|
|ON_BN_DOUBLECLICKED|Пользователь дважды нажимает кнопку.|

При создании `CButton` объекта из ресурса диалога `CButton` объект автоматически уничтожается при закрытии окна диалога.

Если вы `CButton` создаете объект в окне, возможно, потребуется уничтожить его. Если вы `CButton` создаете объект на куче с помощью **новой** функции, необходимо **вызвать удаление** объекта, чтобы уничтожить его, когда пользователь закрывает управление кнопкой Windows. Если вы `CButton` создаете объект в стеке или встраивается в родительский объект диалога, он уничтожается автоматически.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cbuttoncbutton"></a><a name="cbutton"></a>Кнопка::Кнопка

Формирует объект `CButton`.

```
CButton();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

## <a name="cbuttoncreate"></a><a name="create"></a>Кнопка::Создание

Создает управление кнопкой Windows и `CButton` прикрепляет его к объекту.

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
Определяет текст управления кнопкой.

*dwStyle*<br/>
Определяет стиль управления кнопками. Примените к кнопке любую комбинацию [стилей кнопок.](../../mfc/reference/styles-used-by-mfc.md#button-styles)

*rect*<br/>
Определяет размер и положение управления кнопками. Это может быть `CRect` либо `RECT` объект, либо структура.

*pParentWnd*<br/>
Определяет родительское окно управления кнопкой, обычно `CDialog`. Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор управления кнопкой.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы строите `CButton` объект в два этапа. Сначала позвоните конструктору, `Create`а затем позвоните, который создает управление `CButton` кнопкой Windows и прикрепляет его к объекту.

Если приведен WS_VISIBLE стиль, Windows отправляет кнопку управления всеми сообщениями, необходимыми для активации и отображать кнопку.

Примените следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к управлению кнопками:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

- WS_GROUP К управлению группой

- WS_TABSTOP Включить кнопку в порядок внесения табуинга

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

## <a name="cbuttondrawitem"></a><a name="drawitem"></a>CButton::DrawItem

Вызывается в рамках, когда визуальный аспект нарисованной владельцем кнопки изменился.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на структуру [DRAWITEMSTRUCT.](/windows/win32/api/winuser/ns-winuser-drawitemstruct) Структура содержит информацию о элементе, который будет нарисован, и типе требуемого чертежа.

### <a name="remarks"></a>Remarks

Нарисованная владельцем кнопка имеет набор BS_OWNERDRAW стилей. Переопределить эту функцию элемента для `CButton` реализации чертежа для нарисованного владельцем объекта. Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста дисплея, поставляемые в *lpDrawItemStruct,* прежде чем функция участника прекратится.

Также обратите сьязание значений [стиля BS_.](../../mfc/reference/styles-used-by-mfc.md#button-styles)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

## <a name="cbuttongetbitmap"></a><a name="getbitmap"></a>CButton:GetBitmap

Вызов эту функцию участника, чтобы получить ручку бит-карты, ранее установленной с [SetBitmap](#setbitmap), которая связана с кнопкой.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к бит-карте. NULL, если биткарта не указана ранее.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttongetbuttonstyle"></a><a name="getbuttonstyle"></a>Кнопка:GetButtonStyle

Извлекает информацию о стиле управления кнопками.

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает стили кнопки для этого `CButton` объекта. Эта функция возвращает только [значения BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) стилей, а не любой из других стилей окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttongetcheck"></a><a name="getcheck"></a>Кнопка::GetCheck

Извлекает контрольное состояние кнопки радио или флажка.

```
int GetCheck() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение возврата от управления кнопками, создаваемых с помощью BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON или BS_3STATE стиля, является одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|BST_UNCHECKED|Состояние кнопки не проверяется.|
|BST_CHECKED|Состояние кнопки проверяется.|
|BST_INDETERMINATE|Состояние кнопки является неопределенным (применяется только в том случае, если кнопка имеет BS_3STATE или BS_AUTO3STATE стиле).|

Если кнопка имеет какой-либо другой стиль, значение возврата BST_UNCHECKED.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttongetcursor"></a><a name="getcursor"></a>CButton::GetCursor

Вызов эту функцию члена, чтобы получить ручку курсора, ранее установленную с [SetCursor](#setcursor), которая связана с кнопкой.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к изображению курсора. NULL, если курсор не указан ранее.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttongeticon"></a><a name="geticon"></a>Кнопка:GetIcon

Вызов эту функцию элемента, чтобы получить ручку значка, ранее установленную [с SetIcon](#seticon), который связан с кнопкой.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для значка. NULL, если значок не указан ранее.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttongetidealsize"></a><a name="getidealsize"></a>Кнопка:GetIdealSize

Получает идеальный размер для управления кнопками.

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>Параметры

*psize*<br/>
Указатель на текущий размер кнопки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность сообщения BCM_GETIDEALSIZE, как описано в разделе [Кнопки](/windows/win32/controls/buttons) SDK Windows.

## <a name="cbuttongetimagelist"></a><a name="getimagelist"></a>Кнопка:GetImageList

Вызовите этот метод, чтобы получить список изображений из управления кнопками.

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Параметры

*pbuttonImagelist*<br/>
Указатель на список изображений `CButton` объекта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность BCM_GETIMAGELIST сообщения, как описано в разделе [кнопки](/windows/win32/controls/buttons) SDK Windows.

## <a name="cbuttongetnote"></a><a name="getnote"></a>Кнопка:GetNote

Извлекает текст заметок, связанный с текущим управлением ссылкой команды.

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszNote*|(ваут) Указатель на буфер, который абонент несет ответственность за выделение и распределение. Если значение возврата является правдой, буфер содержит текст заметок, связанный с текущим управлением командной ссылкой; в противном случае буфер остается неизменным.|
|*cchNote*|(в, вне) Указатель на неподписанную переменную integer.<br /><br /> Когда этот метод вызывается, переменная содержит размер буфера, указанный параметром *lpszNote.*<br /><br /> Когда этот метод возвращается, если значение возврата является истинным, переменная содержит размер примечания, связанного с текущим управлением ссылкой команды. Если значение возврата FALSE, переменная содержит размер буфера, необходимый для содержания заметки.|

### <a name="return-value"></a>Возвращаемое значение

В первой перегрузке объект [CString,](../../atl-mfc-shared/using-cstring.md) содержащий текст заметок, связанный с текущим управлением командной ссылкой.

-или-

Во второй перегрузке, правда, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопок которых BS_COMMANDLINK или BS_DEFCOMMANDLINK.

Этот метод отправляет [BCM_GETNOTE](/windows/win32/Controls/bcm-getnote) сообщение, которое описано в SDK Windows.

## <a name="cbuttongetnotelength"></a><a name="getnotelength"></a>Кнопка:GetNoteДлина

Извлекает длину текста заметок для текущего управления ссылкой команды.

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина текста заметок в 16-битных символах Unicode для текущего управления командной ссылкой.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопок которых BS_COMMANDLINK или BS_DEFCOMMANDLINK.

Этот метод отправляет [BCM_GETNOTELENGTH](/windows/win32/Controls/bcm-getnotelength) сообщение, которое описано в SDK Windows.

## <a name="cbuttongetsplitglyph"></a><a name="getsplitglyph"></a>Кнопка:GetSplitGlyph

Извлекает глиф, связанный с текущим управлением кнопки разделения.

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>Возвращаемое значение

Символ глифа, связанный с текущим управлением кнопки разделения.

### <a name="remarks"></a>Remarks

Глиф — это физическое представление персонажа в определенном шрифте. Например, управление разделенной кнопкой может быть украшено глифом символа контрольной отметки Unicode (U-2713).

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод инициализирует `mask` член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с BCSIF_GLYPH флагом, а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows. Когда функция сообщения возвращается, этот метод извлекает `himlGlyph` глиф из члена структуры.

## <a name="cbuttongetsplitimagelist"></a><a name="getsplitimagelist"></a>Кнопка:GetSplitImageList

Извлекает [список изображений](../../mfc/reference/cimagelist-class.md) для текущего управления кнопкой разделения.

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList.](../../mfc/reference/cimagelist-class.md)

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод инициализирует `mask` член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с BCSIF_IMAGE флагом, а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows. Когда функция сообщения возвращается, этот метод извлекает список изображений из `himlGlyph` члена структуры.

## <a name="cbuttongetsplitinfo"></a><a name="getsplitinfo"></a>Кнопка:GetSplitInfo

Извлекает параметры, определяющие, как Windows рисует текущее управление кнопкой разделения.

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pInfo*|(ваут) Указатель на [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуру, которая получает информацию о текущем управлении кнопкой разделения. Звонящее отвечает за выделение структуры.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод отправляет [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, которое описано в SDK Windows.

## <a name="cbuttongetsplitsize"></a><a name="getsplitsize"></a>Кнопка::GetSplitSize

Извлекает прямоугольник ограничивающего сядка компонента текущего управления кнопкой разделения.

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pSize*|(ваут) Указатель на структуру [СИЗЕ,](/windows/win32/api/windef/ns-windef-size) которая получает описание прямоугольника.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Когда управление разделенной кнопкой расширяется, он может отображать выпадающий компонент, такой как управление списком или управление пейджером. Этот метод извлекает прямоугольник, содержащий выпадающий компонент.

Этот метод инициализирует `mask` член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с BCSIF_SIZE флагом, а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows. Когда функция сообщения возвращается, этот метод извлекает прямоугольник из `size` члена структуры.

## <a name="cbuttongetsplitstyle"></a><a name="getsplitstyle"></a>Кнопка:GetSplitStyle

Извлекает стили сплит-кнопки, определяющие текущее управление кнопкой разделения.

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Битпое сочетание стилей сплит-кнопки. Для получения дополнительной `uSplitStyle` информаци [BUTTON_SPLITINFOи](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) см.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Стили сплит-кнопки определяют выравнивание, соотношение сторон и графический формат, с помощью которого Windows рисует значок сплит-кнопки.

Этот метод инициализирует `mask` член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с BCSIF_STYLE флагом, а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows. Когда функция сообщения возвращается, этот метод извлекает `uSplitStyle` стили сплит-кнопки из члена структуры.

## <a name="cbuttongetstate"></a><a name="getstate"></a>CButton:GetState

Извлекает состояние управления кнопкой.

```
UINT GetState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Немного поле, содержащее комбинацию значений, указывающих текущее состояние управления кнопками. В следующей таблице перечислены возможные значения.

|Состояние кнопки|Значение|Описание|
|------------------|-----------|-----------------|
|BST_UNCHECKED|0x0000|Начальное состояние.|
|BST_CHECKED|0x0001|Управление кнопкой проверяется.|
|BST_INDETERMINATE|0x0002|Состояние является неопределенным (только возможно, когда управление кнопками имеет три состояния).|
|BST_PUSHED|0x0004|Управление кнопкой нажата.|
|BST_FOCUS|0x0008|Управление кнопками имеет фокус.|

### <a name="remarks"></a>Remarks

Управление кнопками со стилем BS_3STATE или BS_AUTO3STATE кнопки создает флажок с третьим состоянием, которое называется неопределенным состоянием. Неопределенное состояние указывает на то, что флажок не проверяется и не проверяется.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttongettextmargin"></a><a name="gettextmargin"></a>Кнопка:GetTextMargin

Вызовите этот метод, чтобы `CButton` получить текстовую маржу объекта.

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Параметры

*pmargin*<br/>
Указатель на текстовый запас `CButton` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает поле текста.

### <a name="remarks"></a>Remarks

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность BCM_GETTEXTMARGIN сообщения, как описано в разделе [кнопки](/windows/win32/controls/buttons) SDK Windows.

## <a name="cbuttonsetbitmap"></a><a name="setbitmap"></a>CButton::SetBitmap

Вызовите эту функцию участника, чтобы связать новую битную карту с кнопкой.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Ручка бит-карты.

### <a name="return-value"></a>Возвращаемое значение

Ручка битной карты, ранее связанной с кнопкой.

### <a name="remarks"></a>Remarks

Бит-карта будет автоматически размещена на лицке кнопки, по центру по умолчанию. Если бит-карта слишком большая для кнопки, она будет обрезана с обеих сторон. Вы можете выбрать другие варианты выравнивания, включая следующие:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), который `SetBitmap` использует четыре bitmaps на кнопку, использует только один bitmap на кнопку. Когда кнопка нажата, бит-карта, как представляется, смещается вниз и вправо.

Вы несете ответственность за выпуск bitmap, когда вы сделали с ним.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttonsetbuttonstyle"></a><a name="setbuttonstyle"></a>Кнопка::SetButtonStyle

Изменяет стиль кнопки.

```cpp
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
Определяет [стиль кнопки.](../../mfc/reference/styles-used-by-mfc.md#button-styles)

*bRedraw*<br/>
Определяет, должна ли кнопка быть перерисована. Ненулевое значение перерисовывает кнопку. Значение 0 не перерисовывало кнопку. Кнопка перерисовывается по умолчанию.

### <a name="remarks"></a>Remarks

Используйте `GetButtonStyle` функцию участника для получения стиля кнопки. Словом низкого порядка полного стиля кнопки является стиль, специфичный для кнопок.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttonsetcheck"></a><a name="setcheck"></a>Кнопка::SetCheck

Устанавливает или сбрасывает состояние проверки кнопки радио или флажка.

```cpp
void SetCheck(int nCheck);
```

### <a name="parameters"></a>Параметры

*Nпроверьте*<br/>
Определяет состояние проверки. Возможные значения этого параметра:

|Значение|Значение|
|-----------|-------------|
|BST_UNCHECKED|Установите состояние кнопки для беспрепятственного.|
|BST_CHECKED|Установите состояние кнопки для проверки.|
|BST_INDETERMINATE|Установите состояние кнопки для неопределенного. Это значение можно использовать только в том случае, если кнопка имеет BS_3STATE или BS_AUTO3STATE стиле.|

### <a name="remarks"></a>Remarks

Эта функция члена не влияет на кнопку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttonsetcursor"></a><a name="setcursor"></a>CButton::SetCursor

Вызов ими функции участника, чтобы связать новый курсор с кнопкой.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Параметры

*hCursor*<br/>
Ручка курсора.

### <a name="return-value"></a>Возвращаемое значение

Ручка курсора, ранее связанная с кнопкой.

### <a name="remarks"></a>Remarks

Курсор будет автоматически размещен на лице кнопки, по центру по умолчанию. Если курсор слишком большой для кнопки, он будет обрезан с обеих сторон. Вы можете выбрать другие варианты выравнивания, включая следующие:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), который `SetCursor` использует четыре bitmaps на кнопку, использует только один курсор на кнопку. При нажатии кнопки курсор, как представляется, смещается вниз и вправо.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttonsetdropdownstate"></a><a name="setdropdownstate"></a>Кнопка CButton::SetDropDownState

Устанавливает состояние выпадающих вниз текущего управления кнопкой разделения.

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*fDropDown*|(в) TRUE установить состояние BST_DROPDOWNPUSHED; в противном случае, FALSE.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Управление разделенной кнопкой имеет стиль BS_SPLITBUTTON или BS_DEFSPLITBUTTON и состоит из кнопки и выпадающей стрелки справа от него. Для получения дополнительной информации [см.](/windows/win32/Controls/button-styles) Обычно состояние выпадения устанавливается, когда пользователь нажимает на стрелку выпадения вниз. Используйте этот метод для программного набора состояния элемента управления. Стрелка выпадения нарисована затенена, чтобы указать состояние.

Этот метод отправляет [BCM_SETDROPDOWNSTATE](/windows/win32/Controls/bcm-setdropdownstate) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_splitButton,* которая используется для программного доступа к разделенному управлению кнопкой. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает состояние управления сплит-кнопкой, чтобы указать, что стрелка выпадения нажата.

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

## <a name="cbuttonsetelevationrequired"></a><a name="setelevationrequired"></a>Кнопка CButton::УстановкаТребуется

Устанавливает состояние текущего элемента `elevation required`управления кнопкой, что необходимо для отображения элемента управления повышенной иконкой безопасности.

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*fElevationRequired*|(в) TRUE для `elevation required` установки состояния; в противном случае, FALSE.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Если для управления ссылкой кнопки или командной связи требуется `elevation required` повышенное разрешение безопасности для выполнения действия, установите элемент управления в состояние. Впоследствии Windows отображает значок щита управления учетным актом пользователя (UAC). Для получения дополнительной информации см. [MSDN](https://go.microsoft.com/fwlink/p/?linkid=18507)

Этот метод отправляет [BCM_SETSHIELD](/windows/win32/Controls/bcm-setshield) сообщение, которое описано в SDK Windows.

## <a name="cbuttonseticon"></a><a name="seticon"></a>Кнопка::SetIcon

Вызовите эту функцию участника, чтобы связать новую иконку с кнопкой.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
Ручка иконы.

### <a name="return-value"></a>Возвращаемое значение

Ручка значка, ранее связанная с кнопкой.

### <a name="remarks"></a>Remarks

Значок будет автоматически размещен на лицке кнопки, по центру по умолчанию. Если значок слишком большой для кнопки, он будет обрезан с обеих сторон. Вы можете выбрать другие варианты выравнивания, включая следующие:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

В отличие от [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), который `SetIcon` использует четыре bitmaps на кнопку, использует только один значок на кнопку. Когда кнопка нажата, значок, как представляется, смещается вниз и вправо.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttonsetimagelist"></a><a name="setimagelist"></a>Кнопка:SetImageList

Вызовите этот метод, чтобы `CButton` установить список изображений объекта.

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Параметры

*pbuttonImagelist*<br/>
Указатель на новый список изображений.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность BCM_SETIMAGELIST сообщения, как описано в разделе [Кнопки](/windows/win32/controls/buttons) SDK Windows.

## <a name="cbuttonsetnote"></a><a name="setnote"></a>Кнопка::SetNote

Устанавливает текст заметок для текущего управления командной ссылкой.

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszNote*|(в) Указатель на строку Unicode, которая устанавливается в качестве текста заметок для управления командой.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопок которых BS_COMMANDLINK или BS_DEFCOMMANDLINK.

Этот метод отправляет [BCM_SETNOTE](/windows/win32/Controls/bcm-setnote) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_cmdLink,* которая используется для программного доступа к управлению командной ссылкой. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает текст заметок для управления командной ссылкой.

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

## <a name="cbuttonsetsplitglyph"></a><a name="setsplitglyph"></a>CButton::SetSplitGlyph

Связывает указанный глиф с текущим управлением кнопки разделения.

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*chGlyph*|(в) Символ, который определяет глиф для использования в качестве стрелки сплит-кнопки выпадения вниз.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, которые имеют стиль кнопки BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Глиф — это физическое представление персонажа в определенном шрифте. Параметр *chGlyph* не используется в качестве глифа, но вместо этого используется для выбора глифа из набора системно определяемых глифов. Glyph стрелки по умолчанию указывается символом '6', и напоминает символ Unicode BLACK DOWN-POINTING TRIANGLE (U-25BC).

Этот метод `mask` инициализирует член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с `himlGlyph` BCSIF_GLYPH флагом и член с параметром *chGlyph,* а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows.

## <a name="cbuttonsetsplitimagelist"></a><a name="setsplitimagelist"></a>Кнопка::SetSplitImageList

Связывает [список изображений](../../mfc/reference/cimagelist-class.md) с текущим управлением кнопки разделения.

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pSplitImageList*|(в) Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) для присвоения текущего управления кнопкой разделения.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод `mask` инициализирует член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с `himlGlyph` BCSIF_IMAGE флагом и член с параметром *pSplitImageList,* а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows.

## <a name="cbuttonsetsplitinfo"></a><a name="setsplitinfo"></a>Кнопка:SetSplitInfo

Определяет параметры, определяющие, как Windows рисует текущее управление кнопкой разделения.

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pInfo*|(в) Указатель на [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуру, определяющую текущее управление кнопкой разделения.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Этот метод отправляет [BCM_SETSPLITINFO](/windows/win32/Controls/bcm-setsplitinfo) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_splitButton`переменную, которая используется для программного доступа к разделенному управлению кнопкой.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

Следующий пример кода изменяет глиф, который используется для стрелки сплит-кнопки выпадения вниз. Пример заменяет вверх-указывая треугольник глиф для по умолчанию вниз указывая треугольник глиф. Отображаемый глиф зависит от символа, указанного в составе `himlGlyph` `BUTTON_SPLITINFO` структуры. Глиф треугольника вниз указывает на то, что символ '6' и вверх-указывая треугольник глиф определяется символом '5'. Для сравнения, см. метод удобства, [CButton::SetSplitGlyph](#setsplitglyph).

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

## <a name="cbuttonsetsplitsize"></a><a name="setsplitsize"></a>Кнопка CButton::SetSplitSize

Устанавливает прямоугольник выпадающего компонента текущего управления кнопкой разделения.

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pSize*|(в) Указатель на структуру [СИЗЕ,](/windows/win32/api/windef/ns-windef-size) описывающую граничащий прямоугольник.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Когда управление разделенной кнопкой расширяется, он может отображать выпадающий компонент, такой как управление списком или управление пейджером. Этот метод определяет размер связующего прямоугольника, содержащего выпадающий компонент.

Этот метод `mask` инициализирует член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с `size` BCSIF_SIZE флагом и член с параметром *pSize,* а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_splitButton`переменную, которая используется для программного доступа к разделенному управлению кнопкой. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

Следующий пример кода удваивает размер стрелки сплит-кнопки выпадения вниз.

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

## <a name="cbuttonsetsplitstyle"></a><a name="setsplitstyle"></a>Кнопка::SetSplitStyle

Устанавливает стиль текущего управления кнопкой разделения.

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*uSplitStyle*|(в) Битпое сочетание стилей сплит-кнопки. Для получения дополнительной `uSplitStyle` информаци [BUTTON_SPLITINFOи](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) см.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Используйте этот метод только с элементами управления, стиль кнопки которого BS_SPLITBUTTON или BS_DEFSPLITBUTTON.

Стили сплит-кнопки определяют выравнивание, соотношение сторон и графический формат, с помощью которого Windows рисует значок сплит-кнопки. Для получения дополнительной `uSplitStyle` информаци [BUTTON_SPLITINFOи](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) см.

Этот метод `mask` инициализирует член [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) структуры с `uSplitStyle` BCSIF_STYLE флагом и член с параметром *uSplitStyle,* а затем отправляет эту структуру в [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) сообщение, описанное в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_splitButton`переменную, которая используется для программного доступа к разделенному управлению кнопкой.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает стиль стрелки сплит-кнопки выпадения вниз. В стиле BCSS_ALIGNLEFT отображается стрелка на левой стороне кнопки, а BCSS_STRETCH стиль сохраняет пропорции выпадающей стрелки при пересчете кнопки.

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

## <a name="cbuttonsetstate"></a><a name="setstate"></a>CButton::SetState

Устанавливает, выделяется ли элемент управления кнопками или нет.

```cpp
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>Параметры

*bHighlight*<br/>
Определяет, должна ли быть выделена кнопка. Ненулевое значение выделяет кнопку; значение 0 удаляет любое выделение.

### <a name="remarks"></a>Remarks

Выделение влияет на внешний вид кнопки управления. Это не влияет на состояние проверки кнопки радио или флажка.

Управление кнопкой автоматически выделяется, когда пользователь нажимает кнопку левой мыши. Выделение удаляется, когда пользователь выпускает кнопку мыши.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttonsettextmargin"></a><a name="settextmargin"></a>Кнопка::SetTextMargin

Вызовите этот метод, чтобы `CButton` установить текстовый запас объекта.

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Параметры

*pmargin*<br/>
Указатель на новый текстовый запас.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность BCM_SETTEXTMARGIN сообщения, как описано в разделе [кнопки](/windows/win32/controls/buttons) SDK Windows.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)<br/>
[Класс CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
