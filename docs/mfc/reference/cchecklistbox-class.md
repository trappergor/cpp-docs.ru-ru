---
title: Класс CCheckListBox
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: 72038e119f7d4483dcd6c6b343d20fd3655856b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533878"
---
# <a name="cchecklistbox-class"></a>Класс CCheckListBox

Предоставляет функции поля со списком Windows.

## <a name="syntax"></a>Синтаксис

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Создает объект `CCheckListBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCheckListBox::Create](#create)|Создает поля со списком Windows и присоединяет его к `CCheckListBox` объекта.|
|[CCheckListBox::DrawItem](#drawitem)|Вызывается платформой при изменении внешнего вида рисуемого владельцем список поля изменится.|
|[CCheckListBox::Enable](#enable)|Включает или отключает элемент поля контрольного списка.|
|[CCheckListBox::GetCheck](#getcheck)|Получает состояние флажка элемента.|
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Получает стиль элемента управления флажков.|
|[CCheckListBox::IsEnabled](#isenabled)|Определяет, включен ли элемент.|
|[CCheckListBox::MeasureItem](#measureitem)|Вызывается платформой при создании списка со стилем рисуемого владельцем.|
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Вызывается платформой для получения положение флажка элемента.|
|[CCheckListBox::SetCheck](#setcheck)|Задает состояние флажка элемента.|
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Задает стиль элемента управления флажков.|

## <a name="remarks"></a>Примечания

«Контрольный список для поля» отображает список элементов, таких как имена файлов. Каждый элемент в списке имеет флажок рядом с ним, пользователь может установите или снимите флажок.

`CCheckListBox` предназначен только для определяемых владельцем элементов управления, поскольку список содержит несколько текстовых строк. В самом простом случае Бокс контрольный список содержит текстовые строки и установите флажки, но не нужно вообще иметь текст. Например можно создать список маленькие точечные рисунки с помощью флажка рядом с каждым элементом.

Чтобы создать собственные поля со списком, должен быть производным класса из `CCheckListBox`. Чтобы собственный производный класс, написание конструктора для производного класса, а затем вызовите `Create`.

Если вы хотите обрабатывать сообщения Windows уведомления, отправленные поле со списком с родительским (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавить схему сообщений входа и обработчик сообщений функцию-член в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

**ON_** уведомления **(**`id`, `memberFxn` **)**

где `id` указывает идентификатор дочернего окна элемента управления, отправляющего уведомление и `memberFxn` имя функции-члена родительской вы написали для обработки уведомления.

Родительский прототип функции выглядит следующим образом:

**afx_msg** `void` `memberFxn` **();**

Имеется только одна запись схемы сообщений, относящихся конкретно к `CCheckListBox` (но см. также записи схемы сообщений для [CListBox](../../mfc/reference/clistbox-class.md)):

- ON_CLBN_CHKCHANGE пользователя изменилось состояние флажка элемента.

Если пакет контрольный список по умолчанию поля со списком (список строк с размером по умолчанию флажки слева от каждого), можно использовать значение по умолчанию [CCheckListBox::DrawItem](#drawitem) для рисования поля со списком. В противном случае необходимо переопределить [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) функции и [CCheckListBox::DrawItem](#drawitem) и [CCheckListBox::MeasureItem](#measureitem) функции.

Поле контрольного списка можно создать из шаблона диалогового окна или непосредственно в коде.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cchecklistbox"></a>  CCheckListBox::CCheckListBox

Создает объект `CCheckListBox`.

```
CCheckListBox();
```

### <a name="remarks"></a>Примечания

При создании `CCheckListBox` объекта в два этапа. Сначала определите класс, производный от `CCheckListBox`, затем вызвать `Create`, который инициализирует поля со списком Windows и присоединяет его к `CCheckListBox` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

##  <a name="create"></a>  CCheckListBox::Create

Создает поля со списком Windows и присоединяет его к `CCheckListBox` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль поля со списком. Стиль должен быть LBS_HASSTRINGS и LBS_OWNERDRAWFIXED (все элементы в списке имеют одинаковую высоту) или LBS_OWNERDRAWVARIABLE (элементы в списке являются различной высоты). Этот стиль можно объединять с другими [стили списков](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) LBS_USETABSTOPS, за исключением.

*Rect*<br/>
Указывает поле контрольного списка размер и положение. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.

*pParentWnd*<br/>
Указывает поле контрольного списка родительского окна (обычно `CDialog` объекта). Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления поле контрольного списка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CCheckListBox` объекта в два этапа. Во-первых, определите класс, производный от `CcheckListBox` , а затем вызвать `Create`, который инициализирует поля со списком Windows и присоединяет его к `CCheckListBox`. См. в разделе [CCheckListBox::CCheckListBox](#cchecklistbox) образец.

Когда `Create` выполняет, Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения в элементе управления поля контрольного списка.

Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить обработку сообщения по умолчанию, добавить схему сообщений для производного класса и функции-члены переопределение выше обработчик сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.

Примените следующий [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления поле контрольного списка:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_VSCROLL Чтобы добавить вертикальную полосу прокрутки

- WS_HSCROLL для добавления горизонтальной полосы прокрутки

- WS_GROUP для группировки элементов управления

- WS_TABSTOP чтобы разрешить переход к этому элементу управления

##  <a name="drawitem"></a>  CCheckListBox::DrawItem

Вызывается платформой при изменении внешнего вида изменяется рисуемый владельцем контрольный список.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе документа требуется.

### <a name="remarks"></a>Примечания

`itemAction` И `itemState` членами `DRAWITEMSTRUCT` структуры определяют рисования действие, которое должно быть выполнено.

По умолчанию эта функция выводит список флажок по умолчанию, состоящий из списка строк, каждый с размером по умолчанию флажок рядом с. Размер списка флажок находится в [создать](#create).

Переопределите эту функцию-член для реализации Рисование рисуемого владельцем контрольный список полей, которые не используются по умолчанию, такие как контрольный список поля со списками, которые не являются строками, с элементами переменной высоты или с флажками, которые не входят в левой части. Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* до завершения операции этой функции-члена.

Если поле элементы контрольного списка не ту же высоту, контрольный список поле стиля (указано в `Create`) должен быть ** LBS_OWNERVARIABLE и вам необходимо переопределить [MeasureItem](#measureitem) функции.

##  <a name="enable"></a>  CCheckListBox::Enable

Вызывайте эту функцию, чтобы включить или отключить элемент поля контрольного списка.

```
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс элемента поле контрольный список включения.

*bEnabled*<br/>
Указывает, включена ли элемент.

##  <a name="getcheck"></a>  CCheckListBox::GetCheck

Получает состояние указанного поля с флажком.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый от нуля индекс типа "флажок", содержащийся в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Состояние указанного поля с флажком. В следующей таблице перечислены возможные значения.

|Значение|Описание|
|-----------|-----------------|
|BST_CHECKED|Флажок установлен.|
|BST_UNCHECKED|Флажок не установлен.|
|BST_INDETERMINATE|Состояние флажка не определено.|

##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle

Вызовите эту функцию для получения стиля поле контрольного списка.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>Возвращаемое значение

Стиль элемента управления флажки.

### <a name="remarks"></a>Примечания

Сведения о возможных стилей, см. в разделе [SetCheckStyle](#setcheckstyle).

##  <a name="isenabled"></a>  CCheckListBox::IsEnabled

Вызывайте эту функцию, чтобы определить, включен ли элемент.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент включен; в противном случае 0.

##  <a name="measureitem"></a>  CCheckListBox::MeasureItem

Вызывается платформой при создании поля со списком в стиле не по умолчанию.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpMeasureItemStruct*<br/>
Длинный указатель на [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows измерений поле контрольного списка элементов. Если поле контрольного списка создается с помощью [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, платформа вызывает эту функцию-член для каждого элемента в поле со списком. В противном случае этот член вызывается только один раз.

##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition

Платформа вызывает эту функцию для получения позиции и размера флажка в элементе.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>Параметры

*rectItem*<br/>
Положение и размер элемента списка.

*rectCheckBox*<br/>
По умолчанию положения и размера флажка элемента.

### <a name="return-value"></a>Возвращаемое значение

Установите флажок, положение и размер элемента.

### <a name="remarks"></a>Примечания

Реализация по умолчанию возвращает только по умолчанию положение и размер поля с флажком (`rectCheckBox`). По умолчанию типа "флажок" выравнивается в левом верхнем углу элемента и размер стандартный флажок. Возможны случаи, когда требуется флажков в правой части или хотите флажок больше или меньше. В этих случаях переопределить `OnGetCheckPosition` изменение флажок положение и размер в элементе.

##  <a name="setcheck"></a>  CCheckListBox::SetCheck

Задает состояние указанного поля с флажком.

```
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый от нуля индекс типа "флажок", содержащийся в поле со списком.

*Проверьте*<br/>
Состояние кнопки для указанного флажка. Возможные значения в разделе "Примечания".

### <a name="remarks"></a>Примечания

В следующей таблице перечислены возможные значения для *проверьте* параметра.

|Значение|Описание|
|-----------|-----------------|
|BST_CHECKED|Установите указанный флажок.|
|BST_UNCHECKED|Снимите флажок указанного.|
|BST_INDETERMINATE|Установите состояние указанного флажок в неопределенном состоянии.<br /><br /> Это состояние доступна только в том случае, если используется стиль флажок BS_AUTO3STATE или BS_3STATE. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).|

##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle

Вызывайте эту функцию для задания стиля флажков в окне контрольного списка.

```
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
Определяет стиль флажки в поле контрольного списка.

### <a name="remarks"></a>Примечания

Допустимы стили являются:

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

Сведения об этих стилей см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).

## <a name="see-also"></a>См. также

[Пример MFC TSTCON](../../visual-cpp-samples.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)
