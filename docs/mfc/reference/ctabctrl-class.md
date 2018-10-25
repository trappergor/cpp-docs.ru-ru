---
title: Класс CTabCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cfbcdf03a5c527d27d9bff8b37322011cba60bb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063514"
---
# <a name="ctabctrl-class"></a>Класс CTabCtrl

Предоставляет функциональные возможности стандартного элемента управления "вкладка" Windows.

## <a name="syntax"></a>Синтаксис

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTabCtrl::CTabCtrl](#ctabctrl)|Создает объект `CTabCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTabCtrl::AdjustRect](#adjustrect)|Вычисляет область отображения элемента управления вкладки, указанным прямоугольником окна или вычисляет окно прямоугольник, который будет соответствовать область заданного отображения.|
|[CTabCtrl::Create](#create)|Создает набор вкладок и присоединяет его к экземпляру `CTabCtrl` объекта.|
|[CTabCtrl::CreateEx](#createex)|Создает элемент управления вкладки с указанным расширенные стили Windows и присоединяет его к экземпляру `CTabCtrl` объекта.|
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Удаляет все элементы из набора вкладок.|
|[CTabCtrl::DeleteItem](#deleteitem)|Удаляет элемент из набора вкладок.|
|[CTabCtrl::DeselectAll](#deselectall)|Сбрасывает элементы в набор вкладок, очистка, были нажаты.|
|[CTabCtrl::DrawItem](#drawitem)|Рисует указанный объект элемента управления вкладки.|
|[CTabCtrl::GetCurFocus](#getcurfocus)|Извлекает вкладку с текущим фокусом элемента набора вкладок.|
|[CTabCtrl::GetCurSel](#getcursel)|Определяет текущую выбранную вкладку вкладок.|
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, которые в настоящее время используются для вкладок.|
|[CTabCtrl::GetImageList](#getimagelist)|Извлекает список изображений, связанный с элементом управления tab.|
|[CTabCtrl::GetItem](#getitem)|Извлекает сведения о вкладке вкладок.|
|[CTabCtrl::GetItemCount](#getitemcount)|Получает количество вкладок в элементе управления tab.|
|[CTabCtrl::GetItemRect](#getitemrect)|Получает ограничивающий прямоугольник для вкладки в наборе вкладок.|
|[CTabCtrl::GetItemState](#getitemstate)|Получает состояние элемента управления указанной вкладки.|
|[CTabCtrl::GetRowCount](#getrowcount)|Извлекает текущее количество строк вкладок в наборе вкладок.|
|[CTabCtrl::GetToolTips](#gettooltips)|Извлекает дескриптор элемента управления всплывающей подсказки, связанный с элементом управления tab.|
|[CTabCtrl::HighlightItem](#highlightitem)|Задает состояние выделения элемента вкладки.|
|[CTabCtrl::HitTest](#hittest)|Определяет, какие вкладки, с указанными экранными позиции.|
|[CTabCtrl::InsertItem](#insertitem)|Вставляет новую вкладку в наборе вкладок.|
|[CTabCtrl::RemoveImage](#removeimage)|Удаляет изображение из списка изображений набор вкладок.|
|[CTabCtrl::SetCurFocus](#setcurfocus)|Устанавливает фокус на указанной вкладки в наборе вкладок.|
|[CTabCtrl::SetCurSel](#setcursel)|Выбор вкладки в элементе управления tab.|
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для набора вкладок.|
|[CTabCtrl::SetImageList](#setimagelist)|Назначает списка изображений для набора вкладок.|
|[CTabCtrl::SetItem](#setitem)|Задает некоторые или все атрибуты "Вкладка".|
|[CTabCtrl::SetItemExtra](#setitemextra)|Задает число байтов на вкладке, зарезервированный для определяемые приложением данные в наборе вкладок.|
|[CTabCtrl::SetItemSize](#setitemsize)|Задает ширину и высоту элемента.|
|[CTabCtrl::SetItemState](#setitemstate)|Задает состояние элемента управления указанной вкладки.|
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Задает минимальную ширину элементов в наборе вкладок.|
|[CTabCtrl::SetPadding](#setpadding)|Задает объем пространства (заполнения), значок и метку в набор вкладок в каждой вкладке.|
|[CTabCtrl::SetToolTips](#settooltips)|Назначает набор вкладок в элемент управления всплывающей подсказки.|

## <a name="remarks"></a>Примечания

«Вкладка» является аналогом разделителей в записной книжке или меток в картотеке. С помощью элемента управления "Вкладка" приложение может определить несколько страниц для одной области окна или диалогового окна. Каждая страница состоит из набора информации или группу элементов управления, которые приложение отображает, когда пользователь выбирает соответствующую вкладку. Это специальный тип управления "Вкладка" отображает вкладки, которые выглядят как кнопки. После нажатия кнопки должны немедленно выполнить команду вместо отображения страницы.

Этот элемент управления (и, следовательно `CTabCtrl` класс) доступны только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних версиях.

Дополнительные сведения об использовании `CTabCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CTabCtrl](../../mfc/using-ctabctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="adjustrect"></a>  CTabCtrl::AdjustRect

Вычисляет область отображения элемента управления вкладки, указанным прямоугольником окна или вычисляет окно прямоугольник, который будет соответствовать область заданного отображения.

```
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*bLarger*<br/>
Указывает, какие операции необходимо выполнить. Если этот параметр имеет значение TRUE, *lpRect* указывает прямоугольник отображения и получает соответствующие прямоугольной области окна. Если этот параметр имеет значение FALSE, *lpRect* прямоугольной области окна задает и получает соответствующие прямоугольник отображения.

*lpRect*<br/>
Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, которая указывает заданного прямоугольника и получает расчетный прямоугольник.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

##  <a name="create"></a>  CTabCtrl::Create

Создает набор вкладок и присоединяет его к экземпляру `CTabCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль элемента управления tab. Применить любое сочетание [вкладке Стили элемента управления](/windows/desktop/Controls/tab-control-styles), описанные в пакете Windows SDK. См. в разделе **"Примечания"** список стилей окна, которые также можно применить к элементу управления.

*Rect*<br/>
Задает размер и положение элемента управления tab. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.

*pParentWnd*<br/>
Указывает родительскому окну элемента управления вкладки, обычно `CDialog`. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления tab.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инициализация объекта выполнена успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

При создании `CTabCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает вкладок и присоединяет его к `CTabCtrl` объекта.

Помимо стилей элемента управления вкладки вкладки можно применить следующие стили окна:

- WS_CHILD создает дочернее окно, представляющий набор вкладок. Не может использоваться со стилем WS_POPUP.

- WS_VISIBLE создает набор вкладок, изначально является видимым.

- WS_DISABLED создает окно, которое изначально было отключено.

- WS_GROUP указывает первый элемент управления из группы элементов управления, в которых пользователь может перемещаться от одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, определенные с помощью стиля WS_GROUP после первого элемента управления, которым принадлежат той же группе. Следующий элемент управления с помощью стиля WS_GROUP завершает группы стилей и запускается следующая команда (то есть одна команда заканчивается где начинается следующее).

- WS_TABSTOP указывает один из любого числа элементов управления, которые пользователь может перемещать с помощью клавиши TAB. Клавиша TAB перемещает пользователя к следующему элементу управления, указанного стилем WS_TABSTOP.

Чтобы создать набор вкладок с расширенные стили окна, вызовите [CTabCtrl::CreateEx](#createex) вместо `Create`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

##  <a name="createex"></a>  CTabCtrl::CreateEx

Создает элемент управления (дочернего окна) и связывает его с `CTabCtrl` объекта.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.

*dwStyle*<br/>
Задает стиль элемента управления tab. Применить любое сочетание [вкладке Стили элемента управления](/windows/desktop/Controls/tab-control-styles), описанные в пакете Windows SDK. См. в разделе **"Примечания"** в [создать](#create) список стилей окна, которые также можно применить к элементу управления.

*Rect*<br/>
Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родительским для элемента управления.

*nID*<br/>
Идентификатор элемента управления дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, при успешном выполнении в противном случае 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.

`CreateEx` Создает элемент управления с помощью расширенных стилей Windows, определяемое *dwExStyle*. Расширенные стили, определенные для элемента управления с помощью набора [SetExtendedStyle](#setextendedstyle). Например, использовать `CreateEx` такие стили заданы как WS_EX_CONTEXTHELP, но используют `SetExtendedStyle` должны стать TCS_EX_FLATSEPARATORS подобные стили. Дополнительные сведения см. в разделе стили, описанные в [вкладку управления расширенные стили](/windows/desktop/Controls/tab-control-extended-styles) в пакете Windows SDK.

##  <a name="ctabctrl"></a>  CTabCtrl::CTabCtrl

Создает объект `CTabCtrl`.

```
CTabCtrl();
```

##  <a name="deleteallitems"></a>  CTabCtrl::DeleteAllItems

Удаляет все элементы из набора вкладок.

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="deleteitem"></a>  CTabCtrl::DeleteItem

Удаляет указанный элемент из набора вкладок.

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля значение элемента для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

##  <a name="deselectall"></a>  CTabCtrl::DeselectAll

Сбрасывает элементы в набор вкладок, очистка, были нажаты.

```
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>Параметры

*fExcludeFocus*<br/>
Флаг, указывающий область deselection элемента. Если этот параметр имеет значение FALSE, все кнопки на вкладке будут сброшены. Если он имеет значение TRUE, то вкладки все элементы, кроме того, в настоящее время выбран будет выполнен сброс.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщения Win32, [TCM_DESELECTALL](/windows/desktop/Controls/tcm-deselectall), как описано в пакете Windows SDK.

##  <a name="drawitem"></a>  CTabCtrl::DrawItem

Вызывается платформой при изменении внешнего вида рисуемого владельцем элемента управления изменения.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) структуры, описывающий элемент для рисования.

### <a name="remarks"></a>Примечания

`itemAction` Членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CTabCtrl` объекта.

Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* перед этим членом завершении функции.

##  <a name="getcurfocus"></a>  CTabCtrl::GetCurFocus

Извлекает индекс вкладки с текущего фокуса.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс вкладки с текущего фокуса.

##  <a name="getcursel"></a>  CTabCtrl::GetCurSel

Извлекает текущую выбранную вкладку вкладок.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс выбранной вкладки в случае успеха или - 1, если выбрана вкладка "Нет".

##  <a name="getextendedstyle"></a>  CTabCtrl::GetExtendedStyle

Извлекает расширенные стили, которые в настоящее время используются для вкладок.

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Возвращаемое значение

Представляет расширенные стили в настоящий момент для вкладок. Это значение представляет собой сочетание [вкладок расширенные стили](/windows/desktop/Controls/tab-control-extended-styles), как описано в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TCM_GETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-getextendedstyle), как описано в пакете Windows SDK.

##  <a name="getimagelist"></a>  CTabCtrl::GetImageList

Извлекает список изображений, который связан с элементом управления tab.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на список изображений вкладки управления, в случае успешного выполнения; в противном случае — значение NULL.

##  <a name="getitem"></a>  CTabCtrl::GetItem

Извлекает сведения о вкладке вкладок.

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс вкладки.

*pTabCtrlItem*<br/>
Указатель на [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) структуры, можно указать информацию необходимо вернуть. Также используется для получения сведений о вкладке. Эта структура используется с `InsertItem`, `GetItem`, и `SetItem` функций-членов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если выполнение прошло успешно; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

При отправке сообщения, `mask` задает атрибуты, возвращаемые. Если `mask` элемент задает значение TCIF_TEXT `pszText` член должен содержать адрес буфера, который получает текст элемента и `cchTextMax` члена необходимо указать размер буфера.

- `mask`

   Значение, указывающее, какие `TCITEM` членов получить или задать структуры. Этот член может иметь ноль или несколько из следующих значений:

   - TCIF_TEXT `pszText` член является допустимым.

   - TCIF_IMAGE `iImage` член является допустимым.

   - TCIF_PARAM `lParam` член является допустимым.

   - TCIF_RTLREADING текст из `pszText` отображается с использованием порядок чтения справа налево в системах иврит и арабский язык.

   - TCIF_STATE `dwState` член является допустимым.

- `pszText`

   Указатель на заканчивающуюся нулем строку, содержащую текст вкладки, если структура содержит сведения о табуляции. Если структура получает сведения, этот элемент указывает адрес буфера, который получает текст вкладки.

- `cchTextMax`

   Размер буфера, на которые указывают `pszText`. Этот член учитывается, если структура не поступают сведения.

- `iImage` Индекс в вкладку элемента управления списка изображений, или значение-1, если изображение отсутствует для вкладки.

- `lParam`

   Определяемые приложением данные, связанные с вкладкой. При наличии более чем четырьмя байтами определяемые приложением данные на вкладке, приложение должно определить структуру и используйте его вместо `TCITEM` структуры. Должен быть первым членом структуры прикладного [TCITEMHEADER](/windows/desktop/api/commctrl/ns-commctrl-tagtcitemheadera)структуры. `TCITEMHEADER` Структура идентична `TCITEM` структуры, но без `lParam` член. Разница между размером структуры и размер `TCITEMHEADER` структуры должно быть равно количество дополнительных байтов на вкладке.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

##  <a name="getitemcount"></a>  CTabCtrl::GetItemCount

Получает количество вкладок в элементе управления tab.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в элементе управления tab.

### <a name="example"></a>Пример

  См. в примере [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemrect"></a>  CTabCtrl::GetItemRect

Получает ограничивающий прямоугольник для указанной вкладки в наборе вкладок.

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс элемента вкладки.

*lpRect*<br/>
Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает ограничивающий прямоугольник вкладки. Эти координаты использовать текущий режим сопоставления окна просмотра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemstate"></a>  CTabCtrl::GetItemState

Возвращает состояние элемента управления вкладки, идентифицируемый *nItem*.

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс элемента, для которого требуется извлечь сведения о состоянии.

*dwMask*<br/>
Маска, указывающая, какие состояния элемента флаги для возврата. Список значений, см. в разделе маска членом [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) структуры, как описано в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение DWORD, получение сведений о состоянии. Может принимать одно из следующих значений:

|Значение|Описание|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Элемент управления вкладки выбран.|
|TCIS_HIGHLIGHTED|Будет выделен элемент управления вкладки и вкладка и тексты отрисовываются с использованием текущего цвета выделения. При использовании цветом, это будет значение true, интерполяции, не сглаженный цвет.|

### <a name="remarks"></a>Примечания

Состояние элемента определяется `dwState` членом `TCITEM` структуры.

##  <a name="getrowcount"></a>  CTabCtrl::GetRowCount

Извлекает текущее количество строк в наборе вкладок.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество строк из вкладок в элементе управления tab.

### <a name="remarks"></a>Примечания

Только для вкладок со стилем TCS_MULTILINE может иметь несколько строк вкладок.

##  <a name="gettooltips"></a>  CTabCtrl::GetToolTips

Извлекает дескриптор элемента управления всплывающей подсказки, связанный с элементом управления tab.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор элемента управления всплывающей подсказки, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Набор вкладок создает элемент управления всплывающей подсказки, если он имеет стиль TCS_TOOLTIPS. Можно также назначить элемент управления всплывающей подсказки для вкладок с помощью `SetToolTips` функция-член.

##  <a name="highlightitem"></a>  CTabCtrl::HighlightItem

Задает состояние выделения элемента вкладки.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>Параметры

*idItem*<br/>
Отсчитываемый от нуля индекс элемента управления вкладки.

*fHighlight*<br/>
Значение, указывающее состояние выделения устанавливаемое значение. Если это значение равно TRUE, будет выделен вкладке; Если значение равно FALSE, вкладке устанавливается в состояние по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует сообщение Win32 [TCM_HIGHLIGHTITEM](/windows/desktop/Controls/tcm-highlightitem), как описано в пакете Windows SDK.

##  <a name="hittest"></a>  CTabCtrl::HitTest

Определяет, вкладки, если таковые имеются, с указанными экранными позиции.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>Параметры

*pHitTestInfo*<br/>
Указатель на [TCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtchittestinfo) структуры, как описано в пакете SDK для Windows, который указывает положение на экране для тестирования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает отсчитываемый от нуля индекс вкладки или - 1, если в указанной позиции.

##  <a name="insertitem"></a>  CTabCtrl::InsertItem

Вставляет новую вкладку в существующий элемент управления вкладки.

```
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam,
    DWORD dwState,
    DWORD dwStateMask);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс новой вкладки.

*pTabCtrlItem*<br/>
Указатель на [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) структура, задающая атрибуты вкладки.

*lpszItem*<br/>
Адрес нулем строка, содержащая текст вкладки.

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения для вставки в списке изображений.

*nMask*<br/>
Указывает, какие `TCITEM` структуры атрибуты для задания. Может содержать ноль или сочетания из следующих значений:

- TCIF_TEXT `pszText` член является допустимым.

- TCIF_IMAGE `iImage` член является допустимым.

- TCIF_PARAM *lParam* член является допустимым.

- TCIF_RTLREADING текст из `pszText` отображается с использованием порядок чтения справа налево в системах иврит и арабский язык.

- TCIF_STATE *dwState* член является допустимым.

*lParam*<br/>
Определяемые приложением данные, связанные с вкладкой.

*dwState*<br/>
Задает значения для состояния элемента. Дополнительные сведения см. в разделе [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) в пакете Windows SDK.

*dwStateMask*<br/>
Указывает, какие состояния будут устанавливаться. Дополнительные сведения см. в разделе [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс новую вкладку, если выполнение прошло успешно; в противном случае - 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

##  <a name="removeimage"></a>  CTabCtrl::RemoveImage

Удаляет указанный образ из списка изображений набор вкладок.

```
void RemoveImage(int nImage);
```

### <a name="parameters"></a>Параметры

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения, которое требуется удалить.

### <a name="remarks"></a>Примечания

Вкладок обновляет индекс образа для каждой вкладки, чтобы каждая вкладка остается связанным с одного образа.

##  <a name="setcurfocus"></a>  CTabCtrl::SetCurFocus

Устанавливает фокус на указанной вкладки в наборе вкладок.

```
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Указывает индекс вкладки, которая получает фокус.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TCM_SETCURFOCUS](/windows/desktop/Controls/tcm-setcurfocus), как описано в пакете Windows SDK.

##  <a name="setcursel"></a>  CTabCtrl::SetCurSel

Выбор вкладки в элементе управления tab.

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс элемента для выбора.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс ранее выбранной вкладки в случае успеха, в противном случае - 1.

### <a name="remarks"></a>Примечания

Набор вкладок не отправляет сообщение уведомления TCN_SELCHANGING или TCN_SELCHANGE при выборе вкладки с помощью этой функции. Эти уведомления отправляются с помощью WM_NOTIFY, когда пользователь нажимает кнопку или с помощью клавиатуры изменяет вкладки.

##  <a name="setextendedstyle"></a>  CTabCtrl::SetExtendedStyle

Задает расширенные стили для набора вкладок.

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>Параметры

*dwNewStyle*<br/>
Значение, указывающее сочетание вкладку управления расширенные стили.

*dwExMask*<br/>
Значение DWORD, указывающее, какие стили в *dwNewStyle* , могут быть затронуты. Расширенные стили в *dwExMask* будет изменен. Все другие стили сохраняются как есть. Если этот параметр равен нулю, то все стили в *dwNewStyle* будут применяться.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее предыдущего [вкладок расширенные стили](/windows/desktop/Controls/tab-control-extended-styles), как описано в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Эта функция-член реализует поведение сообщение Win32 [TCM_SETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-setextendedstyle), как описано в пакете Windows SDK.

##  <a name="setimagelist"></a>  CTabCtrl::SetImageList

Назначает списка изображений для набора вкладок.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*pImageList*<br/>
Указатель на список изображений, присваиваемое элементом управления tab.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущий список изображений или значение NULL, если нет предыдущего списка изображений.

##  <a name="setitem"></a>  CTabCtrl::SetItem

Задает некоторые или все атрибуты "Вкладка".

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс элемента.

*pTabCtrlItem*<br/>
Указатель на [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) структуру, содержащую новые атрибуты элемента. `mask` Элемент указывает, какие атрибуты следует задать. Если `mask` элемент задает значение TCIF_TEXT `pszText` член является адрес строки с завершающим нулем и `cchTextMax` игнорируется.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [GetItem](#getitem).

##  <a name="setitemextra"></a>  CTabCtrl::SetItemExtra

Задает число байтов на вкладке, зарезервированный для определяемые приложением данные в наборе вкладок.

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>Параметры

*nBytes*<br/>
Количество дополнительных байтов для задания.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [TCM_SETITEMEXTRA](/windows/desktop/Controls/tcm-setitemextra), как описано в пакете Windows SDK.

##  <a name="setitemsize"></a>  CTabCtrl::SetItemSize

Задает ширину и высоту элементов набора вкладок.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Новая ширина и высота (в пикселях) элементов набора вкладок.

### <a name="return-value"></a>Возвращаемое значение

Возвращает старую ширину и высоту элементов набора вкладок.

##  <a name="setitemstate"></a>  CTabCtrl::SetItemState

Задает состояние элемента управления вкладки, идентифицируемый *nItem*.

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс элемента, для которого устанавливаются сведения о состоянии.

*dwMask*<br/>
Маска, указывающая, какие состояния элемента флаги для задания. Список значений, см. в разделе маска членом [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) структуры, как описано в пакете Windows SDK.

*dwState*<br/>
Ссылка на значение DWORD, содержащее сведения о состоянии. Может принимать одно из следующих значений:

|Значение|Описание|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Элемент управления вкладки выбран.|
|TCIS_HIGHLIGHTED|Будет выделен элемент управления вкладки и вкладка и тексты отрисовываются с использованием текущего цвета выделения. При использовании цветом, это будет значение true, интерполяции, не сглаженный цвет.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="setmintabwidth"></a>  CTabCtrl::SetMinTabWidth

Задает минимальную ширину элементов в наборе вкладок.

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>Параметры

*CX*<br/>
Минимальная ширина должен быть задан для элемента управления. Если этот параметр имеет значение-1, элемент управления будет использовать ширину вкладку по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий минимальное табуляции.

### <a name="return-value"></a>Возвращаемое значение

Эта функция-член реализует поведение сообщение Win32 [TCM_SETMINTABWIDTH](/windows/desktop/Controls/tcm-setmintabwidth), как описано в пакете Windows SDK.

##  <a name="setpadding"></a>  CTabCtrl::SetPadding

Задает объем пространства (заполнения), значок и метку в набор вкладок в каждой вкладке.

```
void SetPadding(CSize size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Задает объем пространства (заполнения), значок и метку в набор вкладок в каждой вкладке.

##  <a name="settooltips"></a>  CTabCtrl::SetToolTips

Назначает набор вкладок в элемент управления всплывающей подсказки.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Параметры

*pWndTip*<br/>
Дескриптор элемента управления всплывающей подсказки.

### <a name="remarks"></a>Примечания

Вы можете получить управления всплывающей подсказки, связанный с элементом управления tab, делая вызов к `GetToolTips`.

### <a name="example"></a>Пример

  См. в примере [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
