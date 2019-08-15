---
title: Класс CTabCtrl
ms.date: 11/04/2016
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
ms.openlocfilehash: a0ca4cbad48c420250fe39e131de5504b1ae70f3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502482"
---
# <a name="ctabctrl-class"></a>Класс CTabCtrl

Предоставляет функциональные возможности стандартного элемента управления "вкладка" Windows.

## <a name="syntax"></a>Синтаксис

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CTabCtrl:: CTabCtrl](#ctabctrl)|Создает объект `CTabCtrl`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CTabCtrl:: Аджустрект](#adjustrect)|Вычисляет область просмотра элемента управления вкладки по заданному прямоугольнику окна или вычисляет прямоугольник окна, который соответствует заданной области экрана.|
|[CTabCtrl:: Create](#create)|Создает элемент управления "Вкладка" и присоединяет его к экземпляру `CTabCtrl` объекта.|
|[CTabCtrl:: Креатикс](#createex)|Создает элемент управления "Вкладка" с указанными расширенными стилями Windows и присоединяет его к `CTabCtrl` экземпляру объекта.|
|[CTabCtrl::D Елетеаллитемс](#deleteallitems)|Удаляет все элементы из элемента управления "Вкладка".|
|[CTabCtrl::D Елетеитем](#deleteitem)|Удаляет элемент из элемента управления "Вкладка".|
|[CTabCtrl::D Еселекталл](#deselectall)|Сбрасывает элементы в элементе управления "Вкладка" и очищает все нажатые клавиши.|
|[CTabCtrl::D Равитем](#drawitem)|Рисует указанный элемент элемента управления "Вкладка".|
|[CTabCtrl:: Жеткурфокус](#getcurfocus)|Извлекает вкладку с текущим фокусом элемента управления "Вкладка".|
|[CTabCtrl::GetCurSel](#getcursel)|Определяет текущую выбранную вкладку в элементе управления "Вкладка".|
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, используемые в данный момент для элемента управления "Вкладка".|
|[CTabCtrl::GetImageList](#getimagelist)|Извлекает список изображений, связанных с элементом управления "Вкладка".|
|[CTabCtrl:: DataItem](#getitem)|Извлекает сведения о вкладке в элементе управления "Вкладка".|
|[CTabCtrl::GetItemCount](#getitemcount)|Извлекает число вкладок в наборе вкладок.|
|[CTabCtrl:: Жетитемрект](#getitemrect)|Извлекает ограничивающий прямоугольник для вкладки в элементе управления "Вкладка".|
|[CTabCtrl:: Жетитемстате](#getitemstate)|Получает состояние указанного элемента управления вкладки.|
|[CTabCtrl::GetRowCount](#getrowcount)|Извлекает текущее число строк вкладок в элементе управления "Вкладка".|
|[CTabCtrl:: подсказки](#gettooltips)|Извлекает маркер элемента управления "Подсказка", связанный с элементом управления "Вкладка".|
|[CTabCtrl:: Хигхлигхтитем](#highlightitem)|Задает состояние выделения элемента вкладки.|
|[CTabCtrl:: HitTest](#hittest)|Определяет, какая вкладка, если она есть, находится на заданной позиции экрана.|
|[CTabCtrl:: InsertItem](#insertitem)|Вставляет новую вкладку в элемент управления "Вкладка".|
|[CTabCtrl:: Ремовеимаже](#removeimage)|Удаляет изображение из списка изображений элемента управления "Вкладка".|
|[CTabCtrl:: Сеткурфокус](#setcurfocus)|Устанавливает фокус на указанную вкладку в элементе управления "Вкладка".|
|[CTabCtrl:: Сеткурсел](#setcursel)|Выбирает вкладку в элементе управления "Вкладка".|
|[CTabCtrl:: Сетекстендедстиле](#setextendedstyle)|Задает расширенные стили для элемента управления "Вкладка".|
|[CTabCtrl::SetImageList](#setimagelist)|Присваивает список изображений элементу управления "Вкладка".|
|[CTabCtrl:: Сетитем](#setitem)|Задает некоторые или все атрибуты вкладки.|
|[CTabCtrl:: Сетитемекстра](#setitemextra)|Задает число байтов на вкладку, зарезервированную для определяемых приложением данных в элементе управления "Вкладка".|
|[CTabCtrl:: Сетитемсизе](#setitemsize)|Задает ширину и высоту элемента.|
|[CTabCtrl:: Сетитемстате](#setitemstate)|Задает состояние указанного элемента управления вкладки.|
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Устанавливает минимальную ширину элементов в элементе управления "Вкладка".|
|[CTabCtrl:: Сетпаддинг](#setpadding)|Задает объем пространства (заполнение) вокруг значка и метки каждой вкладки в элементе управления "Вкладка".|
|[CTabCtrl:: Сеттултипс](#settooltips)|Назначает элемент управления «Подсказка» для элемента управления Tab.|

## <a name="remarks"></a>Примечания

Элемент управления "Вкладка" аналогичен разделителям в записной книжке или меткам в CAB-файле. С помощью элемента управления "Вкладка" приложение может определить несколько страниц для одной области окна или диалогового окна. Каждая страница состоит из набора сведений или группы элементов управления, которые отображаются в приложении, когда пользователь выбирает соответствующую вкладку. Специальный тип элемента управления "Вкладка" отображает вкладки, которые выглядят как кнопки. Нажатие кнопки должна сразу же выполнить команду вместо отображения страницы.

Этот элемент управления (и, `CTabCtrl` следовательно, класс) доступен только для программ, работающих под управлением Windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Дополнительные сведения об использовании `CTabCtrl`см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CTabCtrl](../../mfc/using-ctabctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="adjustrect"></a>CTabCtrl:: Аджустрект

Вычисляет область просмотра элемента управления вкладки по заданному прямоугольнику окна или вычисляет прямоугольник окна, который соответствует заданной области экрана.

```
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*бларжер*<br/>
Указывает выполняемую операцию. Если этот параметр имеет значение TRUE, *лпрект* задает отображаемый прямоугольник и получает соответствующий прямоугольник окна. Если этот параметр имеет значение FALSE, *лпрект* задает прямоугольник окна и получает соответствующий отображаемый прямоугольник.

*лпрект*<br/>
Указатель на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , которая указывает заданный прямоугольник и получает вычисляемый прямоугольник.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

##  <a name="create"></a>CTabCtrl:: Create

Создает элемент управления "Вкладка" и присоединяет его к экземпляру `CTabCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль элемента управления Tab. Примените любое сочетание [стилей элементов управления Tab](/windows/win32/Controls/tab-control-styles), описанное в Windows SDK. См. раздел **Примечания** для списка стилей окна, которые также можно применить к элементу управления.

*rect*<br/>
Задает размер и позицию элемента управления "Вкладка". Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/previous-versions/dd162897\(v=vs.85\)) .

*ппарентвнд*<br/>
Задает родительское окно элемента управления вкладки, обычно `CDialog`. Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления вкладки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инициализация объекта выполнена успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

`CTabCtrl` Объект создается в два этапа. Сначала вызовите конструктор, а затем вызовите `Create`метод, который создает элемент управления "Вкладка" и присоединяет `CTabCtrl` его к объекту.

В дополнение к стилям элемента управления "Вкладка" к элементу управления "Вкладка" можно применить следующие стили окна:

- WS_CHILD создает дочернее окно, представляющее элемент управления "Вкладка". Не может использоваться с WS_POPUP стилем.

- WS_VISIBLE создает элемент управления "Вкладка", который изначально является видимым.

- WS_DISABLED создает окно, которое изначально отключено.

- WS_GROUP указывает первый элемент управления группы элементов управления, в которой пользователь может перемещаться от одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, определенные с WS_GROUP стилем после первого элемента управления, принадлежат к одной группе. Следующий элемент управления с стилем WS_GROUP завершает группу стилей и запускает следующую группу (то есть одна группа заканчивается, где начинается следующая).

- WS_TABSTOP указывает одно из нескольких элементов управления, через которое пользователь может перемещаться с помощью клавиши TAB. Клавиша TAB перемещает пользователя к следующему элементу управления, заданному стилем WS_TABSTOP.

Чтобы создать элемент управления "Вкладка" с расширенными стилями окна, вызовите метод `Create` [CTabCtrl:: креатикс](#createex) вместо.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

##  <a name="createex"></a>CTabCtrl:: Креатикс

Создает элемент управления (дочернее окно) и связывает его с `CTabCtrl` объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двексстиле*<br/>
Задает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе параметр *двексстиле* для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

*двстиле*<br/>
Задает стиль элемента управления Tab. Примените любое сочетание [стилей элементов управления Tab](/windows/win32/Controls/tab-control-styles), описанное в Windows SDK. Список стилей окон, которые также можно применить к элементу управления, см. в разделе **Примечания** в [CREATE](#create) .

*rect*<br/>
Ссылка на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , описывающую размер и расположение создаваемого окна в клиентских координатах *ппарентвнд*.

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*nID*<br/>
Идентификатор дочернего окна элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешное выполнение равно 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [CREATE](#create) , чтобы применить расширенные стили Windows, заданные в расширенном стиле Windows в качестве префикса **WS_EX_** .

`CreateEx`создает элемент управления с расширенными стилями Windows, заданным параметром *двексстиле*. Установка расширенных стилей, относящихся к элементу управления с помощью [сетекстендедстиле](#setextendedstyle). Например, используйте `CreateEx` для установки таких стилей, как WS_EX_CONTEXTHELP, но используйте `SetExtendedStyle` для установки таких стилей, как TCS_EX_FLATSEPARATORS. Дополнительные сведения см. в статье стили, описанные в разделе « [Управление расширенными стилями](/windows/win32/Controls/tab-control-extended-styles) » в Windows SDK.

##  <a name="ctabctrl"></a>CTabCtrl:: CTabCtrl

Создает объект `CTabCtrl`.

```
CTabCtrl();
```

##  <a name="deleteallitems"></a>CTabCtrl::D Елетеаллитемс

Удаляет все элементы из элемента управления "Вкладка".

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="deleteitem"></a>CTabCtrl::D Елетеитем

Удаляет указанный элемент из элемента управления "Вкладка".

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемое от нуля значение удаляемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

##  <a name="deselectall"></a>CTabCtrl::D Еселекталл

Сбрасывает элементы в элементе управления "Вкладка" и очищает все нажатые клавиши.

```
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>Параметры

*фексклудефокус*<br/>
Флаг, указывающий область девыделения элемента. Если этот параметр имеет значение FALSE, то все кнопки на вкладке будут сброшены. Если задано значение TRUE, все элементы вкладки, кроме выбранного в данный момент, будут сброшены.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TCM_DESELECTALL](/windows/win32/Controls/tcm-deselectall), как описано в Windows SDK.

##  <a name="drawitem"></a>CTabCtrl::D Равитем

Вызывается структурой при изменении визуального аспекта элемента управления "Вкладка", рисуемого владельцем.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*лпдравитемструкт*<br/>
Указатель на структуру [дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , описывающую закрашиваемый элемент.

### <a name="remarks"></a>Примечания

`itemAction` Элемент`DRAWITEMSTRUCT` структуры определяет выполняемое действие рисования.

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию-член, чтобы реализовать Рисование для объекта `CTabCtrl` , рисуемого владельцем.

Приложение должно восстановить все объекты интерфейса графических устройств (GDI), выбранные для контекста вывода, указанного в *лпдравитемструкт* , перед завершением этой функции-члена.

##  <a name="getcurfocus"></a>CTabCtrl:: Жеткурфокус

Извлекает индекс вкладки с текущим фокусом.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс вкладки с текущим фокусом.

##  <a name="getcursel"></a>CTabCtrl:: рекурсивно

Извлекает текущую выбранную вкладку в элементе управления "Вкладка".

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс выбранной вкладки в случае успеха или-1, если вкладка не выбрана.

##  <a name="getextendedstyle"></a>CTabCtrl:: Жетекстендедстиле

Извлекает расширенные стили, используемые в данный момент для элемента управления "Вкладка".

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Возвращаемое значение

Представляет расширенные стили, используемые в данный момент для элемента управления "Вкладка". Это значение представляет собой сочетание [расширенных стилей элемента управления Tab](/windows/win32/Controls/tab-control-extended-styles), как описано в Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TCM_GETEXTENDEDSTYLE](/windows/win32/Controls/tcm-getextendedstyle), как описано в Windows SDK.

##  <a name="getimagelist"></a>CTabCtrl::/ImageList

Извлекает список изображений, связанных с элементом управления "Вкладка".

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на список изображений элемента управления Tab; в противном случае значение NULL.

##  <a name="getitem"></a>CTabCtrl:: DataItem

Извлекает сведения о вкладке в элементе управления "Вкладка".

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемый от нуля индекс вкладки.

*птабктрлитем*<br/>
Указатель на структуру [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) , используемую для указания извлекаемой информации. Также используется для получения сведений о вкладке. Эта структура используется с `InsertItem`функциями-членами, `GetItem`и `SetItem` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

При отправке `mask` сообщения член указывает, какие атрибуты должны быть возвращены. Если член задает значение TCIF_TEXT, то `pszText` элемент должен содержать адрес буфера, который получает текст элемента, а `cchTextMax` член должен задавать размер буфера. `mask`

- `mask`

   Значение, указывающее `TCITEM` , какие элементы структуры извлекаются или задаются. Этот элемент может быть нулевым или иметь сочетание следующих значений:

   - `pszText` TCIF_TEXT элемент является допустимым.

   - `iImage` TCIF_IMAGE элемент является допустимым.

   - `lParam` TCIF_PARAM элемент является допустимым.

   - TCIF_RTLREADING текст `pszText` отображается с использованием порядка чтения справа налево в системах на иврите или арабском языке.

   - `dwState` TCIF_STATE элемент является допустимым.

- `pszText`

   Указатель на строку с завершающим нулем, содержащую текст вкладки, если структура содержит сведения о вкладке. Если структура получает сведения, этот член задает адрес буфера, который получает текст вкладки.

- `cchTextMax`

   Размер буфера, `pszText`на который указывает. Этот элемент игнорируется, если структура не получает сведений.

- `iImage`Индекс в списке изображений элемента управления Tab или-1, если для вкладки нет изображения.

- `lParam`

   Определяемые приложением данные, связанные с вкладкой. Если на одну вкладку приходится более четырех байтов определяемых приложением данных, приложение должно определить структуру и использовать ее вместо `TCITEM` структуры. Первый член определяемой приложением структуры должен быть структурой [тЦитемхеадер](/windows/win32/api/commctrl/ns-commctrl-tcitemheaderw). Структура идентична `TCITEM` структуре, но без элемента.`lParam` `TCITEMHEADER` Разница между размером структуры и размером `TCITEMHEADER` структуры должна равняться количеству дополнительных байтов на вкладку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

##  <a name="getitemcount"></a>CTabCtrl:: GetItemCount

Извлекает число вкладок в наборе вкладок.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в элементе управления "Вкладка".

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: TabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemrect"></a>CTabCtrl:: Жетитемрект

Извлекает ограничивающий прямоугольник для указанной вкладки в элементе управления "Вкладка".

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемый от нуля индекс элемента вкладки.

*лпрект*<br/>
Указатель на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , которая получает ограничивающий прямоугольник вкладки. Эти координаты используют текущий режим сопоставления окна просмотра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: TabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemstate"></a>CTabCtrl:: Жетитемстате

Получает состояние элемента управления вкладки, идентифицируемого *нитем*.

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемый от нуля номер индекса элемента, для которого требуется получить сведения о состоянии.

*двмаск*<br/>
Маска, указывающая, какие из флагов состояния элемента должны быть возвращены. Список значений см. в разделе mask структуры [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) , как описано в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение DWORD, получающее сведения о состоянии. Может принимать одно из следующих значений:

|Значение|Описание|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Элемент управления вкладки выбран.|
|TCIS_HIGHLIGHTED|Элемент управления вкладки выделяется, а вкладка и текст рисуются с использованием текущего цвета выделения. При использовании цвета выделения это будет истинной интерполяцией, а не с перекрашенным цветом.|

### <a name="remarks"></a>Примечания

Состояние элемента задается `dwState` членом `TCITEM` структуры.

##  <a name="getrowcount"></a>CTabCtrl:: RowCount

Извлекает текущее количество строк в элементе управления "Вкладка".

```
int GetRowCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество строк вкладок в элементе управления "Вкладка".

### <a name="remarks"></a>Примечания

Только элементы управления "Вкладка", имеющие стиль TCS_MULTILINE, могут иметь несколько строк вкладок.

##  <a name="gettooltips"></a>CTabCtrl:: подсказки

Извлекает маркер элемента управления "Подсказка", связанный с элементом управления "Вкладка".

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Возвращаемое значение

При успешном завершении элемента управления Подсказка в противном случае — NULL.

### <a name="remarks"></a>Примечания

Элемент управления "Вкладка" создает элемент управления "всплывающая подсказка", если он имеет стиль TCS_TOOLTIPS. Можно также назначить элемент управления "Подсказка" для элемента управления "Вкладка `SetToolTips` " с помощью функции-члена.

##  <a name="highlightitem"></a>CTabCtrl:: Хигхлигхтитем

Задает состояние выделения элемента вкладки.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>Параметры

*идитем*<br/>
Отсчитываемый от нуля индекс элемента управления вкладки.

*фхигхлигхт*<br/>
Значение, указывающее заданное состояние выделения. Если это значение равно TRUE, вкладка выделена; Если значение равно FALSE, то для вкладки задано состояние по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует [TCM_HIGHLIGHTITEM](/windows/win32/Controls/tcm-highlightitem)сообщения Win32, как описано в Windows SDK.

##  <a name="hittest"></a>CTabCtrl:: HitTest

Определяет, какая вкладка, если она есть, находится на заданной позиции экрана.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>Параметры

*фиттестинфо*<br/>
Указатель на структуру [тчиттестинфо](/windows/win32/api/commctrl/ns-commctrl-tchittestinfo) , как описано в Windows SDK, указывающей на экран, который нужно проверить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает отсчитываемый от нуля индекс вкладки или-1, если вкладка не находится в указанной позиции.

##  <a name="insertitem"></a>CTabCtrl:: InsertItem

Вставляет новую вкладку в существующий элемент управления "Вкладка".

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

*нитем*<br/>
Отсчитываемый от нуля индекс новой вкладки.

*птабктрлитем*<br/>
Указатель на структуру [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) , указывающую атрибуты вкладки.

*лпсзитем*<br/>
Адрес строки, завершающейся нулем, которая содержит текст вкладки.

*нимаже*<br/>
Отсчитываемый от нуля индекс изображения, вставляемого из списка изображений.

*нмаск*<br/>
Указывает, `TCITEM` какие атрибуты структуры задаются. Может быть нулем или сочетанием следующих значений:

- `pszText` TCIF_TEXT элемент является допустимым.

- `iImage` TCIF_IMAGE элемент является допустимым.

- TCIF_PARAM является допустимым членом *lParam* .

- TCIF_RTLREADING текст `pszText` отображается с использованием порядка чтения справа налево в системах на иврите или арабском языке.

- TCIF_STATE является допустимым членом *двстате* .

*lParam*<br/>
Определяемые приложением данные, связанные с вкладкой.

*двстате*<br/>
Указывает значения для состояний элемента. Дополнительные сведения см. в разделе [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) в Windows SDK.

*двстатемаск*<br/>
Указывает, какие состояния должны быть установлены. Дополнительные сведения см. в разделе [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс новой вкладки в случае успеха; в противном случае — 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

##  <a name="removeimage"></a>CTabCtrl:: Ремовеимаже

Удаляет указанный образ из списка изображений элемента управления "Вкладка".

```
void RemoveImage(int nImage);
```

### <a name="parameters"></a>Параметры

*нимаже*<br/>
Отсчитываемый от нуля индекс удаляемого изображения.

### <a name="remarks"></a>Примечания

Элемент управления "Вкладка" обновляет индекс изображения каждой вкладки, чтобы каждая вкладка осталась связанной с одним и тем же изображением.

##  <a name="setcurfocus"></a>CTabCtrl:: Сеткурфокус

Устанавливает фокус на указанную вкладку в элементе управления "Вкладка".

```
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Указывает индекс вкладки, получающей фокус.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TCM_SETCURFOCUS](/windows/win32/Controls/tcm-setcurfocus), как описано в Windows SDK.

##  <a name="setcursel"></a>CTabCtrl:: Сеткурсел

Выбирает вкладку в элементе управления "Вкладка".

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемый от нуля индекс элемента, который необходимо выбрать.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс ранее выбранной вкладки в случае успеха, в противном случае — 1.

### <a name="remarks"></a>Примечания

Элемент управления "Вкладка" не отправляет сообщение уведомления TCN_SELCHANGING или TCN_SELCHANGE, если выбрана вкладка с помощью этой функции. Эти уведомления отправляются с помощью WM_NOTIFY, когда пользователь нажимает или использует клавиатуру для изменения вкладок.

##  <a name="setextendedstyle"></a>CTabCtrl:: Сетекстендедстиле

Задает расширенные стили для элемента управления "Вкладка".

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>Параметры

*двневстиле*<br/>
Значение, указывающее сочетание расширенных стилей элемента управления Tab.

*двексмаск*<br/>
Значение типа DWORD, указывающее, какие стили в *двневстиле* должны быть затронуты. Будут изменены только расширенные стили в *двексмаск* . Все остальные стили будут поддерживаться как есть. Если этот параметр равен нулю, будут затронуты все стили в *двневстиле* .

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD, содержащее предыдущий [элемент управления Tab, расширенные стили](/windows/win32/Controls/tab-control-extended-styles), как описано в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Эта функция члена реализует поведение сообщения Win32 [TCM_SETEXTENDEDSTYLE](/windows/win32/Controls/tcm-setextendedstyle), как описано в Windows SDK.

##  <a name="setimagelist"></a>CTabCtrl:: Сетимажелист

Присваивает список изображений элементу управления "Вкладка".

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*пимажелист*<br/>
Указатель на список изображений, назначаемый элементу управления "Вкладка".

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущий список изображений или значение NULL, если предыдущий список изображений отсутствует.

##  <a name="setitem"></a>CTabCtrl:: Сетитем

Задает некоторые или все атрибуты вкладки.

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемый от нуля индекс элемента.

*птабктрлитем*<br/>
Указатель на структуру [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) , содержащую новые атрибуты элемента. `mask` Член указывает, какие атрибуты задаются. Если член задает значение TCIF_TEXT, то `pszText` членом является адрес строки, `cchTextMax` завершающейся нулем, и элемент игнорируется. `mask`

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. пример для [элемента "DataItem](#getitem)".

##  <a name="setitemextra"></a>CTabCtrl:: Сетитемекстра

Задает число байтов на вкладку, зарезервированную для определяемых приложением данных в элементе управления "Вкладка".

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>Параметры

*nBytes*<br/>
Число устанавливаемых дополнительных байтов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TCM_SETITEMEXTRA](/windows/win32/Controls/tcm-setitemextra), как описано в Windows SDK.

##  <a name="setitemsize"></a>CTabCtrl:: Сетитемсизе

Задает ширину и высоту элементов набора вкладок.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Новая ширина и высота (в пикселях) элементов набора вкладок.

### <a name="return-value"></a>Возвращаемое значение

Возвращает старую ширину и высоту элементов набора вкладок.

##  <a name="setitemstate"></a>CTabCtrl:: Сетитемстате

Задает состояние элемента управления вкладки, идентифицируемого *нитем*.

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемый от нуля номер индекса элемента, для которого задаются сведения о состоянии.

*двмаск*<br/>
Маска, указывающая, какие флаги состояния элемента задаются. Список значений см. в разделе mask структуры [тЦитем](/windows/win32/api/commctrl/ns-commctrl-tcitemw) , как описано в Windows SDK.

*двстате*<br/>
Ссылка на значение DWORD, содержащее сведения о состоянии. Может принимать одно из следующих значений:

|Значение|Описание|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Элемент управления вкладки выбран.|
|TCIS_HIGHLIGHTED|Элемент управления вкладки выделяется, а вкладка и текст рисуются с использованием текущего цвета выделения. При использовании цвета выделения это будет истинной интерполяцией, а не с перекрашенным цветом.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="setmintabwidth"></a>CTabCtrl:: Сетминтабвидс

Устанавливает минимальную ширину элементов в элементе управления "Вкладка".

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>Параметры

*cx*<br/>
Минимальная ширина, устанавливаемая для элемента управления вкладки. Если этот параметр имеет значение-1, то элемент управления будет использовать ширину табуляции по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая минимальная ширина вкладки.

### <a name="return-value"></a>Возвращаемое значение

Эта функция члена реализует поведение сообщения Win32 [TCM_SETMINTABWIDTH](/windows/win32/Controls/tcm-setmintabwidth), как описано в Windows SDK.

##  <a name="setpadding"></a>CTabCtrl:: Сетпаддинг

Задает объем пространства (заполнение) вокруг значка и метки каждой вкладки в элементе управления "Вкладка".

```
void SetPadding(CSize size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Задает объем пространства (заполнение) вокруг значка и метки каждой вкладки в элементе управления "Вкладка".

##  <a name="settooltips"></a>CTabCtrl:: Сеттултипс

Назначает элемент управления «Подсказка» для элемента управления Tab.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Параметры

*пвндтип*<br/>
Маркер элемента управления "Подсказка".

### <a name="remarks"></a>Примечания

Можно получить элемент управления "Подсказка", связанный с элементом управления "Вкладка" `GetToolTips`, вызвав метод.

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: TabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
