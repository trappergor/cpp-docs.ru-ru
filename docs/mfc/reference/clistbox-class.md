---
title: Класс CListBox
description: Описание класса MFC CListBox и его функций участника.
ms.date: 01/22/2020
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
ms.openlocfilehash: 171038ebaaed815aa687c200fe3210bde8000be3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753589"
---
# <a name="clistbox-class"></a>Класс CListBox

Предоставляет функции списка Windows.

## <a name="syntax"></a>Синтаксис

```
class CListBox : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|Формирует объект `CListBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CListBox::AddString](#addstring)|Добавляет строку в поле списка.|
|[Клистбокс:Чартотемт](#chartoitem)|Переопределение, чтобы обеспечить пользовательские WM_CHAR обработки для владельца рисовать список ящиков, которые не имеют строк.|
|[CListBox::CompareItem](#compareitem)|Вызывается по фрейму, чтобы определить положение нового элемента в отсортированном поле списка владельца.draw.|
|[CListBox::Создание](#create)|Создает окно списка Windows и прикрепляет его к объекту. `CListBox`|
|[CListBox::DeleteItem](#deleteitem)|Вызывается по системе, когда пользователь удаляет элемент из окна списка владельца.|
|[CListBox::DeleteString](#deletestring)|Удаляет строку из ящика списка.|
|[CListBox::Dir](#dir)|Добавляет имена файлов, диски или оба из текущего каталога в поле списка.|
|[CListBox::DrawItem](#drawitem)|Вызывается по фреймворку при изменении визуального аспекта окна списка владельца-рисования.|
|[CListBox::FindString](#findstring)|Поиск строки в поле списка.|
|[CListBox::FindStringExact](#findstringexact)|Находит строку первого списка,сопозывававую указанную строку.|
|[CListBox::GetAnchorIndex](#getanchorindex)|Извлекает нулевой индекс текущего якоря в поле списка.|
|[CListBox::GetCaretIndex](#getcaretindex)|Определяет индекс элемента, который имеет прямоугольник фокусировки в поле списка с несколькими вариантами выбора.|
|[CListBox::GetCount](#getcount)|Возвращает количество строк в поле списка.|
|[CListBox::GetCurSel](#getcursel)|Возвращает нулевой индекс выбранной строки в поле списка.|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пиксели, которые поле списка можно прокручивать горизонтально.|
|[CListBox::GetItemData](#getitemdata)|Возвращает значение, связанное с элементом списка-коробки.|
|[CListBox::GetItemDataPtr](#getitemdataptr)|Возвращает указатель на элемент списка-коробки.|
|[CListBox::GetItemHeight](#getitemheight)|Определяет высоту элементов в поле списка.|
|[CListBox::GetItemRect](#getitemrect)|Возвращает прямоугольник элемента списка-коробки в том виде, в каком он отображается в настоящее время.|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Извлекает количество элементов в столбец.|
|[CListBox::GetLocale](#getlocale)|Извлекает идентификатор локализации для ящика списка.|
|[CListBox::GetSel](#getsel)|Возвращает состояние выбора элемента списка-коробки.|
|[CListBox::GetSelCount](#getselcount)|Возвращает количество строк, выбранных в настоящее время в поле списка с несколькими вариантами выбора.|
|[CListBox::GetSelitems](#getselitems)|Возвращает индексы строк, выбранных в настоящее время в поле списка.|
|[CListBox::GetText](#gettext)|Копирует элемент списка-коробки в буфер.|
|[CListBox::GetTextLen](#gettextlen)|Возвращает длину байтов элемента списка-коробки.|
|[CListBox::GetTopIndex](#gettopindex)|Возвращает индекс первой видимой строки в поле списка.|
|[CListBox::InitStorage](#initstorage)|Предраспределяет блоки памяти для элементов списка ящиков и строк.|
|[CListBox::InsertString](#insertstring)|Вставляет строку в определенном месте в поле списка.|
|[Clistbox::ItemFromPoint](#itemfrompoint)|Возвращает индекс пункта списка-коробки, ближайшего к точке.|
|[CListBox::MeasureItem](#measureitem)|Вызывается по системе, когда создается окно списка владельца-рисования для определения размеров списка.|
|[CListBox::ResetContent](#resetcontent)|Очищает все записи из списка поле.|
|[CListBox::SelectString](#selectstring)|Поиск и выбор строки в поле списка одного выбора.|
|[CListBox::SelItemRange](#selitemrange)|Выберите или отбрасывает диапазон строк в поле списка с несколькими вариантами выбора.|
|[CListBox::SetAnchorIndex](#setanchorindex)|Устанавливает якорь в поле списка с несколькими вариантами выбора, чтобы начать расширенный выбор.|
|[CListBox::SetCaretIndex](#setcaretindex)|Устанавливает прямоугольник фокусировки к элементу в указанном индексе в поле списка с несколькими вариантами выбора.|
|[CListBox::SetColumnШирин](#setcolumnwidth)|Устанавливает ширину столбца многоколонного окна списка.|
|[CListBox::SetCurSel](#setcursel)|Выбирает строку списка-коробки.|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Устанавливает ширину в пиксели, которые поле списка можно прокручивать горизонтально.|
|[CListBox::SetItemData](#setitemdata)|Устанавливает значение, связанное с элементом списка-коробки.|
|[CListBox::SetItemDataPtr](#setitemdataptr)|Устанавливает указатель на элемент списка-коробки.|
|[CListBox::SetItemHeight](#setitemheight)|Устанавливает высоту элементов в поле списка.|
|[CListBox::SetLocale](#setlocale)|Устанавливает идентификатор локализации для ящика списка.|
|[CListBox::SetSel](#setsel)|Выберите или отбрасвает элемент списка-коробки в поле списка с несколькими вариантами.|
|[CListBox::SetTabStops](#settabstops)|Устанавливает позиции tab-stop в поле списка.|
|[CListBox::SetTopIndex](#settopindex)|Устанавливает нулевой индекс первой видимой строки в поле списка.|
|[Клистбокс::VKeytoitem](#vkeytoitem)|Переопределение для обеспечения пользовательской обработки WM_KEYDOWN для списка ящиков с набором LBS_WANTKEYBOARDINPUT стилем.|

## <a name="remarks"></a>Remarks

В поле списка отображается список элементов, таких как имена файлов, которые пользователь может просматривать и выбирать.

В поле списка с одним выбором пользователь может выбрать только один элемент. В поле списка с несколькими вариантами выбора можно выбрать ряд элементов. Когда пользователь выбирает элемент, он выделяется, и поле списка отправляет сообщение уведомления в родительское окно.

Вы можете создать поле списка либо из шаблона диалога, либо непосредственно в коде. Чтобы создать его непосредственно, создайте `CListBox` объект, затем позвоните в функцию члена [Create,](#create) чтобы создать элемент управления списком Windows и прикрепить его к объекту. `CListBox` Чтобы использовать поле списка в шаблоне диалогов, объявить переменную списка в `DDX_Control` классе диалоговых коробок, а затем используйте функцию класса `DoDataExchange` диалогового окна для подключения переменной элемента к элементу управления. (Это делается для вас автоматически, когда вы добавляете переменную управления в класс диалогового окна.)

Строительство может быть одноступенчатый процесс в `CListBox`классе, полученных из . Напишите конструктор для производного класса и позвоните `Create` изнутри конструктора.

Если вы хотите обрабатывать сообщения уведомлений Windows, отправленные полем списка, его родителю (обычно классу, полученному из [CDialog),](../../mfc/reference/cdialog-class.md)добавьте запись на карту сообщений и функцию обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись на карту сообщений принимает следующую форму:

`ON_Notification( id, memberFxn )`

где `id` указывается идентификатор окна ребенка элементуправления `memberFxn` списка-коробки, отправляющий уведомление, и является именем функции родительского члена, написанной для обработки уведомления.

Прототип функции родителя:

`afx_msg void memberFxn( );`

Ниже приведен список потенциальных записей на карте сообщений и описание случаев, в которых они будут отправлены родителю:

- ON_LBN_DBLCLK Пользователь дважды щелкает строку в поле списка. Только поле списка, которое имеет [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, отправит это сообщение о уведомлении.

- ON_LBN_ERRSPACE поле списка не может выделить достаточно памяти для удовлетворения запроса.

- ON_LBN_KILLFOCUS Поле списка теряет вхотоза.

- ON_LBN_SELCANCEL Текущий выбор списка-коробки отменяется. Это сообщение отправляется только тогда, когда поле списка имеет LBS_NOTIFY стиль.

- ON_LBN_SELCHANGE Выбор в поле списка изменился. Это уведомление не отправляется, если выбор изменен функцией [cListBox::SetCurSel.](#setcursel) Это уведомление распространяется только на поле списка, которое имеет LBS_NOTIFY стиль. Сообщение LBN_SELCHANGE уведомления отправляется в поле списка с несколькими выборами всякий раз, когда пользователь нажимает клавишу стрелки, даже если выбор не изменяется.

- ON_LBN_SETFOCUS поле списка получает входиную фокус.

- ON_WM_CHARTOITEM поле списка владельца,нарисовавом, не имевавкоторое строки, получает WM_CHAR сообщение.

- ON_WM_VKEYTOITEM Поле списка со стилем LBS_WANTKEYBOARDINPUT получает WM_KEYDOWN сообщение.

При создании `CListBox` объекта в диалоговом поле (через ресурс `CListBox` диалога) объект автоматически уничтожается при закрытии диалогового окна.

Если вы `CListBox` создаете объект в окне, `CListBox` возможно, потребуется уничтожить объект. При создании `CListBox` объекта в стеке он уничтожается автоматически. Если объект `CListBox` создается на куче с помощью **новой** функции, необходимо **вызвать удаление** объекта, чтобы уничтожить его, когда пользователь закрывает родительское окно.

Если вы выделяете `CListBox` какую-либо `CListBox` память в объекте, переопределить деструктор, чтобы избавиться от выделения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="clistboxaddstring"></a><a name="addstring"></a>CListBox::AddString

Добавляет строку в поле списка.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*lpszItem*<br/>
Очки на нулевую строку, которая должна быть добавлена.

### <a name="return-value"></a>Возвращаемое значение

Индекс с нулевым уровнем в строке в поле списка. Значение возврата LB_ERR в случае ошибки; значение возврата LB_ERRSPACE при недостаточном пространстве для хранения новой строки.

### <a name="remarks"></a>Remarks

Если поле списка не было создано со [стилем LBS_SORT,](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) строка добавляется в конец списка. В противном случае строка вставляется в список, и список сортируется. Если поле списка было создано с LBS_SORT стилем, но не [с LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем, фреймворк сортирует список одним или несколько вызовами в функцию `CompareItem` участника.

Используйте [InsertString](#insertstring) для вставки строки в определенное место в поле списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

## <a name="clistboxchartoitem"></a><a name="chartoitem"></a>Клистбокс:Чартотемт

Вызывается по системе, когда родительское окно списка получает WM_CHARTOITEM сообщение из окна списка.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Параметры

*nKey*<br/>
Код ANSI символа, набранного пользователем.

*Nindex*<br/>
Текущее положение списка-коробка caret.

### <a name="return-value"></a>Возвращаемое значение

Возвраты - 1 или - 2 без каких-либо дальнейших действий или ненегативного числа, чтобы указать индекс элемента списка-коробки, на котором для выполнения действия по умолчанию для нажатия клавиши. Возвращает реализацию по умолчанию - 1.

### <a name="remarks"></a>Remarks

Сообщение WM_CHARTOITEM отправляется полем списка, когда оно получает WM_CHAR сообщение, но только в том случае, если поле списка отвечает всем этим критериям:

- Является полем списка владельца-рисования.

- Не имеет [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) набора стилей.

- Имеет по крайней мере один элемент.

Вы никогда не должны называть эту функцию самостоятельно. Переизобить эту функцию, чтобы обеспечить вашу собственную пользовательскую обработку сообщений клавиатуры.

В переопределением вы должны вернуть значение, чтобы определить, какие действия вы выполнили. Значение возврата - 1 или - 2 указывает на то, что вы обрабатываются все аспекты выбора элемента и не требует дальнейших действий в поле списка. Перед возвращением - 1 или - 2, вы можете установить выбор или переместить caret или оба. Чтобы установить выделение, используйте [SetCurSel](#setcursel) или [SetSel.](#setsel) Для перемещения caret используйте [SetCaretIndex](#setcaretindex).

Значение возврата 0 или больше определяет индекс элемента в поле списка и указывает, что поле списка должно выполнять действие по умолчанию для нажатия клавиши на данном элементе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

## <a name="clistboxclistbox"></a><a name="clistbox"></a>CListBox::CListBox

Формирует объект `CListBox`.

```
CListBox();
```

### <a name="remarks"></a>Remarks

Вы строите `CListBox` объект в два этапа. Во-первых, вызов `ClistBox` конструктора, а затем вызов `Create`, который инициализирует окно списка Windows и прикрепляет его к . `CListBox`

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

## <a name="clistboxcompareitem"></a><a name="compareitem"></a>CListBox::CompareItem

Вызывается по системе, чтобы определить относительное положение нового элемента в отсортированном поле списка владельца-рисования.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Параметры

*lpCompareItemStruct*<br/>
Длинный указатель на `COMPAREITEMSTRUCT` структуру.

### <a name="return-value"></a>Возвращаемое значение

Указывает относительное положение двух элементов, описанных в структуре [COMPAREITEMSTRUCT.](/windows/win32/api/winuser/ns-winuser-compareitemstruct) Это может быть любое из следующих значений:

|Значение|Значение|
|-----------|-------------|
|-1|Пункт 1 имеет до пункта 2.|
|0|Пункт 1 и пункт 2 сортируют то же самое.|
|1|Пункт 1 разнослив после пункта 2.|

Смотрите [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) для описания `COMPAREITEMSTRUCT` структуры.

### <a name="remarks"></a>Remarks

По умолчанию эта функция-член ничего не делает. При создании окна списка владельцев с LBS_SORT стилем необходимо переопределить эту функцию участника, чтобы помочь системе сортировки новых элементов, добавленных в поле списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

## <a name="clistboxcreate"></a><a name="create"></a>CListBox::Создание

Создает окно списка Windows и прикрепляет его к объекту. `CListBox`

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль коробки списка. Примените любую комбинацию [стилей списка-коробки](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) к коробке.

*rect*<br/>
Определяет размер и положение списка-коробки. Может быть `CRect` как объект, так `RECT` и структура.

*pParentWnd*<br/>
Уфиксирует родительское окно окна списка `CDialog` (обычно объект). Она не должна быть NULL.

*nID*<br/>
Угоняет идентификатор управления полем списка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы строите `CListBox` объект в два этапа. Сначала позвоните в конструктор, `Create`а затем вызов , который инициализирует окно списка Windows и прикрепляет его к объекту. `CListBox`

При `Create` выполнении Windows отправляет [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_CREATE,](../../mfc/reference/cwnd-class.md#oncreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения в элемент управления список.

Эти сообщения обрабатываются по умолчанию функциями участников [OnNcCreate,](../../mfc/reference/cwnd-class.md#onnccreate) [OnCreate,](../../mfc/reference/cwnd-class.md#oncreate) [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize) `CWnd` и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) в базовом классе. Чтобы расширить обработку сообщений по `CListBox`умолчанию, вывемите класс из, добавьте карту сообщений в новый класс и переизуйте предыдущие функции обработчика сообщений. Переопределить, `OnCreate`например, для выполнения необходимой инициализации для нового класса.

Примените следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к управлению списком.ру.

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

- WS_VSCROLL Для добавления вертикальной панели прокрутки

- WS_HSCROLL Для добавления горизонтальной панели прокрутки

- WS_GROUP К управлению группой

- WS_TABSTOP Чтобы позволить табумирование к этому управлению

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

## <a name="clistboxdeleteitem"></a><a name="deleteitem"></a>CListBox::DeleteItem

Вызывается в рамках, когда пользователь удаляет элемент `CListBox` из объекта владельца рисовать или разрушает окно списка.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDeleteItemStruct*<br/>
Длинный указатель на структуру Windows [DELETEITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) содержащую информацию об удаленном элементе.

### <a name="remarks"></a>Remarks

Реализация по умолчанию этой функции не выполняет никаких действий. Переизбь эту функцию, чтобы перерисовать окно списка владельца по мере необходимости.

Смотрите [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) для описания `DELETEITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

## <a name="clistboxdeletestring"></a><a name="deletestring"></a>CListBox::DeleteString

Удаляет элемент в позиции *nIndex* из окна списка.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Уотек удаляемого индекса строки на нулевой основе.

### <a name="return-value"></a>Возвращаемое значение

Количество строк, оставшихся в списке. Значение возврата LB_ERR если *nIndex* определяет индекс, превышающее количество элементов в списке.

### <a name="remarks"></a>Remarks

Все элементы, следующие *за nIndex* теперь двигаться вниз по одной позиции. Например, если поле списка содержит два элемента, удаляние первого элемента приведет к тому, что оставшийся элемент будет теперь находиться в первой позиции. *nIndex*No0 для элемента в первой позиции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

## <a name="clistboxdir"></a><a name="dir"></a>CListBox::Dir

Добавляет список имен файлов, дисков или обоих в поле списка.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Параметры

*Attr*<br/>
Может быть любое сочетание **значений,** описанных в `CFile::GetStatu` [s,](../../mfc/reference/cfile-class.md#getstatus)или любое сочетание следующих значений:

|Значение|Значение|
|-----------|-------------|
|0x0000|Файл можно прочитать или написать.|
|0x0001|Файл можно читать, но не писать.|
|0x0002|Файл скрыт и не отображается в объявлении каталога.|
|0x0004|Файл — это системный файл.|
|0x0010|Название, указанное *lpszWildCard,* указывает каталог.|
|0x0020|Файл был заархивирован.|
|0x4000|Включите все диски, которые соответствуют имени, указанному *lpszWildCard.*|
|0x8000|Эксклюзивный флаг. Если установлен эксклюзивный флаг, перечислены только файлы указанного типа. В противном случае файлы указанного типа перечислены в дополнение к "нормальным" файлам.|

*lpszWildCard*<br/>
Указывает на строку спецификации файлов. Строка может содержать подстановочные\*знаки (например, З. ).

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс последнего имени файла добавлен в список. Значение возврата LB_ERR в случае ошибки; значение возврата LB_ERRSPACE при недостаточном пространстве для хранения новых строк.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

## <a name="clistboxdrawitem"></a><a name="drawitem"></a>CListBox::DrawItem

Вызывается по фреймворку при изменении визуального аспекта окна списка владельца-рисования.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Длинный указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) содержащую информацию о типе требуемого чертежа.

### <a name="remarks"></a>Remarks

`itemState` Члены `itemAction` `DRAWITEMSTRUCT` структуры определяют действие чертежа, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию элемента для `CListBox` реализации чертежа для объекта владельца-рисования. Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста дисплея, поставляемые в *lpDrawItemStruct,* прежде чем эта функция участника прекратится.

Смотрите [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) для описания `DRAWITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

## <a name="clistboxfindstring"></a><a name="findstring"></a>CListBox::FindString

Находит первую строку в поле списка, содержащем указанную префикс, не изменяя выбор списка-коробки.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит нулевой индекс элемента перед поиском первого элемента. Когда поиск достигает нижней части окна списка, он продолжается от верхней части окна списка обратно к элементу, указанному *nStartAfter.* Если *nStartAfter* -1, весь список поле ищется с самого начала.

*lpszItem*<br/>
Указывает на нулевую строку, содержащую префикс для поиска. Поиск независит от случая, поэтому эта строка может содержать любую комбинацию верхних и нижних букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе элемента сопоставления или LB_ERR, если поиск был неудачным.

### <a name="remarks"></a>Remarks

Используйте функцию члена [SelectString,](#selectstring) чтобы найти и выбрать строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

## <a name="clistboxfindstringexact"></a><a name="findstringexact"></a>CListBox::FindStringExact

Находит строку первого списка,которая соответствует строке, указанной в *lpszFind.*

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Параметры

*nИндексСтарт*<br/>
Уотек индекса элемента с нулевым уровнем до первого элемента, который будет искаться. Когда поиск достигает нижней части окна списка, он продолжается от верхней части окна списка обратно к элементу, указанному *nIndexStart.* Если *nIndexStart* -1, весь список поле ищется с самого начала.

*lpszFind*<br/>
Указывает на нулевую строку для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не является чувствительным к делу, поэтому строка может содержать любую комбинацию верхних и нижних букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента сопоставления или LB_ERR, если поиск был неудачным.

### <a name="remarks"></a>Remarks

Если поле списка было создано со стилем владельца,рисования, но без [стиля LBS_HASSTRINGS,](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) функция `FindStringExact` участника пытается сопоставить значение двойного слова со значением *lpszFind.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

## <a name="clistboxgetanchorindex"></a><a name="getanchorindex"></a>CListBox::GetAnchorIndex

Извлекает нулевой индекс текущего элемента якоря в поле списка.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс текущего якорного элемента, в случае успеха; в противном случае LB_ERR.

### <a name="remarks"></a>Remarks

В поле списка с несколькими вариантами выбора якорь является первым или последним элементом в блоке смежных выбранных элементов.

### <a name="example"></a>Пример

  Смотрите пример [CListBox::SetAnchorIndex](#setanchorindex).

## <a name="clistboxgetcaretindex"></a><a name="getcaretindex"></a>CListBox::GetCaretIndex

Определяет индекс элемента, который имеет прямоугольник фокусировки в поле списка с несколькими вариантами выбора.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента с нулевым уровнем, который имеет прямоугольник фокусировки в поле списка. Если поле списка является полем списка с одним выбором, значение возврата — это индекс выбранного элемента, если таковой имеется.

### <a name="remarks"></a>Remarks

Элемент может быть выбран или не может быть выбран.

### <a name="example"></a>Пример

  Смотрите пример [CListBox::SetCaretIndex](#setcaretindex).

## <a name="clistboxgetcount"></a><a name="getcount"></a>CListBox::GetCount

Извлекает количество элементов в поле списка.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в поле списка или LB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Обратный отсчет на один больше значения индекса последнего элемента (индекс основан на нулевом уровне).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

## <a name="clistboxgetcursel"></a><a name="getcursel"></a>CListBox::GetCurSel

Извлекает нулевой индекс выбранного в настоящее время элемента, если таковой имеется, в поле списка с одним выбором.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе выбранного в настоящее время элемента, если он представляет собой поле списка с одним выбором. Это LB_ERR если в настоящее время нет элемента выбран.

В поле списка с несколькими вариантами выбора индекс элемента, который имеет фокус.

### <a name="remarks"></a>Remarks

Не вызывайте поле списка с несколькими вариантами `GetCurSel` выбора. Используйте [CListBox::GetSelitems](#getselitems) вместо.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

## <a name="clistboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CListBox::GetHorizontalExtent

Извлекает из списка окно ширины в пикселей, с помощью которых он может быть прокрутили горизонтально.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прокрутка ширина окна списка, в пикселях.

### <a name="remarks"></a>Remarks

Это применимо только в том случае, если поле списка имеет горизонтальную панель прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

## <a name="clistboxgetitemdata"></a><a name="getitemdata"></a>CListBox::GetItemData

Извлекает значение двойного слова, поставляемое приложением, связанное с указанным элементом списка-коробки.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с элементом, или LB_ERR, если произошла ошибка.

### <a name="remarks"></a>Remarks

Значение двойного слова было параметром *dwItemData* вызова [SetItemData.](#setitemdata)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

## <a name="clistboxgetitemdataptr"></a><a name="getitemdataptr"></a>CListBox::GetItemDataPtr

Извлекает предоставленное приложение 32-битное значение, связанное с указанным пунктом списка-коробки в качестве указателя **(недействительным).** <strong>\*</strong>

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента в поле списка.

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель, или -1, если происходит ошибка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

## <a name="clistboxgetitemheight"></a><a name="getitemheight"></a>CListBox::GetItemHeight

Определяет высоту элементов в поле списка.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента в поле списка. Этот параметр используется только в том случае, если поле списка имеет LBS_OWNERDRAWVARIABLE стиль; в противном случае, она должна быть установлена до 0.

### <a name="return-value"></a>Возвращаемое значение

Высота, в пикселях, элементов в поле списка. Если поле списка имеет [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, значение возврата — это высота элемента, указанного *nIndex.* При возникновении ошибки значение возврата LB_ERR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

## <a name="clistboxgetitemrect"></a><a name="getitemrect"></a>CListBox::GetItemRect

Извлекает размеры прямоугольника, который граничит с элементом списка-коробки, как он в настоящее время отображается в окне списка коробки.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента.

*lpRect*<br/>
Определяет длинный указатель на [структуру RECT,](/windows/win32/api/windef/ns-windef-rect) которая получает координаты клиента по списку.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если происходит ошибка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

## <a name="clistboxgetlistboxinfo"></a><a name="getlistboxinfo"></a>CListBox::GetListBoxInfo

Извлекает количество элементов в столбец.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов на `CListBox` столбец объекта.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность [сообщения LB_GETLISTBOXINFO,](/windows/win32/Controls/lb-getlistboxinfo) как описано в SDK Windows.

## <a name="clistboxgetlocale"></a><a name="getlocale"></a>CListBox::GetLocale

Извлекает локал, используемый в поле списка.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение идентификатора локализации (LCID) для строк в поле списка.

### <a name="remarks"></a>Remarks

Например, для определения порядка сортировки строк в отсортированном поле списка используется ложа местности.

### <a name="example"></a>Пример

  Смотрите пример [CListBox::SetLocale](#setlocale).

## <a name="clistboxgetsel"></a><a name="getsel"></a>CListBox::GetSel

Извлекает состояние выбора элемента.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Положительное число при выборе указанного элемента; в противном случае, это 0. Значение возврата LB_ERR если произошла ошибка.

### <a name="remarks"></a>Remarks

Эта функция члена работает как с одно-, так и с несколькими вариантами ставок.

Для получения индекса выбранного в настоящее время элемента коробки списка используйте [CListBox::GetCurSel](#getcursel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

## <a name="clistboxgetselcount"></a><a name="getselcount"></a>CListBox::GetSelCount

Извлекает общее количество выбранных элементов в поле списка с несколькими вариантами выбора.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Подсчет выбранных элементов в поле списка. Если поле списка является полем списка с одним выбором, значение возврата LB_ERR.

### <a name="example"></a>Пример

  Смотрите пример [CListBox::GetSelItems](#getselitems).

## <a name="clistboxgetselitems"></a><a name="getselitems"></a>CListBox::GetSelitems

Заполняет буфер массивом целых чисел, которые определяют номера элементов выбранных элементов в поле списка с несколькими вариантами выбора.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>Параметры

*nMaxItems*<br/>
Определяет максимальное количество выбранных элементов, номера элементов которых должны быть помещены в буфер.

*rgIndex*<br/>
Определяет указатель на буфер, достаточно большой для количества целых чипов, указанных *nMaxItems.*

### <a name="return-value"></a>Возвращаемое значение

Фактическое количество элементов, помещенных в буфер. Если поле списка является полем списка с одним `LB_ERR`выбором, значение возврата находится в поле .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

## <a name="clistboxgettext"></a><a name="gettext"></a>CListBox::GetText

Получает строку из ящика списка.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Уотек нулевого индекса строки для извлечения.

*lpszBuffer*<br/>
Указывает на буфер, который получает строку. Буфер должен иметь достаточно места для строки и прекращающийся нулевой символ. Размер строки можно определить заранее, позвонив в функцию `GetTextLen` участника.

*rString*<br/>
Ссылка на объект `CString`.

### <a name="return-value"></a>Возвращаемое значение

Длина (в байтах) строки, исключающая прекращающийся нулевой характер. Если *nIndex* не указывает действительный индекс, значение возврата LB_ERR.

### <a name="remarks"></a>Remarks

Вторая форма этой функции `CString` члена заполняет объект текстом строки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

## <a name="clistboxgettextlen"></a><a name="gettextlen"></a>CListBox::GetTextLen

Получает длину строки в элементе списка-коробки.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет индекс строки с нулевым уровнем.

### <a name="return-value"></a>Возвращаемое значение

Длина строки в символах, исключая терминnull. Если *nIndex* не указывает действительный индекс, значение возврата LB_ERR.

### <a name="example"></a>Пример

  Смотрите пример [CListBox::GetText](#gettext).

## <a name="clistboxgettopindex"></a><a name="gettopindex"></a>CListBox::GetTopIndex

Извлекает нулевой индекс первого видимого элемента в поле списка.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс первого видимого элемента в поле списка в случае успеха LB_ERR иным образом.

### <a name="remarks"></a>Remarks

Первоначально пункт 0 находится в верхней части окна списка, но если поле списка прокрутится, другой элемент может быть в верхней части.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

## <a name="clistboxinitstorage"></a><a name="initstorage"></a>CListBox::InitStorage

Выделяет память для хранения элементов списка-коробки.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Параметры

*nItems*<br/>
Определяет количество добавленных элементов.

*nБайт*<br/>
Определяет объем памяти в байтах для выделения строк элемента.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха необходимо максимальное количество элементов, которые поле списка может хранить до перераспределения памяти, в противном случае LB_ERRSPACE, что означает, что памяти недостаточно.

### <a name="remarks"></a>Remarks

Вызов ими, прежде чем добавлять `CListBox`большое количество элементов в .

Эта функция помогает ускорить инициализацию списков ящиков, которые имеют большое количество элементов (более 100). Он предраспределяет указанное количество памяти так, чтобы последующие функции [AddString,](#addstring) [InsertString](#insertstring)и [Dir](#dir) отнимут как можно меньше времени. Оценки для параметров можно использовать. Если вы переоцените, выделяется дополнительная память; если вы недооцениваете, обычное распределение используется для элементов, превышающей заранее выделенную сумму.

Только Windows 95/98: параметр *nItems* ограничен 16-битовыми значениями. Это означает, что в списках не может содержаться более 32 767 элементов. Хотя количество элементов ограничено, общий размер элементов в поле списка ограничен только доступной памятью.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

## <a name="clistboxinsertstring"></a><a name="insertstring"></a>CListBox::InsertString

Вставляет строку в поле списка.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет нулевой индекс положения для вставки строки. Если этот параметр -1, строка добавляется к концу списка.

*lpszItem*<br/>
Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. Значение возврата LB_ERR в случае ошибки; значение возврата LB_ERRSPACE при недостаточном пространстве для хранения новой строки.

### <a name="remarks"></a>Remarks

В отличие от функции члена [AddString,](#addstring) `InsertString` не вызывает список с [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем для сортировки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

## <a name="clistboxitemfrompoint"></a><a name="itemfrompoint"></a>Clistbox::ItemFromPoint

Определяет пункт списка-коробки ближайший пункт, указанный в *pt*.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Точка для чего можно найти ближайший товар, указанный относительно верхнего левого угла клиентской области ящика списка.

*bOutside*<br/>
Ссылка на переменную BOOL, которая будет установлена на TRUE, если *PT* находится за пределами клиентской области списка поле, FALSE, если *PT* находится внутри клиентской области списка поле.

### <a name="return-value"></a>Возвращаемое значение

Индекс ближайшего товара к точке, указанной в *pt*.

### <a name="remarks"></a>Remarks

Эту функцию можно использовать для определения того, какой элемент списка-коробки перемещает курсор мыши.

### <a name="example"></a>Пример

  Смотрите пример [CListBox::SetAnchorIndex](#setanchorindex).

## <a name="clistboxmeasureitem"></a><a name="measureitem"></a>CListBox::MeasureItem

Вызывается по фреймворку при создании окна списка со стилем владельца-рисования.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpИзмеренныйПункт*<br/>
Длинный указатель на структуру [MEASUREITEMSTRUCT.](/windows/win32/api/winuser/ns-winuser-measureitemstruct)

### <a name="remarks"></a>Remarks

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию члена `MEASUREITEMSTRUCT` и заполнить структуру, чтобы сообщить Windows о списка холостых размеров. Если поле списка создано с [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем, фреймворк вызывает эту функцию элемента для каждого элемента в поле списка. В противном случае этот участник называется только один раз.

Для получения дополнительной информации об использовании [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля `SubclassDlgItem` в поле `CWnd`списка владельца,рисуевого, созданного с функцией участника, см. [Technical Note 14](../../mfc/tn014-custom-controls.md)

Смотрите [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) для описания `MEASUREITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

## <a name="clistboxresetcontent"></a><a name="resetcontent"></a>CListBox::ResetContent

Удаляет все элементы из ящика списка.

```cpp
void ResetContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

## <a name="clistboxselectstring"></a><a name="selectstring"></a>CListBox::SelectString

Поиск элемента списка-коробки, который соответствует указанной строке, и если найден соответствующий элемент, он выбирает элемент.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит нулевой индекс элемента перед поиском первого элемента. Когда поиск достигает нижней части окна списка, он продолжается от верхней части окна списка обратно к элементу, указанному *nStartAfter.* Если *nStartAfter* -1, весь список поле ищется с самого начала.

*lpszItem*<br/>
Указывает на нулевую строку, содержащую префикс для поиска. Поиск независит от случая, поэтому эта строка может содержать любую комбинацию верхних и нижних букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс выбранного элемента, если поиск был успешным. Если поиск был неудачным, значение возврата LB_ERR, а текущий выбор не изменяется.

### <a name="remarks"></a>Remarks

Поле списка прокручивается, если это необходимо, чтобы привести выбранный элемент в поле зрения.

Эта функция участника не может быть использована с полем списка, который имеет [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль.

Элемент выбирается только в том случае, если его начальные символы (с отправной точки) соответствуют символам строки, указанной *lpszItem.*

Используйте `FindString` функцию участника, чтобы найти строку, не выбирая элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

## <a name="clistboxselitemrange"></a><a name="selitemrange"></a>CListBox::SelItemRange

Выбирает несколько последовательных элементов в поле списка с несколькими вариантами выбора.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>Параметры

*bВыбрать*<br/>
Определяет, как настроить выбор. Если *bSelect* является правдой, строка выбрана и выделена; если FALSE, изюминка удаляется и строка больше не выбрана.

*nFirstItem*<br/>
Установить нулевой индекс первого элемента для установки.

*nLastItem*<br/>
Установить нулевой индекс последнего элемента для установки.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Используйте эту функцию участника только с несколькими ящиками списка выбора. Если вам нужно выбрать только один элемент в поле списка с несколькими выборами, то есть, если *nFirstItem* равен *nLastItem* – вместо этого позвоните в функцию участника [SetSel.](#setsel)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

## <a name="clistboxsetanchorindex"></a><a name="setanchorindex"></a>CListBox::SetAnchorIndex

Устанавливает якорь в поле списка с несколькими вариантами выбора, чтобы начать расширенный выбор.

```cpp
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет нулевой индекс элемента списка-коробки, который будет якорем.

### <a name="remarks"></a>Remarks

В поле списка с несколькими вариантами выбора якорь является первым или последним элементом в блоке смежных выбранных элементов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

## <a name="clistboxsetcaretindex"></a><a name="setcaretindex"></a>CListBox::SetCaretIndex

Устанавливает прямоугольник фокусировки к элементу в указанном индексе в поле списка с несколькими вариантами выбора.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет нулевой индекс элемента для получения прямоугольника фокусировки в поле списка.

*bScroll*<br/>
Если это значение равня 0, элемент прокручивается до полного просна. Если это значение не 0, элемент прокручивается до тех пор, пока он не будет хотя бы частично виден.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Если элемент не виден, он прокручивается в поле зрения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

## <a name="clistboxsetcolumnwidth"></a><a name="setcolumnwidth"></a>CListBox::SetColumnШирин

Устанавливает ширину в пикселях всех столбцов в многоколонном поле списка (создано с [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем).

```cpp
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>Параметры

*cxВимизм*<br/>
Определяет ширину пикселей всех столбцов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

## <a name="clistboxsetcursel"></a><a name="setcursel"></a>CListBox::SetCurSel

Выберите строку и при необходимости прокрутите ее в поле зрения.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Параметры

*Nвыберите*<br/>
Определяет нулевой индекс строки, который будет выбран. Если *nSelect* является -1, поле списка не имеет выбора.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

При выборе новой строки поле списка удаляет выделение из ранее выбранной строки.

Используйте эту функцию участника только с одноразовыми ящиками списка.

Чтобы установить или удалить выделение в поле списка с несколькими выборами, используйте [CListBox::SetSel](#setsel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

## <a name="clistboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CListBox::SetHorizontalExtent

Устанавливает ширину в пиксели, с помощью которых поле списка может быть прокрутено горизонтально.

```cpp
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>Параметры

*cxExtent*<br/>
Определяет количество пикселей, с помощью которых поле списка может быть прокрутено горизонтально.

### <a name="remarks"></a>Remarks

Если размер окна списка меньше этого значения, горизонтальная панель прокрутки будет горизонтально прокручивать элементы в поле списка. Если поле списка размером с несколько размеров или больше этого значения скрыто.

Чтобы ответить на `SetHorizontalExtent`вызов, поле списка должно быть определено со [стилем WS_HSCROLL.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

Эта функция участника не полезна для многоколонных ящиков списка. Для многоколонных ящиков списка позвоните функции `SetColumnWidth` участника.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

## <a name="clistboxsetitemdata"></a><a name="setitemdata"></a>CListBox::SetItemData

Устанавливает значение, связанное с указанным элементом, в поле списка.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента.

*dwItemData*<br/>
Опознавательный значение, связанное с элементом.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если происходит ошибка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

## <a name="clistboxsetitemdataptr"></a><a name="setitemdataptr"></a>CListBox::SetItemDataPtr

Устанавливает 32-битное значение, связанное с указанным элементом, в поле списка, чтобы быть указанным указателем **(недействительным).** <strong>\*</strong>

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента.

*Pdata*<br/>
Определяет указатель, связанный с элементом.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Этот указатель остается действительным в течение всего срока службы вполе списка, даже если относительное положение элемента в поле списка может измениться по мере добавления или удаления элементов. Таким образом, индекс элемента в поле может измениться, но указатель остается надежным.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

## <a name="clistboxsetitemheight"></a><a name="setitemheight"></a>CListBox::SetItemHeight

Устанавливает высоту элементов в поле списка.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Упогоняет нулевой индекс элемента в поле списка. Этот параметр используется только в том случае, если поле списка имеет LBS_OWNERDRAWVARIABLE стиль; в противном случае, она должна быть установлена до 0.

*cyItemHeight*<br/>
Определяет высоту элемента в пикселях.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если индекс или высота недействительны.

### <a name="remarks"></a>Remarks

Если поле списка имеет [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль, эта функция устанавливает высоту элемента, указанного *nIndex.* В противном случае эта функция устанавливает высоту всех элементов в поле списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

## <a name="clistboxsetlocale"></a><a name="setlocale"></a>CListBox::SetLocale

Устанавливает идентификатор локализации для этого окна списка.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Параметры

*nNewLocale*<br/>
Новое значение идентификатора локального (LCID) для настройки для окна списка.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение идентификатора локального (LCID) для этого окна списка.

### <a name="remarks"></a>Remarks

Если `SetLocale` не вызывается, локализуется из системы. Этот язык по умолчанию системы может быть изменен с помощью регионального (или международного) приложения панели управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

## <a name="clistboxsetsel"></a><a name="setsel"></a>CListBox::SetSel

Выберите строку в поле списка с несколькими вариантами выбора.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит нулевой индекс строки, который будет установлен. Если -1, выбор добавляется или удаляется из всех строк, в зависимости от значения *bSelect.*

*bВыбрать*<br/>
Определяет, как настроить выбор. Если *bSelect* является правдой, строка выбрана и выделена; если FALSE, изюминка удаляется и строка больше не выбрана. Указанная строка выбрана и выделена по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

LB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Используйте эту функцию участника только с несколькими ящиками списка выбора.

Чтобы выбрать элемент из окна списка с одним выбором, используйте [CListBox::SetCurSel](#setcursel).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

## <a name="clistboxsettabstops"></a><a name="settabstops"></a>CListBox::SetTabStops

Устанавливает позиции tab-stop в поле списка.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Параметры

*cxEachStop*<br/>
Остановки вкладок устанавливаются на каждом диалоговом блоке *cxEachStop.* *Ознакомьтесь с rgTabStops* для описания диалогового блока.

*nTabStops*<br/>
Определяет количество остановок вкладок, чтобы иметь в поле списка.

*rgTabStops*<br/>
Указывает на первого члена массива целых числа, содержащих позиции tab-stop в единицах диалогов. Единица диалога представляет собой горизонтальное или вертикальное расстояние. Один горизонтальный блок диалога равен одной четверти текущего блока ширины базы диалога, а один вертикальный блок диалога равен одной восьмой текущей единицы базовой высоты диалога. Базовые единицы диалогов вычисляются на основе высоты и ширины шрифта текущей системы. Функция `GetDialogBaseUnits` Windows возвращает текущие базовые единицы диалогов в пиксели. Остановки вкладок должны быть отсортированы в порядке увеличения; задние вкладки не допускаются.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если все вкладки были установлены; в противном случае 0.

### <a name="remarks"></a>Remarks

Чтобы установить стопы вкладок до размера по умолчанию 2 единиц диалогов, вызовите безпаралистную версию этой функции-члена. Чтобы установить вкладку останавливается до размера, кроме 2, позвоните в версию с аргументом *cxEachStop.*

Чтобы установить стопы вкладок на массив размеров, используйте версию с аргументами *rgTabStops* и *nTabStops.* Остановка вкладок будет установлена для каждого значения в *rgTabStops,* до числа, указанного *nTabStops.*

Чтобы ответить на `SetTabStops` вызов функции участника, поле списка должно быть создано со [стилем LBS_USETABSTOPS.](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

## <a name="clistboxsettopindex"></a><a name="settopindex"></a>CListBox::SetTopIndex

Гарантирует, что будет виден определенный элемент списка-коробки.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет нулевой индекс элемента списка-коробки.

### <a name="return-value"></a>Возвращаемое значение

Ноль в случае успеха или LB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Система прокручивает поле списка до тех пор, пока ни элемент, указанный *nIndex,* не появится в верхней части окна списка, ни максимальный диапазон прокрутки не будет достигнут.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

## <a name="clistboxvkeytoitem"></a><a name="vkeytoitem"></a>Клистбокс::VKeytoitem

Вызывается по системе, когда родительское окно списка получает WM_VKEYTOITEM сообщение из окна списка.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Параметры

*nKey*<br/>
Виртуальный код ключа, на который нажал пользователь. Список стандартных виртуальных кодов ключей можно узнать на примере Winuser.h

*Nindex*<br/>
Текущее положение списка-коробка caret.

### <a name="return-value"></a>Возвращаемое значение

Возвраты - 2 без каких-либо дальнейших действий, - 1 для действия по умолчанию, или неотрицательное число для указания индекса элемента коробки списка, на котором для выполнения действия по умолчанию для нажатия клавиши.

### <a name="remarks"></a>Remarks

Сообщение WM_VKEYTOITEM отправляется полем списка, когда оно получает WM_KEYDOWN сообщение, но только в том случае, если поле списка соответствует обоим следующим:

- Имеет [набор LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилей.

- Имеет по крайней мере один элемент.

Вы никогда не должны называть эту функцию самостоятельно. Переизобить эту функцию, чтобы обеспечить вашу собственную пользовательскую обработку сообщений клавиатуры.

Необходимо вернуть значение, чтобы сообщить рамоче, какие действия выполняется ввашем переопределение. Значение возврата - 2 указывает на то, что приложение обработало все аспекты выбора элемента и не требует дальнейших действий со стороны списка. Перед возвращением - 2, вы можете установить выбор или переместить caret или оба. Чтобы установить выделение, используйте [SetCurSel](#setcursel) или [SetSel.](#setsel) Для перемещения caret используйте [SetCaretIndex](#setcaretindex).

Значение возврата - 1 указывает на то, что поле списка должно выполнять действие по умолчанию в ответ на нажатие клавиши. Возвращает реализацию по умолчанию - 1.

Значение возврата 0 или больше определяет индекс элемента в поле списка и указывает, что поле списка должно выполнять действие по умолчанию для нажатия клавиши на данном элементе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)
