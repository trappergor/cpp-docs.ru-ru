---
title: CComboBox-класс
ms.date: 11/04/2016
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
ms.openlocfilehash: 9509b122e271ac22529c1b8a7b8e8d0b4b50025b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641107"
---
# <a name="ccombobox-class"></a>CComboBox-класс

Предоставляет функции поля со списком Windows.

## <a name="syntax"></a>Синтаксис

```
class CComboBox : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|Создает объект `CComboBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|Добавляет строку в конец списка в окне списка, поле со списком или в отсортированном позиции для поля списка CBS_SORT стиль.|
|[CComboBox::Clear](#clear)|Удаляет (очищает) текущее выделение, если таковое имеется, в элементе управления.|
|[CComboBox::CompareItem](#compareitem)|Вызывается платформой для определения относительной позиции нового элемента списка в отсортированном определяемое владельцем поле со списком.|
|[CComboBox::Copy](#copy)|Копирует текущее выделение, если таковое имеется, в буфер обмена в формате CF_TEXT.|
|[CComboBox::Create](#create)|Создает поле со списком и присоединяет его к `CComboBox` объекта.|
|[CComboBox::Cut](#cut)|Удаляет (порезов) текущее выделение, если имеется, в политике изменения в элемент управления и копирует удаленный текст в буфер обмена в формате CF_TEXT.|
|[CComboBox::DeleteItem](#deleteitem)|Вызывается платформой при удалении элемента списка определяемое владельцем поле со списком.|
|[CComboBox::DeleteString](#deletestring)|Удаляет строку из списка поля со списком.|
|[CComboBox::Dir](#dir)|Добавляет список имен файлов в список поля со списком.|
|[CComboBox::DrawItem](#drawitem)|Вызывается платформой при изменении внешнего вида изменяется рисуемый владельцем поле со списком.|
|[CComboBox::FindString](#findstring)|Выполняет поиск первой строки, которая содержит указанный префикс в списке поля со списком.|
|[CComboBox::FindStringExact](#findstringexact)|Находит первый списка строки (в поле со списком), совпадающий с указанной строкой.|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Извлекает сведения о `CComboBox` объекта.|
|[CComboBox::GetCount](#getcount)|Получает число элементов в списке поля со списком.|
|[CComboBox::GetCueBanner](#getcuebanner)|Возвращает текст подсказки, отображаемый для элемента управления поля со списком.|
|[CComboBox::GetCurSel](#getcursel)|Извлекает индекс выбранного элемента, если таковой имеется, в списке поля со списком.|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Получает экранные координаты видимым (удаленные вниз) поля с раскрывающимся списком.|
|[CComboBox::GetDroppedState](#getdroppedstate)|Определяет, является ли поле со списком с раскрывающимся списком видимым (раскрыл).|
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Получает минимальную допустимую ширину для части раскрывающегося списка в поле со списком.|
|[CComboBox::GetEditSel](#geteditsel)|Возвращает позиции символов начала и конца текущего выделения в элементе управления списком.|
|[CComboBox::GetExtendedUI](#getextendedui)|Определяет, имеет ли поле со списком пользовательского интерфейса по умолчанию или расширенный пользовательский интерфейс.|
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пикселях, что часть списка поля со списком может прокручиваться по горизонтали.|
|[CComboBox::GetItemData](#getitemdata)|Извлекает значение 32-разрядных предоставляемую приложением, связанный с элементом указанного поле со списком.|
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Извлекает 32-разрядного указателя предоставляемую приложением, который связан с элементом указанного поле со списком.|
|[CComboBox::GetItemHeight](#getitemheight)|Получает высоту элементов списка в поле со списком.|
|[CComboBox::GetLBText](#getlbtext)|Получает строку из списка поля со списком.|
|[CComboBox::GetLBTextLen](#getlbtextlen)|Получает длину строки в списке поля со списком.|
|[CComboBox::GetLocale](#getlocale)|Извлекает идентификатор языкового стандарта для поле со списком.|
|[CComboBox::GetMinVisible](#getminvisible)|Получает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.|
|[CComboBox::GetTopIndex](#gettopindex)|Возвращает индекс первой видимой позиции в списке части поля со списком.|
|[CComboBox::InitStorage](#initstorage)|Выделяет блоки памяти для элементов и строк в списке части поля со списком.|
|[CComboBox::InsertString](#insertstring)|Вставляет строку в список поля со списком.|
|[CComboBox::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в поле ввода поля со списком.|
|[CComboBox::MeasureItem](#measureitem)|Вызывается платформой для определения измерения поле со списком, когда создается определяемое владельцем поле со списком.|
|[CComboBox::Paste](#paste)|Вставляет данные из буфера обмена в элемент управления в текущей позиции курсора. Данные вставляются только в том случае, если буфер обмена содержит данные в формате CF_TEXT.|
|[CComboBox::ResetContent](#resetcontent)|Удаляет все элементы из списка, поле и элемент управления списком.|
|[CComboBox::SelectString](#selectstring)|Выполняет поиск строки в списке поля со списком и, если строка найдена, выбирает строки в поле со списком и копирует строки в элемент управления редактирования.|
|[CComboBox::SetCueBanner](#setcuebanner)|Задает текст подсказки, отображаемый для элемента управления поля со списком.|
|[CComboBox::SetCurSel](#setcursel)|Выбирает строку в списке поля со списком.|
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Задает минимальную допустимую ширину для части раскрывающегося списка в поле со списком.|
|[CComboBox::SetEditSel](#seteditsel)|Выбирает символы в элементе управления списком.|
|[CComboBox::SetExtendedUI](#setextendedui)|Выбирает значение по умолчанию пользовательский интерфейс или расширенный пользовательский интерфейс для поле со списком, в которой стиль CBS_DROPDOWN или CBS_DROPDOWNLIST.|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Задает ширину в пикселях, что часть списка поля со списком может прокручиваться по горизонтали.|
|[CComboBox::SetItemData](#setitemdata)|Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.|
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Задает 32-разрядный указатель, связанный с указанным элементом в поле со списком.|
|[CComboBox::SetItemHeight](#setitemheight)|Задает высоту элементов списка в поле со списком или высоту элемента управления редактирования (или статического текста) часть поле со списком.|
|[CComboBox::SetLocale](#setlocale)|Задает идентификатор языкового стандарта для поле со списком.|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Задает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.|
|[CComboBox::SetTopIndex](#settopindex)|Указывает части списка в поле со списком для отображения элемента с указанным индексом в верхней.|
|[CComboBox::ShowDropDown](#showdropdown)|Показывает или скрывает поле со списком, в которой стиль CBS_DROPDOWN или CBS_DROPDOWNLIST поле со списком.|

## <a name="remarks"></a>Примечания

Поле со списком состоит из поле со списком, в сочетании со статический элемент управления или элемент управления. Часть списка элемента управления могут отображаться все время или только может раскрывающийся список, когда пользователь щелкнет стрелку раскрывающегося списка рядом с элементом управления.

Выбранного элемента (если таковые имеются) в поле со списком отображается в статический или изменение элемента управления. Кроме того Если поле со списком имеет стиль стрелку раскрывающегося списка, пользователь может вводить буквы один из элементов в списке, и списка, если он отображается, будут выделите следующий элемент с этого начального знака.

В следующей таблице сравниваются три поля со списком [стили](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

|Стиль|Когда отображается поле со списком|Статический метод или редактирования элемента управления|
|-----------|-------------------------------|-----------------------------|
|Простая|Всегда|Правка|
|Drop-down|При удалении|Правка|
|Раскрывающийся список|При удалении|Static|

Можно создать `CComboBox` объект на основе шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CComboBox` для создания `CComboBox` объект; затем вызвать [создать](#create) функцию-член для создания элемента управления и присоединить его к `CComboBox` объекта.

Если вы хотите обрабатывать сообщения Windows уведомления, отправленные поле со списком с родительским (обычно класс, производный от `CDialog`), добавить схему сообщений входа и обработчик сообщений функцию-член в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

**ON_** уведомления **(**`id`**,**`memberFxn`**)**

где `id` указывает идентификатор дочернего окна элемента управления полем со списком, отправляющего уведомление и `memberFxn` имя функции-члена родительской вы написали для обработки уведомления.

Родительский прототип функции выглядит следующим образом:

**afx_msg** `void` `memberFxn` **();**

Порядок, в котором некоторые уведомления будут отправляться, предсказать нельзя. В частности CBN_SELCHANGE уведомление может возникнуть до или после CBN_CLOSEUP уведомление.

Ниже перечислены возможные записей карты.

- ON_CBN_CLOSEUP (Windows 3.1 и более поздних версий.) В списке поле со списком закрытия. Это сообщение уведомления не отправляются для поле со списком, который имеет [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля.

- ON_CBN_DBLCLK пользователь дважды щелкает строку в списке поля со списком. Это сообщение уведомления отправляется только для поля со списком в стиле CBS_SIMPLE. Для поля со списком с [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) в стиле, как двойной щелчок будет невозможен, так как одним щелчком скрывает поле со списком.

- ON_CBN_DROPDOWN списке списком — раскрывающийся список (виден). Это сообщение уведомления могут выполняться только для поле со списком в стиле CBS_DROPDOWN или CBS_DROPDOWNLIST.

- ON_CBN_EDITCHANGE пользователя были предприняты никакие действие, которое может изменен текст в элемент управления Правка части поле со списком. В отличие от CBN_EDITUPDATE сообщение это сообщение отправляется после обновления экрана в Windows. Она не отправляется, если поле со списком имеет стиль CBS_DROPDOWNLIST.

- ON_CBN_EDITUPDATE элемент управления Правка часть поле со списком — об изменении отображаемого текста. Это сообщение уведомления отправляется после форматирования текста элемента управления, но до отображения текста. Она не отправляется, если поле со списком имеет стиль CBS_DROPDOWNLIST.

- ON_CBN_ERRSPACE поле со списком не удается выделить достаточно памяти для выполнения конкретного запроса.

- ON_CBN_SELENDCANCEL (Windows 3.1 и более поздних версий.) Указывает, что следует отменить выбор пользователя. Пользователь щелкает элемент и затем нажимает другого окна или элемента управления, чтобы скрыть список поля со списком. Это сообщение уведомления отправляется перед уведомление CBN_CLOSEUP, чтобы указать, что следует игнорировать выбора пользователя. CBN_SELENDCANCEL или CBN_SELENDOK сообщение уведомления отправляется, даже если CBN_CLOSEUP сообщение уведомления не отправляются (как в случае поле со списком в стиле CBS_SIMPLE).

- ON_CBN_SELENDOK пользователь выбирает элемент и затем нажимает клавишу ВВОД или нажимает клавишу Стрелка вниз, чтобы скрыть список поля со списком. Это сообщение уведомления отправляется перед сообщением CBN_CLOSEUP, чтобы указать, что выбранный пользователем должно считаться допустимым. CBN_SELENDCANCEL или CBN_SELENDOK сообщение уведомления отправляется, даже если CBN_CLOSEUP сообщение уведомления не отправляются (как в случае поле со списком в стиле CBS_SIMPLE).

- ON_CBN_KILLFOCUS поле со списком теряет фокус ввода.

- ON_CBN_SELCHANGE элементом, выбранным в списке поля со списком будет изменяться в результате пользователь, щелкнув в окне списка или изменения выделения с помощью клавиш со стрелками. При обработке этого сообщения, текст в элементе управления поля со списком можно получить только через `GetLBText` или другой ту же функцию. `GetWindowText` нельзя использовать.

- ON_CBN_SETFOCUS поле со списком получает фокус ввода.

Если вы создаете `CComboBox` объекта в диалоговом окне (с помощью ресурса диалогового окна), `CComboBox` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

При внедрении `CComboBox` объекта в объект в другом окне, необходимо уничтожить его. Если вы создаете `CComboBox` объект в стеке, он будет удален автоматически. При создании `CComboBox` объект в куче с помощью **новый** функцию, необходимо вызвать **удалить** в объекте уничтожить его при уничтожении поле со списком Windows.

**Примечание** требуется обрабатывать сообщения WM_KEYDOWN и WM_CHAR, необходимость подкласс списком измените и список элементов управления, создавать производные классы от `CEdit` и `CListBox`, и добавьте обработчики для этих сообщений для производных классов. Дополнительные сведения см. в разделе [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="addstring"></a>  CComboBox::AddString

Добавляет строку в списке поля со списком.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*lpszString*<br/>
Указатель на заканчивающуюся нулем строку, который должен быть добавлен.

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, это отсчитываемый от нуля индекс строки в поле со списком. Возвращает значение CB_ERR при возникновении ошибки; Возвращаемое значение является CB_ERRSPACE, если недостаточно места для хранения новой строки.

### <a name="remarks"></a>Примечания

Если поле со списком не был создан с помощью [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, строка добавляется в конец списка. В противном случае строка вставляется в списке, и список отсортирован.

> [!NOTE]
>  Эта функция не поддерживается Windows `ComboBoxEx` элемента управления. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/desktop/Controls/comboboxex-controls) в пакете Windows SDK.

Чтобы вставить строку в определенное место в пределах списка, используйте [InsertString](#insertstring) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

##  <a name="ccombobox"></a>  CComboBox::CComboBox

Создает объект `CComboBox`.

```
CComboBox();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

##  <a name="clear"></a>  CComboBox::Clear

Удаляет (очищает) текущее выделение, если таковой имеется, в поле ввода поля со списком.

```
void Clear();
```

### <a name="remarks"></a>Примечания

Чтобы удалить текущее выделение и помещает удаленные содержимое в буфер обмена, используйте [Вырезать](#cut) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

##  <a name="compareitem"></a>  CComboBox::CompareItem

Вызывается платформой для определения относительной позиции нового элемента в списке части отсортированный рисования владельцем поле со списком.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Параметры

*lpCompareItemStruct*<br/>
Длинный указатель на [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) структуры.

### <a name="return-value"></a>Возвращаемое значение

Показывает относительное положение двух элементов, описанных в `COMPAREITEMSTRUCT` структуры. Это может быть любой из следующих значений:

|Значение|Значение|
|-----------|-------------|
|- 1|Элемент 1 предшествует элемент 2.|
|0|1 и 2 элемент сортировки же.|
|1|Элемент 1 сортирует после элемента 2.|

См. в разделе [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) описание `COMPAREITEMSTRUCT`.

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. При создании рисуемого владельцем поле со списком в стиле LBS_SORT, необходимо переопределить эту функцию-член для помощи в framework в сортировке новые элементы добавлены в поле со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

##  <a name="copy"></a>  CComboBox::Copy

Копирует текущее выделение, если таковой имеется, в поле ввода поля со списком в буфер обмена в формате CF_TEXT.

```
void Copy();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

##  <a name="create"></a>  CComboBox::Create

Создает поле со списком и присоединяет его к `CComboBox` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль поля со списком. Применить любое сочетание [поле со списком стилей](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) в поле.

*Rect*<br/>
Указывает положение и размер поля со списком. Может быть [структура RECT](../../mfc/reference/rect-structure1.md) или `CRect` объекта.

*pParentWnd*<br/>
Указывает поле со списком родительского окна (обычно `CDialog`). Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CComboBox` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает поле со списком Windows и присоединяет его к `CComboBox` объекта.

Когда `Create` выполняет, Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения в поле со списком.

Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить обработку сообщения по умолчанию, являются производными от класса `CComboBox`, добавить схему сообщений к новому классу и переопределить выше функции-члены обработчика сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.

Примените следующий [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления списком. :

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_VSCROLL для добавления вертикальная прокрутка для поля со списком в поле со списком

- WS_HSCROLL для добавления горизонтальной прокрутки для списка в поле со списком

- WS_GROUP для группировки элементов управления

- WS_TABSTOP Чтобы включить поле со списком в порядок следования

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

##  <a name="cut"></a>  CComboBox::Cut

Удаляет (порезов), текущее выделение, если таковой имеется, в поле со списком ввода, управления и копирует удаленный текст в буфер обмена в формате CF_TEXT.

```
void Cut();
```

### <a name="remarks"></a>Примечания

Чтобы удалить текущее выделение, не помещая удаляемый текст в буфер обмена, вызовите [Очистить](#clear) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

##  <a name="deleteitem"></a>  CComboBox::DeleteItem

Вызывается платформой, когда пользователь удаляет элемент из рисуемого владельцем `CComboBox` объекта или уничтожает поле со списком.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDeleteItemStruct*<br/>
Длинный указатель на Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) структуру, содержащую сведения о удаляемого элемента. См. в разделе [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) описание этой структуры.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для перерисовки поле со списком, при необходимости.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

##  <a name="deletestring"></a>  CComboBox::DeleteString

Удаляет элемент в позиции *nIndex* из поля со списком.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает индекс строки, который требуется удалить.

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, то это количество строк, оставшихся в списке. Если возвращаемое значение равно CB_ERR *nIndex* указывает индексом большим, чем число элементов в списке.

### <a name="remarks"></a>Примечания

Все элементы, следующие *nIndex* теперь перейти на одну позицию вниз. Например если поле со списком содержит два элемента, удаление первого элемента приведет к оставшиеся элемент теперь на первом месте. *nIndex*= 0 в первой позиции элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

##  <a name="dir"></a>  CComboBox::Dir

Добавляет список имен файлов или дисков в поле списка поля со списком.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Параметры

*attr*<br/>
Может быть любым сочетанием **перечисления** значений описано в разделе [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) или любое сочетание следующих значений:

- Файл DDL_READWRITE можно чтение и запись.

- DDL_READONLY файл может быть считываться, но не записываются.

- DDL_HIDDEN файл является скрытым и не отображается в каталоге.

- DDL_SYSTEM файл является системным.

- Имя, указанное в DDL_DIRECTORY *lpszWildCard* указывает каталог.

- DDL_ARCHIVE файл помещен в архив.

- DDL_DRIVES включают все диски, которые соответствуют именем, указанным *lpszWildCard*.

- Эксклюзивные DDL_EXCLUSIVE флаг. Если флаг exclusive, перечислены только файлы указанного типа. В противном случае файлы указанного типа, перечислены в дополнение к файлам «normal».

*lpszWildCard*<br/>
Указывает строку спецификация файла. Строка может содержать подстановочные знаки (например, *.\*).

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, это отсчитываемый от нуля индекс последнего имени файла, добавляемого в список. Возвращает значение CB_ERR при возникновении ошибки; Возвращаемое значение является CB_ERRSPACE, если недостаточно места для хранения новых строк.

### <a name="remarks"></a>Примечания

Эта функция не поддерживается Windows `ComboBoxEx` элемента управления. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/desktop/Controls/comboboxex-controls) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

##  <a name="drawitem"></a>  CComboBox::DrawItem

Вызывается платформой при изменении внешнего вида рисуемого владельцем поле со списком поля изменится.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе документа требуется.

### <a name="remarks"></a>Примечания

`itemAction` Членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. См. в разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание этой структуры.

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CComboBox` объекта. Перед завершением работы эта функция-член, приложение должно восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

##  <a name="findstring"></a>  CComboBox::FindString

Находит, но не выделяет первой строки, которая содержит указанный префикс в списке поля со списком.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит отсчитываемый от нуля индекс элемента перед первым элементом для поиска. Когда достигается конец списка, он продолжает в верхней части списка обратно элемент, заданный параметром *nStartAfter*. Если значение-1, поле со списком всего выполняется поиск с самого начала.

*lpszString*<br/>
Указатель на заканчивающуюся нулем строку, содержащая префикс для поиска. Поиск является независимым, регистр, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение больше или равно 0, это начинающийся с нуля индекс элемента сопоставления. Это CB_ERR, если поиск завершился неудачей.

### <a name="remarks"></a>Примечания

Эта функция не поддерживается Windows `ComboBoxEx` элемента управления. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/desktop/Controls/comboboxex-controls) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

##  <a name="findstringexact"></a>  CComboBox::FindStringExact

Вызовите `FindStringExact` функции-члена для поиска первого списка строки (в поле со списком), соответствующую строку, указанную в *lpszFind*.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Параметры

*nIndexStart*<br/>
Указывает отсчитываемый от нуля индекс элемента перед первым элементом для поиска. Когда достигается конец списка, он продолжает в верхней части списка обратно элемент, заданный параметром *nIndexStart*. Если *nIndexStart* равно -1, поле со списком всего осуществляется с самого начала.

*lpszFind*<br/>
Указатель на заканчивающуюся нулем строку для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не учитывается регистр, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс, соответствующий элемент или CB_ERR, если поиск завершился неудачей.

### <a name="remarks"></a>Примечания

Если поле со списком был создан с помощью стиле рисуемый владельцем, но без [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, `FindStringExact` пытается сопоставить двойное значение на соответствие значению из *lpszFind*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

##  <a name="getcomboboxinfo"></a>  CComboBox::GetComboBoxInfo

Возвращает сведения о `CComboBox` объекта.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Параметры

*pcbi*<br/>
Указатель на [COMBOBOXINFO](/windows/desktop/api/winuser/ns-winuser-tagcomboboxinfo) структуры.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности [CB_GETCOMBOBOXINFO](/windows/desktop/Controls/cb-getcomboboxinfo) сообщения, как описано в пакете Windows SDK.

##  <a name="getcount"></a>  CComboBox::GetCount

Вызовите эту функцию-член для получения числа элементов в списке части поле со списком.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов. Количество возвращаемых результатов является один больше, чем значение индекса последнего элемента (индекс начинается с нуля). Это CB_ERR, если произошла ошибка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

##  <a name="getcuebanner"></a>  CComboBox::GetCueBanner

Возвращает текст подсказки, отображаемый для элемента управления поля со списком.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszText*|[out] Указатель на буфер, получающий текст баннера подсказки.|
|*cchText*|[in] Размер буфера, *lpszText* указывает параметр.|

### <a name="return-value"></a>Возвращаемое значение

В первой перегрузке [CString](../../atl-mfc-shared/using-cstring.md) , содержащий текст баннера подсказки, если он существует; в противном случае `CString` объект, который имеет нулевую длину.

- или -

Во второй перегрузке значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Текст подсказки является запрос, который отображается в области ввода поле со списком. Текст подсказки отображается, пока пользователь не предоставит входных данных.

Этот метод отправляет [CB_GETCUEBANNER](/windows/desktop/Controls/cb-getcuebanner) сообщения, который описан в пакете Windows SDK.

##  <a name="getcursel"></a>  CComboBox::GetCurSel

Вызывайте эту функцию члена, чтобы определить, какой элемент в поле со списком выбран.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс выбранного элемента в окне списка, поле со списком или CB_ERR, если элемент не выбран.

### <a name="remarks"></a>Примечания

`GetCurSel` Возвращает индекс в списке.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

##  <a name="getdroppedcontrolrect"></a>  CComboBox::GetDroppedControlRect

Вызовите `GetDroppedControlRect` функция-член для извлечения координаты на экране отображается (удалены) поле с раскрывающимся списком.

```
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Параметры

*lprect*<br/>
Указывает на [структура RECT](../../mfc/reference/rect-structure1.md) который используется для отправки координаты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

##  <a name="getdroppedstate"></a>  CComboBox::GetDroppedState

Вызовите `GetDroppedState` функция-член в списке, выберите в раскрывающемся поле со списком является ли видимой (раскрыл).

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если поле со списком является видимым. в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

##  <a name="getdroppedwidth"></a>  CComboBox::GetDroppedWidth

Вызывайте эту функцию для получения Минимальный допустимый ширину в пикселях для списка поля со списком поле со списком.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения Минимальная допустимая ширина в пикселях; в противном случае CB_ERR.

### <a name="remarks"></a>Примечания

Эта функция применяется только для полей со списком [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля.

По умолчанию минимальную допустимую ширину поле с раскрывающимся списком равно 0. Минимальная допустимая ширина задаются путем вызова [SetDroppedWidth](#setdroppedwidth). При отображении списка часть поля со списком, ширина больше минимальную допустимую ширину или ширина поля со списком.

### <a name="example"></a>Пример

  См. в примере [SetDroppedWidth](#setdroppedwidth).

##  <a name="geteditsel"></a>  CComboBox::GetEditSel

Возвращает позиции символов начала и конца текущего выделения в элементе управления списком.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

32-разрядное значение, содержащее начальную позицию в младшее слово и позицию первого символа невыбранные после окончания выделения в старшее слово. Если эта функция используется в поле со списком без элемента управления, возвращается CB_ERR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

##  <a name="getextendedui"></a>  CComboBox::GetExtendedUI

Вызовите `GetExtendedUI` функция-член для определения, имеет ли поле со списком пользовательского интерфейса по умолчанию или расширенный пользовательский интерфейс.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если поле со списком имеет расширенный пользовательский интерфейс; в противном случае 0.

### <a name="remarks"></a>Примечания

Расширенный пользовательский интерфейс может быть идентифицирована одним из следующих способов.

- Щелкните статический элемент управления отображает список только для полей со списком [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля.

- Нажатие клавиши Стрелка вниз отображает поле со списком (F4 отключена).

Прокрутка в статического элемента управления остается недоступной, если список элементов не является видимым (стрелка ключи отключены).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

##  <a name="gethorizontalextent"></a>  CComboBox::GetHorizontalExtent

Извлекает из поля со списком ширину в пикселях, по которым части списка в поле со списком может прокручиваться по горизонтали.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прокручиваемые ширина части списка в поле со списком в пикселях.

### <a name="remarks"></a>Примечания

Это применимо только в том случае, если часть списка в поле со списком имеет горизонтальную полосу прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

##  <a name="getitemdata"></a>  CComboBox::GetItemData

Извлекает значение 32-разрядных предоставляемую приложением, связанный с элементом указанного поле со списком.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс элемента в поле со списком «список».

### <a name="return-value"></a>Возвращаемое значение

Значение 32-разрядной, связанное с элементом, или CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

32-разрядное значение можно задать *dwItemData* параметр [SetItemData](#setitemdata) вызова функции-члена. Используйте `GetItemDataPtr` функция-член, если указатель является 32-разрядное значение извлекаемого (**void** <strong>\*</strong>).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

##  <a name="getitemdataptr"></a>  CComboBox::GetItemDataPtr

Извлекает значение 32-разрядных предоставляемую приложением, связанный с элементом указанного поле со списком как указатель (**void** <strong>\*</strong>).

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс элемента в поле со списком «список».

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель или значение -1, если произошла ошибка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

##  <a name="getitemheight"></a>  CComboBox::GetItemHeight

Вызовите `GetItemHeight` функция-член для извлечения высота элементов списка в поле со списком.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Задает компонент прокрутки на поля со списком, высота которого которой требуется извлечь. Если *nIndex* параметра равно -1, извлекается высоту элемента управления редактирования (или статического текста) часть поля со списком. Если у поля со списком [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, *nIndex* указывает отсчитываемый от нуля индекс элемента списка, высота которого которой требуется извлечь. В противном случае *nIndex* должно быть равным 0.

### <a name="return-value"></a>Возвращаемое значение

Высота в пикселях указанного элемента в поле со списком. Возвращает значение CB_ERR при возникновении ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

##  <a name="getlbtext"></a>  CComboBox::GetLBText

Получает строку из списка поля со списком.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс списка строки для копирования.

*lpszText*<br/>
Указывает на буфер, который принимает строку. Буфер должен иметь достаточно места для строки и знак завершения null.

*rString*<br/>
Ссылка на `CString`.

### <a name="return-value"></a>Возвращаемое значение

Длина строки, за исключением завершающего нуль-символа (в байтах). Если *nIndex* не указывает допустимый индекс, возвращаемым значением является CB_ERR.

### <a name="remarks"></a>Примечания

Вторая форма этого члена функции заливки `CString` с текстом элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

##  <a name="getlbtextlen"></a>  CComboBox::GetLBTextLen

Получает длину строки в списке поля со списком.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс строки списка.

### <a name="return-value"></a>Возвращаемое значение

Длина строки в байтах, за исключением завершающего нуль-символа. Если *nIndex* не указывает допустимый индекс, возвращаемым значением является CB_ERR.

### <a name="example"></a>Пример

  См. в примере [CComboBox::GetLBText](#getlbtext).

##  <a name="getlocale"></a>  CComboBox::GetLocale

Извлекает локали, используемой в поле со списком.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение идентификатора (LCID) языка для строк в поле со списком.

### <a name="remarks"></a>Примечания

Языковой стандарт используется, например, для определения порядка сортировки строк в отсортированном со списком.

### <a name="example"></a>Пример

  См. в примере [CComboBox::SetLocale](#setlocale).

##  <a name="getminvisible"></a>  CComboBox::GetMinVisible

Получает минимальное число видимых элементов в раскрывающемся списке текущего элемента управления поля со списком.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное число видимых элементов в текущем списке раскрывающегося списка.

### <a name="remarks"></a>Примечания

Этот метод отправляет [CB_GETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible) сообщения, который описан в пакете Windows SDK.

##  <a name="gettopindex"></a>  CComboBox::GetTopIndex

Возвращает отсчитываемый от нуля индекс первой видимой позиции в списке части поля со списком.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первой видимой позиции в списке части поля со списком в случае успешного выполнения CB_ERR в противном случае.

### <a name="remarks"></a>Примечания

Первоначально элемент 0 — в верхней части списка, но если поле со списком прокрутку, еще один элемент может быть в верхней.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

##  <a name="initstorage"></a>  CComboBox::InitStorage

Выделяет память для хранения элементов списка в списке части поля со списком.

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

В случае успешного выполнения максимальное количество элементов, которые могут хранить часть поля со списком, списков перед выделением памяти при необходимости, в противном случае CB_ERRSPACE, то не хватает памяти.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию перед добавлением большое число элементов в списке часть `CComboBox`.

Windows 95/98 только: *wParam* ограничен 16-разрядных значений. Это означает, что списки с множественным не может содержать более 32 767 элементы. Несмотря на то, что количество элементов является ограниченным, общий размер элементов в поле со списком ограничено только объемом доступной памяти.

Эта функция помогает ускорить инициализации списка полей, имеющих большое количество элементов (более 100). Он выделяет указанный объем памяти, чтобы последующие [AddString](#addstring), [InsertString](#insertstring), и [Dir](#dir) функции принимают кратчайшие сроки. Оценки можно использовать для параметров. Если вы пересмотреть, выделения дополнительной памяти; Если вы недооцените требования, обычного выделения используется для элементов, которые вычитаются из суммы предварительно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

##  <a name="insertstring"></a>  CComboBox::InsertString

Вставляет строку в список поля со списком.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс позиции в списке, в которую будет вставлена строка. Если этот параметр имеет значение -1, строка добавляется в конец списка.

*lpszString*<br/>
Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. Возвращает значение CB_ERR при возникновении ошибки. Возвращаемое значение является CB_ERRSPACE, если недостаточно места для хранения новой строки.

### <a name="remarks"></a>Примечания

В отличие от функции-члена [AddString](#addstring) , функция-член `InsertString` не вызывает сортировку списка со стилем [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

> [!NOTE]
>  Эта функция не поддерживается Windows `ComboBoxEx` элемента управления. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/desktop/Controls/comboboxex-controls) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

##  <a name="limittext"></a>  CComboBox::LimitText

Ограничивает длину в байтах текст, который пользователь может ввести в поле ввода поля со списком.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Параметры

*nMaxChars*<br/>
Задает длину (в байтах), пользователь может ввести текст. Если этот параметр равен 0, длина текста устанавливается до 65 535 байт.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, при успешном выполнении. При вызове для поле со списком в стиле [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или для поля со списком без элемента управления, возвращается значение CB_ERR.

### <a name="remarks"></a>Примечания

Если поле со списком имеет стиль [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles), ограничение еще больше, чем размер элемента управления редактирования текста не окажет никакого воздействия.

`LimitText` ограничивает только текст, который пользователь может ввести. Он не влияет на любой текст уже в элементе управления при отправке сообщения, а также влияет на длину текста, копируются в элемент управления редактирования, при выборе строки в поле со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

##  <a name="measureitem"></a>  CComboBox::MeasureItem

Вызывается платформой, когда создается поле со списком в стиле рисуемого владельцем.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpMeasureItemStruct*<br/>
Длинный указатель на [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования поле Windows измерений списка в поле со списком. Если поле со списком создается с помощью [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, платформа вызывает эту функцию-член для каждого элемента в поле со списком. В противном случае этот член вызывается только один раз.

Использование стилей CBS_OWNERDRAWFIXED в поле со списком пользовательской отрисовки, созданных в [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) функцию-член `CWnd` включает в себя вопросы дальнейшей программирования. См. в обсуждении [14 технических Примечание](../../mfc/tn014-custom-controls.md).

См. в разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

##  <a name="paste"></a>  CComboBox::Paste

Вставляет данные из буфера обмена в поле ввода поля со списком в текущей позиции курсора.

```
void Paste();
```

### <a name="remarks"></a>Примечания

Данные вставляются только в том случае, если буфер обмена содержит данные в формате CF_TEXT.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

##  <a name="resetcontent"></a>  CComboBox::ResetContent

Удаляет все элементы из списка, поле и элемент управления списком.

```
void ResetContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

##  <a name="selectstring"></a>  CComboBox::SelectString

Выполняет поиск строки в списке поля со списком и если строка найдена, выбирает строки в поле со списком и копирует его в элемент управления редактирования.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит отсчитываемый от нуля индекс элемента перед первым элементом для поиска. Когда достигается конец списка, он продолжает в верхней части списка обратно элемент, заданный параметром *nStartAfter*. Если значение-1, поле со списком всего выполняется поиск с самого начала.

*lpszString*<br/>
Указатель на заканчивающуюся нулем строку, содержащая префикс для поиска. Поиск является независимым, регистр, поэтому эта строка может содержать любое сочетание прописных и строчных букв.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс выбранного элемента, если строка была найдена. Если поиск завершился неудачей, возвращаемым значением является CB_ERR и текущего выделения не изменяется.

### <a name="remarks"></a>Примечания

Строка выбирается только в том случае, если его начальные символы (от начальной) соответствует символам в строке префикса.

Обратите внимание, что `SelectString` и `FindString` функции-члены как найти строку, но `SelectString` функция-член также выбирает строки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

##  <a name="setcuebanner"></a>  CComboBox::SetCueBanner

Задает текст подсказки, отображаемый для элемента управления поля со списком.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszText*|[in] Указатель на буфер нулевым байтом, который содержит текст подсказки.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Текст подсказки является запрос, который отображается в области ввода поле со списком. Текст подсказки отображается, пока пользователь не предоставит входных данных.

Этот метод отправляет [CB_SETCUEBANNER](/windows/desktop/Controls/cb-setcuebanner) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная *m_combobox*, который используется для программного доступа к поле со списком. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Пример

В следующем примере кода задает баннер подсказки для элемента управления полем со списком.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="setcursel"></a>  CComboBox::SetCurSel

Выбирает строку в списке поля со списком.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Параметры

*Выберите*<br/>
Указывает отсчитываемый от нуля индекс строки для выбора. Если значение -1, любое текущее выделение в поле со списком удаляется и очищается поле ввода.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента, выбранного при успешном выполнении сообщения. Возвращает значение CB_ERR Если *выберите* больше, чем число элементов в списке или, если *выберите* устанавливается равным -1, которая очищает выделение.

### <a name="remarks"></a>Примечания

При необходимости, поле со списком прокрутке строки (Если отображается поле со списком). Текст в элементе управления списком изменяется для отражения нового выделения. Предыдущее выделение в поле со списком удаляется.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

##  <a name="setdroppedwidth"></a>  CComboBox::SetDroppedWidth

Вызывайте эту функцию, чтобы задать минимальную допустимую ширину, в пикселях для списка поля со списком поле со списком.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Минимальную ширину части списка в поле со списком в пикселях.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения новая ширина окна списка, в противном случае CB_ERR.

### <a name="remarks"></a>Примечания

Эта функция применяется только для полей со списком [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля.

По умолчанию минимальную допустимую ширину поле с раскрывающимся списком равно 0. При отображении списка часть поля со списком, ширина больше минимальную допустимую ширину или ширина поля со списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

##  <a name="seteditsel"></a>  CComboBox::SetEditSel

Выбирает символы в элементе управления списком.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Параметры

*nStartChar*<br/>
Определяет начальную позицию. Если начальная позиция имеет значение -1, удаляется любого существующего выделения.

*nEndChar*<br/>
Задает конечное положение. Если конечная позиция имеет значение -1, затем весь текст от начальной позиции до последнего символа в элементе управления будет выбрана.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция-член выполнено успешно; в противном случае 0. Если это CB_ERR `CComboBox` имеет [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля или не имеет поле со списком.

### <a name="remarks"></a>Примечания

Позиции отсчитываются от нуля. Чтобы выбрать первый символ в элемент управления редактирования, необходимо указать начальную позицию 0. Конечная позиция — для символа сразу после последнего символа для выбора. Например чтобы выбрать первые четыре символа элемента управления, используется начальная позиция 0 и конечной позициями 4.

> [!NOTE]
>  Эта функция не поддерживается Windows `ComboBoxEx` элемента управления. Дополнительные сведения об этом элементе управления см. в разделе [элементы управления ComboBoxEx](/windows/desktop/Controls/comboboxex-controls) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CComboBox::GetEditSel](#geteditsel).

##  <a name="setextendedui"></a>  CComboBox::SetExtendedUI

Вызовите `SetExtendedUI` функция-член можно выбрать пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс для поле со списком, который имеет [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Параметры

*bExtended*<br/>
Указывает, следует ли использовать поле со списком, расширенный пользовательский интерфейс или пользовательский интерфейс по умолчанию. Значение TRUE выбирает Расширенный пользовательский интерфейс; значение FALSE выбирает стандартный пользовательский интерфейс.

### <a name="return-value"></a>Возвращаемое значение

CB_OKAY, если операция выполнена успешно, или CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Расширенный пользовательский интерфейс может быть идентифицирована одним из следующих способов.

- Щелкните статический элемент управления отображает список только для полей со списком в стиле CBS_DROPDOWNLIST.

- Нажатие клавиши Стрелка вниз отображает поле со списком (F4 отключена).

Прокрутка в статический элемент управления отключен, если в списке элементов не отображается (отключены клавиш со стрелками).

### <a name="example"></a>Пример

  См. в примере [CComboBox::GetExtendedUI](#getextendedui).

##  <a name="sethorizontalextent"></a>  CComboBox::SetHorizontalExtent

Задает ширину в пикселях, по которым части списка в поле со списком может прокручиваться по горизонтали.

```
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Параметры

*nExtent*<br/>
Задает количество пикселей, на которое части списка в поле со списком может прокручиваться по горизонтали.

### <a name="remarks"></a>Примечания

Если ширина поля меньше, чем это значение, горизонтальной полосы прокрутки по горизонтали прокручивается элементов в поле со списком. Если ширина окна списка равно или больше, чем это значение, горизонтальная полоса прокрутки является скрытым или, если у поля со списком [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, отключен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

##  <a name="setitemdata"></a>  CComboBox::SetItemData

Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс элемента для задания.

*dwItemData*<br/>
Содержит новое значение, связываемое с элементом.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Используйте `SetItemDataPtr` функция-член Если 32-разрядных элемент должен быть указателем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

##  <a name="setitemdataptr"></a>  CComboBox::SetItemDataPtr

Задает 32-разрядное значение, связанное с указанным элементом в поле со списком, чтобы быть заданный указатель (**void** <strong>\*</strong>).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс для элемента.

*pData*<br/>
Содержит указатель, чтобы связать с элементом.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Этот указатель остается допустимым в течение жизненного цикла поле со списком, несмотря на то, что относительное положение элемента в поле со списком может измениться, как добавляются или удаляются элементы. Таким образом можно изменить индекс элемента в списке, но указатель остается надежной.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

##  <a name="setitemheight"></a>  CComboBox::SetItemHeight

Вызовите `SetItemHeight` функцию-член для установите высоту элементов списка в поле со списком или высоту элемента управления редактирования (или статического текста) часть поле со списком.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает, установлен ли высота элементов списка или высоту элемента управления редактирования (или статического текста) часть поля со списком.

Если у поля со списком [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, *nIndex* указывает отсчитываемый от нуля индекс элемента списка, высота которого должен быть установлен, в противном случае, *nIndex* должно быть равно 0 и задаст высоту всех элементов списка.

Если *nIndex* является -1, высота элемента управления редактированием или статического текста часть поля со списком задать.

*cyItemHeight*<br/>
Указывает высоту в пикселях компонент поле со списком *nIndex*.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR, если индекс или высота является недопустимым; в противном случае 0.

### <a name="remarks"></a>Примечания

Высота элемента управления редактирования (или статического текста) часть поля со списком задается независимо от высоты элементов списка. Приложения необходимо убедиться, что высота этой части элемента управления редактирования (или статического текста) не меньше, чем высота элемента определенного списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

##  <a name="setlocale"></a>  CComboBox::SetLocale

Задает идентификатор языкового стандарта для этого поля со списком.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Параметры

*nNewLocale*<br/>
Новое значение языкового стандарта идентификатор (LCID), чтобы задать для поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение языкового стандарта код (LCID) для этого поля со списком.

### <a name="remarks"></a>Примечания

Если `SetLocale` не вызывается, значение по умолчанию языкового стандарта, полученная от системы. Этот язык системы по умолчанию можно изменить с помощью панели управления Язык и International.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

##  <a name="setminvisibleitems"></a>  CComboBox::SetMinVisibleItems

Задает минимальное число видимых элементов в раскрывающемся списке текущего поля со списком.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iMinVisible*|[in] Указывает минимальное число видимых элементов.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [CB_SETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная *m_combobox*, который используется для программного доступа к поле со списком. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Пример

В следующем примере кода вставляет 20 элементов в списке выберите в раскрывающемся поле со списком. Затем он указывает, что как минимум 10 элементов отображаться при нажатии клавиши со стрелкой раскрывающегося списка.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="settopindex"></a>  CComboBox::SetTopIndex

Гарантирует, что какой-либо элемент отображается в списке части поля со списком.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает отсчитываемый от нуля индекс элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или CB_ERR при возникновении ошибки.

### <a name="remarks"></a>Примечания

Система прокручивает поле со списком до элемента, заданного посредством *nIndex* отображается в верхней части списка поля или диапазона Максимальная прокрутка был достигнут.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

##  <a name="showdropdown"></a>  CComboBox::ShowDropDown

Показывает или скрывает элемент в списке поле со списком, который имеет [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля.

```
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Параметры

*bShowIt*<br/>
Указывает, является ли поле с раскрывающимся списком, чтобы отображать и скрывать. Значение TRUE показывает поле со списком. Значение FALSE скрывает поле со списком.

### <a name="remarks"></a>Примечания

По умолчанию поле со списком, в котором этот стиль будет отображать поле со списком.

Эта функция-член не оказывает влияния на поле со списком, созданных с помощью [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля.

### <a name="example"></a>Пример

  См. в примере [CComboBox::GetDroppedState](#getdroppedstate).

## <a name="see-also"></a>См. также

[Пример MFC CTRLBARS](../../visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
