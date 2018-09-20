---
title: Класс CListBox | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
dev_langs:
- C++
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ceef559e83b111a9ca8bcb96541fe8fbda19cf0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387182"
---
# <a name="clistbox-class"></a>CListBox-класс

Предоставляет функции списка Windows.

## <a name="syntax"></a>Синтаксис

```
class CListBox : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|Создает объект `CListBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CListBox::AddString](#addstring)|Добавляет строку в поле со списком.|
|[CListBox::CharToItem](#chartoitem)|Переопределение, чтобы обеспечить пользовательский WM_CHAR обработки для списков рисуемый владельцем, которых нет строки.|
|[CListBox::CompareItem](#compareitem)|Вызывается платформой для определения позиции нового элемента в поле со списком отсортированный пользовательской отрисовки.|
|[CListBox::Create](#create)|Поле со списком Windows создает и присоединяет его к `CListBox` объекта.|
|[CListBox::DeleteItem](#deleteitem)|Вызывается платформой, когда пользователь удаляет элемент из списка рисуемого владельцем.|
|[CListBox::DeleteString](#deletestring)|Удаляет строку из списка.|
|[CListBox::Dir](#dir)|Добавляет имена файлов, дисков или оба из текущего каталога в поле со списком.|
|[CListBox::DrawItem](#drawitem)|Вызывается платформой при изменении внешнего вида рисуемого владельцем список поля изменится.|
|[CListBox::FindString](#findstring)|Поиск строки в поле со списком.|
|[CListBox::FindStringExact](#findstringexact)|Выполняет поиск первой строки списка, которая совпадает с указанной строкой.|
|[CListBox::GetAnchorIndex](#getanchorindex)|Возвращает отсчитываемый от нуля индекс текущего элемента привязки в поле со списком.|
|[CListBox::GetCaretIndex](#getcaretindex)|Определяет индекс элемента, который имеет прямоугольник фокуса в поле со списком с множественным выбором.|
|[CListBox::GetCount](#getcount)|Возвращает число строк в поле со списком.|
|[CListBox::GetCurSel](#getcursel)|Возвращает отсчитываемый от нуля индекс строки, выбранного в поле со списком.|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пикселях, что поле со списком может прокручиваться по горизонтали.|
|[CListBox::GetItemData](#getitemdata)|Возвращает 32-разрядное значение, связанное с элементом списка.|
|[CListBox::GetItemDataPtr](#getitemdataptr)|Возвращает указатель на элемент списка.|
|[CListBox::GetItemHeight](#getitemheight)|Определяет высоту элементов в поле со списком.|
|[CListBox::GetItemRect](#getitemrect)|Возвращает ограничивающий прямоугольник элемента списка, так как он отображается в текущий момент.|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Получает число элементов в столбце.|
|[CListBox::GetLocale](#getlocale)|Извлекает идентификатор языкового стандарта для поле со списком.|
|[CListBox::GetSel](#getsel)|Возвращает состояние выбора элемента списка.|
|[CListBox::GetSelCount](#getselcount)|Возвращает число строк, выбранного в поле со списком с множественным выбором.|
|[CListBox::GetSelItems](#getselitems)|Возвращает индексы строки, выбранной в поле со списком.|
|[CListBox::GetText](#gettext)|Копирует элемент списка в буфер.|
|[CListBox::GetTextLen](#gettextlen)|Возвращает длину в байтах элемента списка.|
|[CListBox::GetTopIndex](#gettopindex)|Возвращает индекс первой видимой строки в поле со списком.|
|[CListBox::InitStorage](#initstorage)|Выделяет блоки памяти для элементов списка и строк.|
|[CListBox::InsertString](#insertstring)|Вставляет строку в определенном месте в поле со списком.|
|[CListBox::ItemFromPoint](#itemfrompoint)|Возвращает индекс элемента списка ближайшего точку.|
|[CListBox::MeasureItem](#measureitem)|Вызывается платформой при рисуемого владельцем поле со списком, чтобы определить список измерений.|
|[CListBox::ResetContent](#resetcontent)|Удаляет все записи из списка.|
|[CListBox::SelectString](#selectstring)|Выполняет поиск и выбирает строку в поле со списком с поддержкой единственного выбора.|
|[CListBox::SelItemRange](#selitemrange)|Выбирает или отменяет выделение диапазона строк в поле со списком с множественным выбором.|
|[CListBox::SetAnchorIndex](#setanchorindex)|Задает привязку в поле со списком множественного выбора, чтобы начать расширенного выделения.|
|[CListBox::SetCaretIndex](#setcaretindex)|Задает прямоугольник фокуса к элементу по указанному индексу в поле со списком с множественным выбором.|
|[CListBox::SetColumnWidth](#setcolumnwidth)|Задает ширину столбца по нескольким столбцам списка.|
|[CListBox::SetCurSel](#setcursel)|Выбирает строку списка.|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Задает ширину в пикселях, что поле со списком может прокручиваться по горизонтали.|
|[CListBox::SetItemData](#setitemdata)|Задает 32-разрядное значение, связанное с элементом списка.|
|[CListBox::SetItemDataPtr](#setitemdataptr)|Задает указатель на элемент списка.|
|[CListBox::SetItemHeight](#setitemheight)|Задает высоту элементов в поле со списком.|
|[CListBox::SetLocale](#setlocale)|Задает идентификатор языкового стандарта для поле со списком.|
|[CListBox::SetSel](#setsel)|Выбирает или отменяет выделение элемента списка в поле со списком с множественным выбором.|
|[CListBox::SetTabStops](#settabstops)|Задает позиции табуляции в поле со списком.|
|[CListBox::SetTopIndex](#settopindex)|Задает отсчитываемый от нуля индекс первой видимой строки в поле со списком.|
|[CListBox::VKeyToItem](#vkeytoitem)|Переопределите, чтобы предоставить пользовательские WM_KEYDOWN, обработка для поля списка LBS_WANTKEYBOARDINPUT набор стилей.|

## <a name="remarks"></a>Примечания

Поле со списком отображает список элементов, таких как имена файлов, который пользователь может просмотреть и выбрать.

В поле со списком поддержкой единственного выбора пользователь может выбрать только один элемент. В поле со списком множественным выбором можно выбрать диапазон элементов. Когда пользователь выбирает элемент, он выделяется, и поле со списком отправляет сообщение уведомления в родительское окно.

Поле со списком можно создать из шаблона диалогового окна или непосредственно в коде. Чтобы создать напрямую, создания `CListBox` объекта, а затем вызовите [создать](#create) функцию-член для создания элемента управления списка Windows и присоединить его к `CListBox` объекта. Чтобы использовать поле со списком в шаблон диалогового окна, объявите переменную списков в классе диалогового окна, а затем использовать `DDX_Control` в классе диалогового окна `DoDataExchange` для подключения к переменной-члена для элемента управления. (это выполняется для вас автоматически при добавлении управляющая переменная в классе диалогового окна.)

Построение может быть задачей в класс, производный от `CListBox`. Создание конструктора для производного класса, а также вызова `Create` из в конструкторе.

Если вы хотите обрабатывать сообщения Windows уведомления, отправленные поле со списком с родительским (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавить схему сообщений входа и обработчик сообщений функцию-член в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

`ON_Notification( id, memberFxn )`

где `id` указывает идентификатор дочернего окна элемента управления списка, отправляющего уведомление и `memberFxn` имя функции-члена родительской вы написали для обработки уведомления.

Родительский прототип функции выглядит следующим образом:

`afx_msg void memberFxn( );`

Ниже приведен список потенциальных записей карты и описание вариантов, в которых они бы отправлены родительским.

- ON_LBN_DBLCLK пользователь дважды щелкает строку в поле со списком. Только окно списка, имеющий [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля будет отправлять это сообщение уведомления.

- Поле со списком ON_LBN_ERRSPACE не удается выделить достаточно памяти для выполнения запроса.

- ON_LBN_KILLFOCUS поле со списком теряет фокус ввода.

- Отменяется ON_LBN_SELCANCEL текущего списка выделения. Это сообщение отправляется только в том случае, если поле со списком имеет стиль LBS_NOTIFY.

- Изменился ON_LBN_SELCHANGE элементом, выбранным в поле со списком. Это уведомление не отправляется, если выделение изменяется при [CListBox::SetCurSel](#setcursel) функция-член. Это уведомление применяется только к полем со списком, в которой LBS_NOTIFY стиль. LBN_SELCHANGE отправляется уведомление для списка множественного выбора каждый раз, когда пользователь нажимает клавишу со стрелкой, даже если изменяется.

- ON_LBN_SETFOCUS поле со списком получает фокус ввода.

- ON_WM_CHARTOITEM рисуемого владельцем списка, имеющий без оговорок получает сообщение WM_CHAR.

- ON_WM_VKEYTOITEM объект списка со стилем LBS_WANTKEYBOARDINPUT получает сообщение WM_KEYDOWN.

Если вы создаете `CListBox` объекта в диалоговом окне (с помощью ресурса диалогового окна), `CListBox` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

Если вы создаете `CListBox` объекта в окне, может потребоваться уничтожить `CListBox` объекта. Если вы создаете `CListBox` объект в стеке, он будет удален автоматически. При создании `CListBox` объект в куче с помощью **новый** функцию, необходимо вызвать **удалить** в объекте уничтожить его, когда пользователь закрывает родительского окна.

Если выделять память в `CListBox` объекта, переопределить `CListBox` деструктор для удаления выделения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="addstring"></a>  CListBox::AddString

Добавляет строку в поле со списком.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*lpszItem*<br/>
Указатель на заканчивающуюся нулем строку, который должен быть добавлен.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс строки в поле со списком. Возвращает значение LB_ERR при возникновении ошибки; Возвращаемое значение является LB_ERRSPACE, если недостаточно места для хранения новой строки.

### <a name="remarks"></a>Примечания

Если поле со списком не был создан с помощью [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, строка добавляется в конец списка. В противном случае строка вставляется в списке, и список отсортирован. Если поле со списком была создана со стилем LBS_SORT, но не [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, платформа сортирует список с одного или нескольких вызовов к `CompareItem` функция-член.

Используйте [InsertString](#insertstring) для вставки строки в определенное расположение в поле со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

##  <a name="chartoitem"></a>  CListBox::CharToItem

Вызывается платформой, когда поле списка родительское окно получает сообщение WM_CHARTOITEM из списка.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Параметры

*nKey*<br/>
ANSI код символа, введенного пользователем.

*nIndex*<br/>
Текущая позиция курсора списков.

### <a name="return-value"></a>Возвращаемое значение

Возвращает - 1 или - 2 для дальнейших действий или неотрицательное число, указывающее индекс элемента списка, для которого следует выполнить действие по умолчанию для клавиши. Реализация по умолчанию возвращается значение-1.

### <a name="remarks"></a>Примечания

WM_CHARTOITEM сообщение отправляется в списке, при получении сообщения WM_CHAR, но только в том случае, если поле со списком удовлетворяет всем следующим критериям:

- Представляет список рисуемого владельцем.

- Не поддерживает [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) в стиле набора.

- Содержит по крайней мере один элемент.

Никогда не следует вызывать эту функцию самостоятельно. Переопределите эту функцию для предоставления собственных обычной обработки сообщений клавиатуры.

В переопределении должен возвращать значение, чтобы сообщить платформе какое действие вы выполнили. Возвращаемое значение - 1 или - 2 указывает обрабатывать все аспекты выбора элемента и не требует дальнейших действий в списке. Перед возвратом - 1 или - 2, можно выбрать в списке или переместите курсор или оба. Чтобы выбрать в списке, используйте [SetCurSel](#setcursel) или [SetSel](#setsel). Чтобы переместить курсор, используйте [SetCaretIndex](#setcaretindex).

Возвращаемое значение 0 или больше указывает индекс элемента в поле со списком и указывает, что поле со списком должно выполнять действие по умолчанию для клавиши на данный элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

##  <a name="clistbox"></a>  CListBox::CListBox

Создает объект `CListBox`.

```
CListBox();
```

### <a name="remarks"></a>Примечания

При создании `CListBox` объекта в два этапа. Во-первых, вызовите конструктор `ClistBox` , а затем вызвать `Create`, который инициализирует поле со списком Windows и присоединяет его к `CListBox`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

##  <a name="compareitem"></a>  CListBox::CompareItem

Вызывается платформой для определения относительной позиции нового элемента в поле со списком отсортированный пользовательской отрисовки.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Параметры

*lpCompareItemStruct*<br/>
Длинный указатель на `COMPAREITEMSTRUCT` структуры.

### <a name="return-value"></a>Возвращаемое значение

Показывает относительное положение двух элементов, описанных в [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) структуры. Это может быть любой из следующих значений:

|Значение|Значение|
|-----------|-------------|
|-1|Элемент 1 предшествует элемент 2.|
|0|1 и 2 элемент сортировки же.|
|1|Элемент 1 сортирует после элемента 2.|

См. в разделе [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) описание `COMPAREITEMSTRUCT` структуры.

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. При создании рисуемого владельцем поле со списком в стиле LBS_SORT, необходимо переопределить эту функцию-член для помощи в framework в сортировке новые элементы добавлены в поле со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

##  <a name="create"></a>  CListBox::Create

Поле со списком Windows создает и присоединяет его к `CListBox` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль окна списка. Применить любое сочетание [стили списков](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) в поле.

*Rect*<br/>
Указывает список размер и положение. Может быть либо `CRect` объекта или `RECT` структуры.

*pParentWnd*<br/>
Указывает список родительского окна (обычно `CDialog` объекта). Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления списка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CListBox` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который инициализирует поле со списком Windows и присоединяет его к `CListBox` объекта.

Когда `Create` выполняет, Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения в элемент управления «список».

Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить обработку сообщения по умолчанию, являются производными от класса `CListBox`, добавить схему сообщений к новому классу и переопределить выше функции-члены обработчика сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.

Примените следующий [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления списка.

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_VSCROLL Чтобы добавить вертикальную полосу прокрутки

- WS_HSCROLL для добавления горизонтальной полосы прокрутки

- WS_GROUP для группировки элементов управления

- WS_TABSTOP чтобы разрешить переход к этому элементу управления

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

##  <a name="deleteitem"></a>  CListBox::DeleteItem

Вызывается платформой, когда пользователь удаляет элемент из рисуемого владельцем `CListBox` объекта или уничтожает поле со списком.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDeleteItemStruct*<br/>
Длинный указатель на Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) структуру, содержащую сведения о удаляемого элемента.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для повторной отрисовки поверхности рисования владельцем поле со списком при необходимости.

См. в разделе [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) описание `DELETEITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

##  <a name="deletestring"></a>  CListBox::DeleteString

Удаляет элемент в позиции *nIndex* из списка.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс строки для удаления.

### <a name="return-value"></a>Возвращаемое значение

Число строк, оставшихся в списке. Если возвращаемое значение равно LB_ERR *nIndex* указывает индексом большим, чем число элементов в списке.

### <a name="remarks"></a>Примечания

Все элементы, следующие *nIndex* теперь перейти на одну позицию вниз. Например если поле со списком содержит два элемента, удаление первого элемента приведет к оставшиеся элемент теперь на первом месте. *nIndex*= 0 в первой позиции элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

##  <a name="dir"></a>  CListBox::Dir

Добавляет список имен файлов, дисков или оба значения в поле со списком.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Параметры

*attr*<br/>
Может быть любым сочетанием **перечисления** значений описано в разделе `CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus), или любое сочетание следующих значений:

|Значение|Значение|
|-----------|-------------|
|0x0000|Файл можно чтение и запись.|
|0x0001|Файл может быть считываться, но не записываются.|
|0x0002|Файл является скрытым и не отображается в каталоге.|
|0x0004|Файл является системным.|
|0x0010|Имя, указанное в *lpszWildCard* указывает каталог.|
|0x0020|Файл помещен в архив.|
|0x4000|Все диски, которые соответствуют именем, указанным *lpszWildCard*.|
|0x8000|Эксклюзивные флаг. Если флаг exclusive, перечислены только файлы указанного типа. В противном случае файлы указанного типа, перечислены в дополнение к файлам «normal».|

*lpszWildCard*<br/>
Указывает строку спецификация файла. Строка может содержать подстановочные знаки (например, *.\*).

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс последнего имени файла, добавляемого в список. Возвращает значение LB_ERR при возникновении ошибки; Возвращаемое значение является LB_ERRSPACE, если недостаточно места для хранения новых строк.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

##  <a name="drawitem"></a>  CListBox::DrawItem

Вызывается платформой при изменении внешнего вида рисуемого владельцем список поля изменится.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе документа требуется.

### <a name="remarks"></a>Примечания

`itemAction` И `itemState` членами `DRAWITEMSTRUCT` структуры определяют рисования действие, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CListBox` объекта. Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* перед этим членом завершении функции.

См. в разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание `DRAWITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

##  <a name="findstring"></a>  CListBox::FindString

Находит первую строку в поле со списком, который содержит указанный префикс без изменения списков выбора.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит отсчитываемый от нуля индекс элемента перед первым элементом для поиска. Когда достигается конец списка, он продолжает в верхней части списка обратно элемент, заданный параметром *nStartAfter*. Если *nStartAfter* равно -1, поле со списком всего осуществляется с самого начала.

*lpszItem*<br/>
Указатель на заканчивающуюся нулем строку, содержащая префикс для поиска. Поиск является независимым, регистр, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс, соответствующий элемент или LB_ERR, если поиск завершился неудачей.

### <a name="remarks"></a>Примечания

Используйте [SelectString](#selectstring) функции-члена для поиска и выберите строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

##  <a name="findstringexact"></a>  CListBox::FindStringExact

Выполняет поиск первой строки списка, которая соответствует строке, указанной в *lpszFind*.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Параметры

*nIndexStart*<br/>
Указывает отсчитываемый от нуля индекс элемента перед первым элементом для поиска. Когда достигается конец списка, он продолжает в верхней части списка обратно элемент, заданный параметром *nIndexStart*. Если *nIndexStart* равно -1, поле со списком всего осуществляется с самого начала.

*lpszFind*<br/>
Указатель на заканчивающуюся нулем строку для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не учитывается регистр, поэтому строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс, соответствующий элемент или LB_ERR, если поиск завершился неудачей.

### <a name="remarks"></a>Примечания

Если поле со списком был создан с помощью стиле рисуемый владельцем, но без [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, `FindStringExact` функция-член пытается найти соответствие двойное значение на соответствие значению из *lpszFind*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

##  <a name="getanchorindex"></a>  CListBox::GetAnchorIndex

Возвращает отсчитываемый от нуля индекс текущего элемента привязки в поле со списком.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс текущего элемента привязки, если выполнение прошло успешно; в противном случае LB_ERR.

### <a name="remarks"></a>Примечания

В поле со списком множественным выбором элемент привязки является первому и последнему элементу в блоке смежных выбранных элементов.

### <a name="example"></a>Пример

  См. в примере [CListBox::SetAnchorIndex](#setanchorindex).

##  <a name="getcaretindex"></a>  CListBox::GetCaretIndex

Определяет индекс элемента, который имеет прямоугольник фокуса в поле со списком с множественным выбором.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента, который имеет прямоугольник фокуса в поле со списком. Если поле со списком поле со списком с поддержкой единственного выбора, возвращается индекс элемента, который выбран, если таковые имеются.

### <a name="remarks"></a>Примечания

Элемент может или не может быть выбран.

### <a name="example"></a>Пример

  См. в примере [CListBox::SetCaretIndex](#setcaretindex).

##  <a name="getcount"></a>  CListBox::GetCount

Получает число элементов в поле со списком.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в поле со списком или LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Количество возвращаемых результатов является один больше, чем значение индекса последнего элемента (индекс начинается с нуля).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

##  <a name="getcursel"></a>  CListBox::GetCurSel

Возвращает отсчитываемый от нуля индекс выбранного элемента, при наличии таковой, в поле со списком с поддержкой единственного выбора.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс выбранного элемента, если это поле со списком с поддержкой единственного выбора. Это LB_ERR, если элемент не выбран в данный момент.

В поле список с множественным выбором, индекс элемента, который имеет фокус.

### <a name="remarks"></a>Примечания

Не вызывайте `GetCurSel` для списка множественного выбора. Используйте [CListBox::GetSelItems](#getselitems) вместо этого.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

##  <a name="gethorizontalextent"></a>  CListBox::GetHorizontalExtent

Извлекает из списка ширину в пикселях, на которое он может прокручиваться по горизонтали.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прокручиваемые ширина поле со списком в пикселях.

### <a name="remarks"></a>Примечания

Это применимо только в том случае, если поле со списком имеет горизонтальную полосу прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

##  <a name="getitemdata"></a>  CListBox::GetItemData

Получает значение двойного слова, предоставляемую приложением, связанный с элементом указанного списка.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

32-битное значение, связанный с элементом, или LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Двойное значение было *dwItemData* параметр [SetItemData](#setitemdata) вызова.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

##  <a name="getitemdataptr"></a>  CListBox::GetItemDataPtr

Извлекает значение 32-разрядных предоставленную приложением, связанное с элементом указанного списка как указатель (**void** <strong>\*</strong>).

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель или значение -1, если произошла ошибка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

##  <a name="getitemheight"></a>  CListBox::GetItemHeight

Определяет высоту элементов в поле со списком.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента в поле со списком. Этот параметр используется только в том случае, если поле со списком имеет стиль LBS_OWNERDRAWVARIABLE; в противном случае он задается значение 0.

### <a name="return-value"></a>Возвращаемое значение

Высота в пикселях элементов в поле со списком. Если поле со списком имеет [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, возвращаемое значение имеет высоту элемента, заданного посредством *nIndex*. Если возникает ошибка, возвращается LB_ERR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

##  <a name="getitemrect"></a>  CListBox::GetItemRect

Возвращает размеры прямоугольника границы поле со списком элемента, как он отображается в текущий момент в окне списка.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента.

*lpRect*<br/>
Указывает, длинный указатель на [структура RECT](../../mfc/reference/rect-structure1.md) , получающий список клиентских координат элемента.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

##  <a name="getlistboxinfo"></a>  CListBox::GetListBoxInfo

Получает число элементов в столбце.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов на столбце `CListBox` объекта.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности [LB_GETLISTBOXINFO](/windows/desktop/Controls/lb-getlistboxinfo) сообщения, как описано в пакете Windows SDK.

##  <a name="getlocale"></a>  CListBox::GetLocale

Возвращает языковой стандарт, используемый в списке.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение идентификатор (LCID) языка для строк в поле со списком.

### <a name="remarks"></a>Примечания

Языковой стандарт используется, например, для определения порядка сортировки строк из отсортированного списка.

### <a name="example"></a>Пример

  См. в примере [CListBox::SetLocale](#setlocale).

##  <a name="getsel"></a>  CListBox::GetSel

Извлекает состояние выделения элемента.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Положительное число, если указанный элемент выбран; в противном случае — 0. Возвращает значение LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Эта функция-член работает с обоих одним - и список с множественным выбором.

Чтобы получить индекс элемента списка, выбранных в настоящий момент, используйте [CListBox::GetCurSel](#getcursel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

##  <a name="getselcount"></a>  CListBox::GetSelCount

Возвращает общее число выбранных элементов в поле со списком с множественным выбором.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число выбранных элементов в поле со списком. Если поле со списком поле со списком с поддержкой единственного выбора, возвращаемое значение является LB_ERR.

### <a name="example"></a>Пример

  См. в примере [CListBox::GetSelItems](#getselitems).

##  <a name="getselitems"></a>  CListBox::GetSelItems

Заполняет буфер массив целых чисел, который определяет элемент число выбранных элементов в поле со списком с множественным выбором.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>Параметры

*nMaxItems*<br/>
Указывает максимальное количество выбранных элементов, в котором номера элемента должны располагаться в буфере.

*rgIndex*<br/>
Задает указатель на буфер, достаточный для количество целых чисел, определяемое *nMaxItems*.

### <a name="return-value"></a>Возвращаемое значение

Фактическое число элементов помещаются в буфер. Если поле со списком поле со списком с поддержкой единственного выбора, возвращаемое значение является `LB_ERR`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

##  <a name="gettext"></a>  CListBox::GetText

Получает строку из списка.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс строки, которые требуется извлечь.

*lpszBuffer*<br/>
Указатель на буфер, получающий строки. Буфер должен иметь достаточно места для строки и знак завершения null. Размер строки можно определить заранее, вызвав `GetTextLen` функция-член.

*rString*<br/>
Ссылка на объект `CString`.

### <a name="return-value"></a>Возвращаемое значение

Длина строки, за исключением завершающего нуль-символа (в байтах). Если *nIndex* не указывает допустимый индекс, возвращаемым значением является LB_ERR.

### <a name="remarks"></a>Примечания

Вторая форма этого члена функции заливки `CString` с текстом строки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

##  <a name="gettextlen"></a>  CListBox::GetTextLen

Получает длину строки в элементе списка.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс строки.

### <a name="return-value"></a>Возвращаемое значение

Длина строки в символах, за исключением завершающего нуль-символа. Если *nIndex* не указывает допустимый индекс, возвращаемым значением является LB_ERR.

### <a name="example"></a>Пример

  См. в примере [CListBox::GetText](#gettext).

##  <a name="gettopindex"></a>  CListBox::GetTopIndex

Возвращает отсчитываемый от нуля индекс первой видимой позиции в поле со списком.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первой видимой позиции в поле со списком, в случае успешного выполнения LB_ERR в противном случае.

### <a name="remarks"></a>Примечания

Первоначально элемент 0 — в верхней части списка, но если поле со списком прокрутку, еще один элемент может быть в верхней.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

##  <a name="initstorage"></a>  CListBox::InitStorage

Выделяет память для хранения элементов списка.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Параметры

*nItems*<br/>
Указывает количество добавляемых элементов.

*nBytes*<br/>
Указывает объем памяти в байтах для выделения для элемента строки.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения максимальное количество элементов, которые может вместить поле со списком перед выделением памяти при необходимости, в противном случае LB_ERRSPACE, то не хватает памяти.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию перед добавлением большое количество элементов, `CListBox`.

Эта функция помогает ускорить инициализации списка полей, имеющих большое количество элементов (более 100). Он выделяет указанный объем памяти, чтобы последующие [AddString](#addstring), [InsertString](#insertstring), и [Dir](#dir) функции принимают кратчайшие сроки. Оценки можно использовать для параметров. Если вы пересмотреть, выделения дополнительной памяти; Если вы недооцените требования, обычного выделения используется для элементов, которые вычитаются из суммы предварительно.

Windows 95/98 только: *nItems* ограничен 16-разрядных значений. Это означает, что списки с множественным не может содержать более 32 767 элементы. Несмотря на то, что количество элементов является ограниченным, общий размер элементов в поле со списком ограничено только объемом доступной памяти.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

##  <a name="insertstring"></a>  CListBox::InsertString

Вставляет строку в поле со списком.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс позиции для вставки строки. Если этот параметр имеет значение -1, строка добавляется в конец списка.

*lpszItem*<br/>
Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. Возвращает значение LB_ERR при возникновении ошибки; Возвращаемое значение является LB_ERRSPACE, если недостаточно места для хранения новой строки.

### <a name="remarks"></a>Примечания

В отличие от [AddString](#addstring) функции-члена `InsertString` не ведет список с [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

##  <a name="itemfrompoint"></a>  CListBox::ItemFromPoint

Определяет элемент списка ближайшего точку, указанную в *pt*.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Точка, для которого необходимо найти ближайший элемент, указанный относительно левого верхнего угла клиентской области окна списка.

*bOutside*<br/>
Ссылка на БУЛЕВОЙ переменной, которой будет присвоено значение TRUE, если *pt* находится за пределами области ближайшего элемента списка, значение FALSE, если *pt* находится внутри клиентской области ближайшего элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента, ближайшего к точке, указанной в *pt*.

### <a name="remarks"></a>Примечания

Чтобы определить, какой элемент списка, то курсор мыши перемещается над можно использовать эту функцию.

### <a name="example"></a>Пример

  См. в примере [CListBox::SetAnchorIndex](#setanchorindex).

##  <a name="measureitem"></a>  CListBox::MeasureItem

Вызывается платформой при создании списка со стилем рисуемого владельцем.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpMeasureItemStruct*<br/>
Длинный указатель на [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows из списка измерений. Если поле со списком создается с помощью [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, платформа вызывает эту функцию-член для каждого элемента в поле со списком. В противном случае этот член вызывается только один раз.

Для получения дополнительных сведений об использовании [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля в списке пользовательской отрисовки, созданных с помощью `SubclassDlgItem` функцию-член `CWnd`, см. в обсуждении [14 технических Примечание](../../mfc/tn014-custom-controls.md).

См. в разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

##  <a name="resetcontent"></a>  CListBox::ResetContent

Удаляет все элементы из списка.

```
void ResetContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

##  <a name="selectstring"></a>  CListBox::SelectString

Поиск для элемента списка, соответствующую указанной строке, и если найден соответствующий элемент, он выбирает элемент.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит отсчитываемый от нуля индекс элемента перед первым элементом для поиска. Когда достигается конец списка, он продолжает в верхней части списка обратно элемент, заданный параметром *nStartAfter*. Если *nStartAfter* равно -1, поле со списком всего осуществляется с самого начала.

*lpszItem*<br/>
Указатель на заканчивающуюся нулем строку, содержащая префикс для поиска. Поиск является независимым, регистр, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс выбранного элемента, если поиск был успешным. Если поиск завершился неудачей, возвращаемым значением является LB_ERR и текущего выделения не изменяется.

### <a name="remarks"></a>Примечания

Поле со списком может прокручиваться, при необходимости, для отображения выбранного элемента в представлении.

Эта функция-член не может использоваться с полем со списком, имеющий [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля.

Элемент выбирается только в том случае, если его начальные символы (от начальной) соответствует символам в строкой, указанной параметром *lpszItem*.

Используйте `FindString` функции-члена для поиска строки без выбора элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

##  <a name="selitemrange"></a>  CListBox::SelItemRange

Выбирает несколько последовательных элементов в поле со списком с множественным выбором.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>Параметры

*bSelect*<br/>
Указывает, как выбрать в списке. Если *bSelect* имеет значение TRUE, выбран и выделенной строки; Если значение равно FALSE, выделение удаляется строка больше не выбран.

*nFirstItem*<br/>
Указывает отсчитываемый от нуля индекс первого элемента для задания.

*nLastItem*<br/>
Указывает отсчитываемый от нуля индекс последнего элемента для задания.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только с полями список с множественным выбором. Если вам нужно выбрать только один элемент в поле со списком с множественным выбором — то есть если *nFirstItem* равен *nLastItem* — вызвать [SetSel](#setsel) функцию-член, вместо этого.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

##  <a name="setanchorindex"></a>  CListBox::SetAnchorIndex

Задает привязку в поле со списком множественного выбора, чтобы начать расширенного выделения.

```
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента списка, который будет служить в качестве привязки.

### <a name="remarks"></a>Примечания

В поле со списком множественным выбором элемент привязки является первому и последнему элементу в блоке смежных выбранных элементов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

##  <a name="setcaretindex"></a>  CListBox::SetCaretIndex

Задает прямоугольник фокуса к элементу по указанному индексу в поле со списком с множественным выбором.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента для получения прямоугольника фокуса в поле со списком.

*bScroll*<br/>
Если это значение равно 0, элемент при прокрутке, пока он не полностью видимым. Если это значение не равно 0, элемент при прокрутке пока он отображается по крайней мере частично.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Если элемент не отображается, если они оказались в представление.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

##  <a name="setcolumnwidth"></a>  CListBox::SetColumnWidth

Задает ширину в пикселях всех столбцов в списке по нескольким столбцам (созданные с помощью [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля).

```
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>Параметры

*cxWidth*<br/>
Задает ширину в пикселях всех столбцов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

##  <a name="setcursel"></a>  CListBox::SetCurSel

Выбирает строку и прокручивает его на экране, при необходимости.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Параметры

*Выберите*<br/>
Указывает отсчитываемый от нуля индекс строки для выбора. Если *выберите* равно -1, поле со списком задан не выбрано.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

При выборе новой строки, поле со списком снимает выделение с ранее выбранной строки.

Используйте эту функцию-член только с единственным выбором списками.

Чтобы задать или удалить выделение в поле со списком с множественным выбором, используйте [CListBox::SetSel](#setsel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

##  <a name="sethorizontalextent"></a>  CListBox::SetHorizontalExtent

Задает ширину в пикселях, по которым поле со списком может прокручиваться по горизонтали.

```
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>Параметры

*cxExtent*<br/>
Задает количество пикселей, на которое поле со списком может прокручиваться по горизонтали.

### <a name="remarks"></a>Примечания

Если размер списка меньше, чем это значение, горизонтальной полосы прокрутки по горизонтали прокручивается элементов в поле со списком. Если же по объему или превышает это значение, поле со списком, горизонтальная полоса прокрутки будет скрыт.

Для ответа на вызов `SetHorizontalExtent`, поле со списком должно определено с [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) стиля.

Эта функция-член бесполезно для списков по нескольким столбцам. Списки по нескольким столбцам, вызовите `SetColumnWidth` функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

##  <a name="setitemdata"></a>  CListBox::SetItemData

Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента.

*dwItemData*<br/>
Задает значение, связанное с элементом.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

##  <a name="setitemdataptr"></a>  CListBox::SetItemDataPtr

Задает 32-разрядное значение, связанное с указанным элементом в поле со списком, чтобы быть заданный указатель ( **void** <strong>\*</strong>).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента.

*pData*<br/>
Указывает указатель, связываемых с элементом.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Этот указатель остается допустимым в течение жизненного цикла поле со списком, несмотря на то, что относительное положение элемента в поле со списком может измениться, как добавляются или удаляются элементы. Таким образом можно изменить индекс элемента в списке, но указатель остается надежной.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

##  <a name="setitemheight"></a>  CListBox::SetItemHeight

Задает высоту элементов в поле со списком.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента в поле со списком. Этот параметр используется только в том случае, если поле со списком имеет стиль LBS_OWNERDRAWVARIABLE; в противном случае он задается значение 0.

*cyItemHeight*<br/>
Указывает высоту в пикселях элемента.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если индекс или высота является недопустимым.

### <a name="remarks"></a>Примечания

Если поле со списком имеет [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, эта функция задает высоту элемента, заданного посредством *nIndex*. В противном случае эта функция задает высоту всех элементов в поле со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

##  <a name="setlocale"></a>  CListBox::SetLocale

Задает идентификатор языкового стандарта для этого списка.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Параметры

*nNewLocale*<br/>
Новое значение языкового стандарта идентификатор (LCID), чтобы задать для поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение языкового стандарта код (LCID) для этого списка.

### <a name="remarks"></a>Примечания

Если `SetLocale` не вызывается, значение по умолчанию языкового стандарта, полученная от системы. Этот язык системы по умолчанию можно изменить с помощью панели управления Язык и International.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

##  <a name="setsel"></a>  CListBox::SetSel

Выбирает строку в поле со списком с множественным выбором.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс строки, устанавливаемое значение. Если значение -1, выбор добавлении или удалении из всех строк, в зависимости от значения *bSelect*.

*bSelect*<br/>
Указывает, как выбрать в списке. Если *bSelect* имеет значение TRUE, выбран и выделенной строки; Если значение равно FALSE, выделение удаляется строка больше не выбран. Указанная строка выбран и выделенным по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только с полями список с множественным выбором.

Чтобы выбрать элемент из списка с поддержкой единственного выбора, используйте [CListBox::SetCurSel](#setcursel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

##  <a name="settabstops"></a>  CListBox::SetTabStops

Задает позиции табуляции в поле со списком.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);


BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Параметры

*cxEachStop*<br/>
Позиции табуляции устанавливаются на каждый *cxEachStop* диалоговых единицах. См. в разделе *rgTabStops* описание единица размера диалогового окна.

*nTabStops*<br/>
Указывает количество позиций табуляции для того, в поле со списком.

*rgTabStops*<br/>
Указывает первый элемент массива целых чисел, содержащий позиции табуляции в диалоговых единицах. Единица размера диалогового окна является горизонтальное или вертикальное расстояние. Единицы диалогового окна по горизонтали равным одной четвертой текущей единице измерения базового ширины диалогового окна, и единицы по вертикали диалоговое окно эквивалентен одну восьмую единиц базовый высоту текущего диалогового окна. Базовые единицы диалогового окна вычисляются в зависимости от высоты и ширины текущего системного шрифта. `GetDialogBaseUnits` Windows функция возвращает базовых единиц текущего диалогового окна в пикселях. Табуляции должны быть отсортированы по возрастанию; Обратная табуляция не допускаются.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если были заданы все знаки табуляции; в противном случае 0.

### <a name="remarks"></a>Примечания

Чтобы установить табуляции по умолчанию размер 2 единицы диалогового окна, вызова без параметров версии эта функция-член. Чтобы Установка позиций табуляции до размера, отличного от 2, вызовите версию с *cxEachStop* аргумент.

Чтобы установить табуляции в массив размеров, использовать версию с *rgTabStops* и *nTabStops* аргументы. Позиции табуляции устанавливается для каждого значения в *rgTabStops*, до числа, указанного *nTabStops*.

Для ответа на вызов `SetTabStops` функция-член, поле со списком должна быть создана с помощью [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

##  <a name="settopindex"></a>  CListBox::SetTopIndex

Гарантирует, что элемент определенного списка является видимым.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или LB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Система прокручивает поле со списком до элемента, заданного посредством *nIndex* отображается в верхней части списка поля или диапазона Максимальная прокрутка был достигнут.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

##  <a name="vkeytoitem"></a>  CListBox::VKeyToItem

Вызывается платформой, когда родительское окно списка получает сообщения WM_VKEYTOITEM из списка.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Параметры

*nKey*<br/>
Виртуального кода клавиши ключа нажатой клавише. Список стандартных коды виртуальных клавиш см. в разделе Winuser.h

*nIndex*<br/>
Текущая позиция курсора списков.

### <a name="return-value"></a>Возвращаемое значение

Возвращает - 2 для никаких дополнительных действий, - 1 для действия по умолчанию или неотрицательное число, указывающее индекс элемента списка для выполнения действия по умолчанию для клавиши.

### <a name="remarks"></a>Примечания

WM_VKEYTOITEM сообщение отправляется в списке, когда он получает сообщение WM_KEYDOWN, но только в том случае, если поле со списком соответствует оба следующих:

- Имеет [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) в стиле набора.

- Содержит по крайней мере один элемент.

Никогда не следует вызывать эту функцию самостоятельно. Переопределите эту функцию для предоставления собственных обычной обработки сообщений клавиатуры.

Должен возвращать значение, чтобы сообщить платформе, какое действие выполняется переопределение. Возвращаемое значение, равное - 2 указывает, что приложение обрабатывать все аспекты выбора элемента и не требует дальнейших действий в списке. Возврат до - 2, можно выбрать в списке или переместите курсор или оба. Чтобы выбрать в списке, используйте [SetCurSel](#setcursel) или [SetSel](#setsel). Чтобы переместить курсор, используйте [SetCaretIndex](#setcaretindex).

Возвращаемое значение, равное - 1 указывает, что поле со списком должно выполнять действие по умолчанию в ответ на нажатие клавиши. Реализация по умолчанию возвращается значение-1.

Возвращаемое значение 0 или больше указывает индекс элемента в поле со списком и указывает, что поле со списком должно выполнять действие по умолчанию для клавиши на данный элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC CTRLTEST](../../visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)
