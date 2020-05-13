---
title: Класс CComboBox
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
ms.openlocfilehash: dc803fb4ce137b256f4197afaec7bc3327e1e85a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754829"
---
# <a name="ccombobox-class"></a>Класс CComboBox

Предоставляет функции поля со списком Windows.

## <a name="syntax"></a>Синтаксис

```
class CComboBox : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|Формирует объект `CComboBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|Добавляет строку к концу списка в поле списка комбо-бокса или в отсортированном положении для коробок с CBS_SORT.|
|[CComboBox::Clear](#clear)|Удаляет (очищает) текущий выбор, если такового имеется, в элементе управления отсеиваний.|
|[CComboBox::CompareItem](#compareitem)|Вызывается по фреймворку, чтобы определить относительное положение нового элемента списка в отсортированном нарисованном владельцем комбо-коробке.|
|[CComboBox::Copy](#copy)|Копирует текущий выбор, если таковой имеется, на Clipboard в CF_TEXT формате.|
|[CComboBox::Создание](#create)|Создает комбо-коробку и прикрепляет ее к объекту. `CComboBox`|
|[CComboBox::Cut](#cut)|Удаляет (вырезает) текущий выбор, если таковой имеется, в элементе управления редактированием и копирует удаленный текст на CF_TEXT формате.|
|[CComboBox::DeleteItem](#deleteitem)|Вызывается по системе, когда элемент списка удаляется из нарисованного владельцем комбо-окна.|
|[CComboBox::DeleteString](#deletestring)|Удаляет строку из ящика списка комбо-бокса.|
|[CComboBox::Dir](#dir)|Добавляет список имен файлов в поле списка комбо-бокса.|
|[CComboBox::DrawItem](#drawitem)|Вызывается рамки, когда визуальный аспект владельца обращается комбо окно изменения.|
|[CComboBox::FindString](#findstring)|Находит первую строку, содержащую указанную префиксу, в поле списка комбо-бокса.|
|[CComboBox::FindStringExact](#findstringexact)|Находит первую строку списка-коробки (в комбо-коробке), которая соответствует указанной строке.|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Извлекает информацию `CComboBox` об объекте.|
|[CComboBox::GetCount](#getcount)|Получает количество элементов в поле списка комбо-коробки.|
|[CComboBox::GetCueBanner](#getcuebanner)|Получает текст сигнала, который отображается для управления комбо-боксом.|
|[CComboBox::GetCurSel](#getcursel)|Извлекает индекс выбранного в настоящее время элемента, если таковой имеется, в поле списка комбо-бокса.|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Извлекает на экран координаты видимого (упавого) ящика списка выпадающих комбо-боксов.|
|[CComboBox::GetDroppedState](#getdroppedstate)|Определяет, видна ли поле списка выпадающих комбо-боксов (упало).|
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Получает минимальную разрешенную ширину для выпадающих вниз список-коробка часть комбо-бокс.|
|[CComboBox::GetEditSel](#geteditsel)|Получает начальные и заканчивающиеся позиции персонажей текущего выбора в управлении редактированием комбо-коробки.|
|[CComboBox::GetExtendedUI](#getextendedui)|Определяет, имеет ли комбо-бокс пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс.|
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пиксели, которые часть комбо-коробки можно прокрутить горизонтально.|
|[CComboBox::GetItemData](#getitemdata)|Извлекает 32-битное значение, поставляемое приложением, связанное с указанным комбо-коробкой.|
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Извлекает 32-битный указатель, поставляемый приложением, который связан с указанным комбо-коробкой.|
|[CComboBox::GetItemHeight](#getitemheight)|Извлекает высоту элементов списка в комбо-коробке.|
|[CComboBox::GetLBText](#getlbtext)|Получает строку из списка поле комбо-бокс.|
|[CComboBox::GetLBTextLen](#getlbtextlen)|Получает длину строки в листе поле комбо-бокс.|
|[CComboBox::GetLocale](#getlocale)|Извлекает идентификатор локализации для комбо-коробки.|
|[CComboBox::GetMinVisible](#getminvisible)|Получает минимальное количество видимых элементов в списке выпадающих в настоящее время комбо-бокс.|
|[CComboBox::GetTopIndex](#gettopindex)|Возвращает индекс первого видимого элемента в части комбо-коробки.|
|[CComboBox::InitStorage](#initstorage)|Предраспределяет блоки памяти для элементов и строк в лист-бокс часть комбо-бокс.|
|[CComboBox::InsertString](#insertstring)|Вставляет строку в список поля со списком.|
|[CComboBox::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в управление редактированием комбо-коробки.|
|[CComboBox::MeasureItem](#measureitem)|Вызывается рамки для определения размеров комбо-коробки при создании нарисованной владельцем комбо-коробки.|
|[CComboBox::Paste](#paste)|Вставляет данные из Clipboard в элемент управления правки в текущем положении курсора. Данные вставляются только в том случае, если Clipboard содержит данные в CF_TEXT формате.|
|[CComboBox::ResetContent](#resetcontent)|Удаляет все элементы из коробки списка и отодевать управление комбо-коробкой.|
|[CComboBox::SelectString](#selectstring)|Поиск строки в поле списка комбо-боксии и, если строка найдена, выбирает строку в поле списка и копирует строку для управления отсеивательством.|
|[CComboBox::SetCueBanner](#setcuebanner)|Устанавливает текст сигнала, который отображается для управления комбо-коробкой.|
|[CComboBox::SetCurSel](#setcursel)|Выбирает строку в поле списка комбо-бокса.|
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Устанавливает минимальную разрешенную ширину для выпадающей части комбо-бокса.|
|[CComboBox::SetEditSel](#seteditsel)|Выбирает символы в управлении редактированием комбо-коробки.|
|[CComboBox::SetExtendedUI](#setextendedui)|Выбирает либо пользовательский интерфейс по умолчанию, либо расширенный пользовательский интерфейс для комбо-бокса, который имеет CBS_DROPDOWN или CBS_DROPDOWNLIST стиль.|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Устанавливает ширину в пиксели, что список коробки часть комбо-бокс может быть прокрутка горизонтально.|
|[CComboBox::SetItemData](#setitemdata)|Устанавливает 32-битное значение, связанное с указанным элементом, в комбо-коробке.|
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Устанавливает 32-битный указатель, связанный с указанным элементом, в комбо-коробке.|
|[CComboBox::SetItemHeight](#setitemheight)|Устанавливает высоту элементов списка в комбо-коробке или высоту редактирования-контроля (или статического текста) часть комбо-коробки.|
|[CComboBox::SetLocale](#setlocale)|Устанавливает идентификатор локализации для комбо-коробки.|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Устанавливает минимальное количество видимых элементов в списке выпадающих в текущем комбо-поле.|
|[CComboBox::SetTopIndex](#settopindex)|Сообщает часть комбо-коробки для отображения элемента с указанным индексом в верхней части.|
|[CComboBox::ShowDropDown](#showdropdown)|Показывает или скрывает список поле комбо-бокс, который имеет CBS_DROPDOWN или CBS_DROPDOWNLIST стиле.|

## <a name="remarks"></a>Remarks

Комбо-коробка состоит из ящика списка в сочетании со статическим управлением или управлением отсвакой. Часть элемента управления в листе-коробке может отображаться в любое время или может упасть только тогда, когда пользователь выбирает стрелку выпадения рядом с элементом управления.

Выбранный в настоящее время элемент (если таков) в поле списка отображается в элементе управления статикой или элементе отсваза. Кроме того, если комбо-бокс имеет стиль выпадающего списка, пользователь может ввести начальный символ одного из элементов в списке, а поле списка, если его видно, выделит следующий элемент с этим исходным символом.

В следующей таблице сравниваются три [стиля](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)комбо-бокса.

|Стиль|Когда отображается поле списка|Статический или элементатический контроль|
|-----------|-------------------------------|-----------------------------|
|Простая|Всегда|Изменить|
|Drop-down|При падении вниз|Изменить|
|Раскрывающийся список|При падении вниз|Статические|

Вы можете `CComboBox` создать объект из шаблона диалога или непосредственно в коде. В обоих случаях сначала `CComboBox` позвоните `CComboBox` в конструктор, чтобы построить объект; затем вызов функции члена [Создать](#create) для создания `CComboBox` элемента управления и прикрепить его к объекту.

Если вы хотите обрабатывать сообщения уведомлений Windows, отправленные комбо-коробкой его родителю (обычно классу, полученному из), `CDialog`добавьте запись на карту сообщений и функцию обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись на карту сообщений принимает следующую форму:

**НА\_**_Уведомление_ **(id** _id_, _memberFxn_ **)**

где `id` указывается идентификатор окна ребенка управления комбо-боксом отправки уведомления и `memberFxn` имя функции родительского члена, написанной для обработки уведомления.

Прототип функции родителя:

**afx_msg** `void` afx_msg `memberFxn` **();**

Порядок отправки определенных уведомлений не может быть предсказан. В частности, уведомление о CBN_SELCHANGE может произойти либо до, либо после CBN_CLOSEUP уведомления.

Потенциальные записи на карту сообщений:

- ON_CBN_CLOSEUP (Windows 3.1 и более поздний срок). Коробка списка комбо-бокса закрылась. Это сообщение о уведомлении не отправляется для комбо-бокса, который имеет [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль.

- ON_CBN_DBLCLK Пользователь дважды щелкает строку в коробке списка комбо-коробки. Это сообщение уведомления отправляется только для комбо-бокса со стилем CBS_SIMPLE. Для комбо-бокса со [стилем CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST,](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) двойной клик не может произойти, потому что одним щелчком мыши скрывается список поле.

- ON_CBN_DROPDOWN В поле списка комбо-бокс вот-вот упадет (будет сделано видимым). Это сообщение уведомления может произойти только для комбо-бокса со стилем CBS_DROPDOWN или CBS_DROPDOWNLIST.

- ON_CBN_EDITCHANGE Пользователь предпринял действие, которое, возможно, изменило текст в части управления редактированием комбо-коробки. В отличие от сообщения CBN_EDITUPDATE, это сообщение отправляется после обновления экрана Windows. Он не отправляется, если комбо-бокс имеет CBS_DROPDOWNLIST стиль.

- ON_CBN_EDITUPDATE Часть управления редактированием комбо-коробки вот-вот отображает измененный текст. Это сообщение уведомления отправляется после того, как элемент управления отформатировал текст, но прежде чем он отобразит текст. Он не отправляется, если комбо-бокс имеет CBS_DROPDOWNLIST стиль.

- ON_CBN_ERRSPACE Комбо-бокс не может выделить достаточно памяти для удовлетворения конкретного запроса.

- ON_CBN_SELENDCANCEL (Windows 3.1 и более поздний срок). Указывает на то, что выбор пользователя должен быть отменен. Пользователь нажимает на элемент, а затем нажимает другое окно или элемент управления, чтобы скрыть список поле комбо-бокс. Это сообщение уведомления отправляется до сообщения CBN_CLOSEUP уведомления, чтобы указать, что выбор пользователя должен быть проигнорирован. Сообщение CBN_SELENDCANCEL или CBN_SELENDOK уведомления отправляется, даже если сообщение CBN_CLOSEUP уведомления не отправлено (как в случае комбо-бокса со стилем CBS_SIMPLE).

- ON_CBN_SELENDOK Пользователь выбирает элемент, а затем либо нажимает клавишу ENTER или нажимает клавишу DOWN ARROW, чтобы скрыть окно списка комбо-бокса. Это сообщение уведомления отправляется до CBN_CLOSEUP сообщения, чтобы указать, что выбор пользователя должен считаться действительным. Сообщение CBN_SELENDCANCEL или CBN_SELENDOK уведомления отправляется, даже если сообщение CBN_CLOSEUP уведомления не отправлено (как в случае комбо-бокса со стилем CBS_SIMPLE).

- ON_CBN_KILLFOCUS Комбо-бокс теряет вхотоза.

- ON_CBN_SELCHANGE Выбор в поле списка комбо-бокса собирается быть измененв в результате того, что пользователь либо нажат в поле списка или изменит выбор с помощью клавиш со стрелками. При обработке этого сообщения текст в правке комбо-бокса `GetLBText` может быть извлечен только через другую аналогичную функцию. `GetWindowText`не может быть использован.

- ON_CBN_SETFOCUS Комбо-коробка получает вхотливую фокусировку.

При создании `CComboBox` объекта в диалоговом поле (через ресурс `CComboBox` диалога) объект автоматически уничтожается при закрытии диалогового окна.

Если вы встраите `CComboBox` объект в другой объект окна, вам не нужно его уничтожать. При создании `CComboBox` объекта в стеке он уничтожается автоматически. Если вы `CComboBox` создаете объект на куче с помощью **новой** функции, необходимо **вызвать удаление** объекта, чтобы уничтожить его, когда комбо-коробка Windows будет уничтожена.

**Заметка** Если вы хотите обрабатывать WM_KEYDOWN и WM_CHAR сообщения, вы должны подклассировать элементы управления элементами отработки и списка комбо-боксов, получить классы из `CEdit` и `CListBox`добавить обработчики для этих сообщений в выведенные классы. Для получения дополнительной информации [см. CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="ccomboboxaddstring"></a><a name="addstring"></a>CComboBox::AddString

Добавляет строку в поле списка комбо-коробки.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*lpszString*<br/>
Очки на нулевую строку, которая должна быть добавлена.

### <a name="return-value"></a>Возвращаемое значение

Если значение возврата больше или равно 0, это нулевой индекс строки в поле списка. Значение возврата CB_ERR если произошла ошибка; значение возврата CB_ERRSPACE при недостаточном пространстве для хранения новой строки.

### <a name="remarks"></a>Remarks

Если поле списка не было создано со [стилем CBS_SORT,](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) строка добавляется в конец списка. В противном случае строка вставляется в список, и список сортируется.

> [!NOTE]
> Эта функция не поддерживается `ComboBoxEx` управлением Windows. Для получения дополнительной информации об этом элементе управления, см [ComboBoxEx управления](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

Чтобы вставить строку в определенное место в списке, используйте функцию члена [InsertString.](#insertstring)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

## <a name="ccomboboxccombobox"></a><a name="ccombobox"></a>CComboBox::CComboBox

Формирует объект `CComboBox`.

```
CComboBox();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

## <a name="ccomboboxclear"></a><a name="clear"></a>CComboBox::Clear

Удаляет (очищает) текущий выбор, если такового имеется, в управлении комбо-боксом.

```cpp
void Clear();
```

### <a name="remarks"></a>Remarks

Чтобы удалить текущий выбор и поместить удаленное содержимое на Clipboard, используйте функцию участника [Cut.](#cut)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

## <a name="ccomboboxcompareitem"></a><a name="compareitem"></a>CComboBox::CompareItem

Вызывается по фреймворку, чтобы определить относительное положение нового элемента в части списка-коробки отсортированной комбо-коробки владельца-рисования.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Параметры

*lpCompareItemStruct*<br/>
Длинный указатель на структуру [COMPAREITEMSTRUCT.](/windows/win32/api/winuser/ns-winuser-compareitemstruct)

### <a name="return-value"></a>Возвращаемое значение

Указывает относительное положение двух элементов, описанных в структуре. `COMPAREITEMSTRUCT` В качестве такой точки может выступать любой из следующих вариантов:

|Значение|Значение|
|-----------|-------------|
|- 1|Пункт 1 имеет до пункта 2.|
|0|Пункт 1 и пункт 2 сортируют то же самое.|
|1|Пункт 1 разнослив после пункта 2.|

Смотрите [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) для `COMPAREITEMSTRUCT`описания .

### <a name="remarks"></a>Remarks

По умолчанию эта функция-член ничего не делает. При создании комбо-коробки владельца с LBS_SORT стилем необходимо переопределить эту функцию участника, чтобы помочь структуре в сортировке новых элементов, добавленных в поле списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

## <a name="ccomboboxcopy"></a><a name="copy"></a>CComboBox::Copy

Копирует текущий выбор, если таковые имеются, в правлении комбо-бокса на Clipboard в CF_TEXT формате.

```cpp
void Copy();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

## <a name="ccomboboxcreate"></a><a name="create"></a>CComboBox::Создание

Создает комбо-коробку и прикрепляет ее к объекту. `CComboBox`

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль комбо-коробки. Примените любую комбинацию [стилей комбо-бокса](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) к коробке.

*rect*<br/>
Указывает на положение и размер комбо-коробки. Может быть [структура RECT](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект.

*pParentWnd*<br/>
Определяет родительское окно комбо-коробки (обычно `CDialog`a). Она не должна быть NULL.

*nID*<br/>
Определяет идентификатор управления комбо-коробкой.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы строите `CComboBox` объект в два этапа. Во-первых, вызов конструктора, а затем вызов `Create`, который создает `CComboBox` окно комбо Windows и прикрепляет его к объекту.

При `Create` выполнении Windows отправляет [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_CREATE,](../../mfc/reference/cwnd-class.md#oncreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения в комбо-бокс.

Эти сообщения обрабатываются по умолчанию функциями участников [OnNcCreate,](../../mfc/reference/cwnd-class.md#onnccreate) [OnCreate,](../../mfc/reference/cwnd-class.md#oncreate) [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize) `CWnd` и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) в базовом классе. Чтобы расширить обработку сообщений по `CComboBox`умолчанию, вывемите класс из, добавьте карту сообщений в новый класс и переизуйте предыдущие функции обработчика сообщений. Переопределить, `OnCreate`например, для выполнения необходимой инициализации для нового класса.

Примените следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к управлению комбо-коробкой. :

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

- WS_VSCROLL Чтобы добавить вертикальную прокрутку для ящика списка в комбо-поле

- WS_HSCROLL Чтобы добавить горизонтальную прокрутку для ящика списка в комбо-поле

- WS_GROUP К управлению группой

- WS_TABSTOP Включить комбо-коробку в порядок табуирования

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

## <a name="ccomboboxcut"></a><a name="cut"></a>CComboBox::Cut

Удаляет (вырезает) текущий выбор, если таковой имеется, в элементе управления редактированием комбо-бокса и копирует удаленный текст на clipboard в CF_TEXT формате.

```cpp
void Cut();
```

### <a name="remarks"></a>Remarks

Чтобы удалить текущий выбор, не размещая удаленный текст на Clipboard, позвоните в функцию [участника Clear.](#clear)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

## <a name="ccomboboxdeleteitem"></a><a name="deleteitem"></a>CComboBox::DeleteItem

Вызывается по фрейму, когда пользователь удаляет `CComboBox` элемент из объекта, нарисоватого владельцем, или уничтожает комбо-бокс.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDeleteItemStruct*<br/>
Длинный указатель на структуру Windows [DELETEITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) содержащую информацию об удаленном элементе. Смотрите [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) для описания этой структуры.

### <a name="remarks"></a>Remarks

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределить эту функцию, чтобы перерисовать комбо-бокс по мере необходимости.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

## <a name="ccomboboxdeletestring"></a><a name="deletestring"></a>CComboBox::DeleteString

Удаляет элемент в позиции *nIndex* из комбо-коробки.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Устраняет индекс строки, которая должна быть удалена.

### <a name="return-value"></a>Возвращаемое значение

Если значение возврата больше или равно 0, то это количество строк, остающихся в списке. Значение возврата CB_ERR если *nIndex* определяет индекс, превышающее количество элементов в списке.

### <a name="remarks"></a>Remarks

Все элементы, следующие *за nIndex* теперь двигаться вниз по одной позиции. Например, если комбо-бокс содержит два элемента, то удаляние первого элемента приведет к тому, что оставшийся элемент окажется в первой позиции. *nIndex*No0 для элемента в первой позиции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

## <a name="ccomboboxdir"></a><a name="dir"></a>CComboBox::Dir

Добавляет список имен файлов или дисков в поле списка комбо-бокса.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Параметры

*Attr*<br/>
Может быть любое сочетание **значений,** описанных в [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) или любое сочетание следующих значений:

- DDL_READWRITE файл можно прочитать или написать.

- DDL_READONLY файл можно читать, но не писать.

- DDL_HIDDEN файл скрыт и не отображается в объявлении каталога.

- DDL_SYSTEM файл — это системный файл.

- DDL_DIRECTORY Название, указанное *lpszWildCard,* определяет каталог.

- DDL_ARCHIVE файл был заархивирован.

- DDL_DRIVES Включите все диски, которые соответствуют имени, указанному *lpszWildCard.*

- DDL_EXCLUSIVE эксклюзивный флаг. Если установлен эксклюзивный флаг, перечислены только файлы указанного типа. В противном случае файлы указанного типа перечислены в дополнение к "нормальным" файлам.

*lpszWildCard*<br/>
Указывает на строку спецификации файлов. Строка может содержать подстановочные\*знаки (например, З. ).

### <a name="return-value"></a>Возвращаемое значение

Если значение возврата больше или равно 0, это нулевой индекс последнего файла, добавленного в список. Значение возврата CB_ERR если произошла ошибка; значение возврата CB_ERRSPACE при недостаточном пространстве для хранения новых строк.

### <a name="remarks"></a>Remarks

Эта функция не поддерживается `ComboBoxEx` управлением Windows. Для получения дополнительной информации об этом элементе управления, см [ComboBoxEx управления](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

## <a name="ccomboboxdrawitem"></a><a name="drawitem"></a>CComboBox::DrawItem

Вызывается рамки, когда визуальный аспект владельца рисовать комбо окно изменения.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) содержащую информацию о типе требуемого чертежа.

### <a name="remarks"></a>Remarks

Член `itemAction` `DRAWITEMSTRUCT` структуры определяет действие чертежа, которое должно быть выполнено. Смотрите [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) для описания этой структуры.

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию элемента для `CComboBox` реализации чертежа для объекта владельца-рисования. Перед тем, как эта функция участника прекратится, приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста дисплея, поставляемого в *lpDrawItemStruct.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

## <a name="ccomboboxfindstring"></a><a name="findstring"></a>CComboBox::FindString

Находит, но не выбирает первую строку, которая содержит указанную префикс в поле списка комбо-бокса.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит нулевой индекс элемента перед поиском первого элемента. Когда поиск достигает нижней части окна списка, он продолжается от верхней части окна списка обратно к элементу, указанному *nStartAfter.* Если -1, весь список поле ищется с самого начала.

*lpszString*<br/>
Указывает на нулевую строку, содержащую префикс для поиска. Поиск независит от случая, поэтому эта строка может содержать любую комбинацию верхних и нижних букв.

### <a name="return-value"></a>Возвращаемое значение

Если значение возврата больше или равно 0, это нулевой индекс сопоставления элемента. CB_ERR если поиск был неудачным.

### <a name="remarks"></a>Remarks

Эта функция не поддерживается `ComboBoxEx` управлением Windows. Для получения дополнительной информации об этом элементе управления, см [ComboBoxEx управления](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

## <a name="ccomboboxfindstringexact"></a><a name="findstringexact"></a>CComboBox::FindStringExact

Позвоните `FindStringExact` функции участника, чтобы найти первую строку списка-коробки (в комбо-коробке), которая соответствует строке, указанной в *lpszFind.*

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Параметры

*nИндексСтарт*<br/>
Уотек индекса элемента с нулевым уровнем до первого элемента, который будет искаться. Когда поиск достигает нижней части окна списка, он продолжается от верхней части окна списка обратно к элементу, указанному *nIndexStart.* Если *nIndexStart* -1, весь список поле ищется с самого начала.

*lpszFind*<br/>
Указывает на нулевую строку для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не является чувствительным к делу, поэтому эта строка может содержать любую комбинацию верхних и нижних букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе элемента сопоставления или CB_ERR если поиск был неудачным.

### <a name="remarks"></a>Remarks

Если комбо-коробка была создана со стилем владельца,рисовать, но без [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиля, `FindStringExact` попытки сопоставить значение двойного слова со значением *lpszFind*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

## <a name="ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo

Извлекает информацию `CComboBox` для объекта.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Параметры

*pcbi*<br/>
Указатель на структуру [COMBOBOXINFO.](/windows/win32/api/winuser/ns-winuser-comboboxinfo)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность [сообщения CB_GETCOMBOBOXINFO,](/windows/win32/Controls/cb-getcomboboxinfo) как описано в SDK Windows.

## <a name="ccomboboxgetcount"></a><a name="getcount"></a>CComboBox::GetCount

Вызов эту функцию участника, чтобы получить количество элементов в листе коробки часть комбо-бокс.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов. Обратный отсчет на один больше значения индекса последнего элемента (индекс основан на нулевом уровне). Это CB_ERR, если ошибка происходит.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

## <a name="ccomboboxgetcuebanner"></a><a name="getcuebanner"></a>CComboBox::GetCueBanner

Получает текст сигнала, который отображается для управления комбо-боксом.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszText*|(ваут) Указатель на буфер, который получает текст баннера кий.|
|*cchText*|(в) Размер буфера, на который указывает параметр *lpszText.*|

### <a name="return-value"></a>Возвращаемое значение

В первой перегрузке объект [CString,](../../atl-mfc-shared/using-cstring.md) содержащий текст баннера кий, если он существует; в противном случае `CString` объект, который имеет нулевую длину.

-или-

Во второй перегрузке, правда, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Cue текст — это подсказка, отображаемый в области ввода управления комбо-коробкой. Текст сигнала отображается до тех пор, пока пользователь не предоставит ввод.

Этот метод отправляет [CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner) сообщение, которое описано в SDK Windows.

## <a name="ccomboboxgetcursel"></a><a name="getcursel"></a>CComboBox::GetCurSel

Вызовите эту функцию участника, чтобы определить, какой элемент в комбо-коробке выбран.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе выбранного в настоящее время элемента в поле списка комбо-бокса или CB_ERR, если нет элемента выбран.

### <a name="remarks"></a>Remarks

`GetCurSel`возвращает индекс в список.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

## <a name="ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect

Вызов `GetDroppedControlRect` функции участника для извлечения координат экрана видимого (выпадающего) ящика списка выпадающих комбо-боксов.

```cpp
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Параметры

*lprect*<br/>
Указывает на [структуру RECT,](/windows/win32/api/windef/ns-windef-rect) которая должна получать координаты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

## <a name="ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a>CComboBox::GetDroppedState

Позвоните `GetDroppedState` функции участника, чтобы определить, является ли поле списка выпадающих комбо-бокс виден (упал).

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если поле списка видно; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

## <a name="ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth

Вызовите эту функцию, чтобы получить минимально допустимую ширину, в пикселях, из списка поле комбо-бокса.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха минимальная допустимая ширина в пикселях; в противном случае, CB_ERR.

### <a name="remarks"></a>Remarks

Эта функция применяется только к комбо-боксам с [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стилем.

По умолчанию минимальная допустимая ширина окна списка выпадающих составляет 0. Минимальная допустимая ширина может быть установлена, позвонив [в SetDroppedWidth.](#setdroppedwidth) Когда список-коробка часть комбо-коробка отображается, его ширина больше минимально допустимой ширины или ширина комбо-бокса.

### <a name="example"></a>Пример

  Смотрите пример [SetDroppedWidth](#setdroppedwidth).

## <a name="ccomboboxgeteditsel"></a><a name="geteditsel"></a>CComboBox::GetEditSel

Получает начальные и заканчивающиеся позиции персонажей текущего выбора в управлении редактированием комбо-коробки.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

32-битное значение, содержащее исходное положение в слове низкого порядка и положение первого невыбранного символа после окончания выбора в слове высокого порядка. Если эта функция используется в комбо-поле без элемента управления иссего, CB_ERR возвращается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

## <a name="ccomboboxgetextendedui"></a><a name="getextendedui"></a>CComboBox::GetExtendedUI

Позвоните `GetExtendedUI` функции участника, чтобы определить, имеет ли комбо-бокс пользовательский интерфейс по умолчанию или расширенный пользовательский интерфейс.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если комбо-бокс имеет расширенный пользовательский интерфейс; в противном случае 0.

### <a name="remarks"></a>Remarks

Расширенный пользовательский интерфейс можно определить следующим образом:

- Нажав на статический элемент управления отображает список поле только для комбо-коробок с [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стилем.

- Нажатие клавиши DOWN ARROW отображает поле списка (F4 отключен).

Прокрутка в статическом элементе отключена, когда список элементов не виден (клавиши стрелки отключены).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

## <a name="ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent

Извлекает из комбо-бокса ширину в пиксели, с помощью которых часть комбо-коробки можно прокручивать горизонтально.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прокрутка ширина списка-коробка часть комбо-коробки, в пикселях.

### <a name="remarks"></a>Remarks

Это применимо только в том случае, если часть комбо-коробки со списком коробки имеет горизонтальную панель прокрутки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

## <a name="ccomboboxgetitemdata"></a><a name="getitemdata"></a>CComboBox::GetItemData

Извлекает 32-битное значение, поставляемое приложением, связанное с указанным комбо-коробкой.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит нулевой индекс элемента в поле списка комбо-бокса.

### <a name="return-value"></a>Возвращаемое значение

32-битное значение, связанное с элементом, или CB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

32-битное значение можно установить с параметром *dwItemData* вызова функции участника [SetItemData.](#setitemdata) Используйте `GetItemDataPtr` функцию члена, если 32-битное значение, подносивщее для извлечения, является указателем **(недействительным).** <strong>\*</strong>

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

## <a name="ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a>CComboBox::GetItemDataPtr

Получает предоставленное приложение 32-битное значение, связанное с указанным комбо-коробкой в качестве указателя **(недействительным).** <strong>\*</strong>

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит нулевой индекс элемента в поле списка комбо-бокса.

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель, или -1, если происходит ошибка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

## <a name="ccomboboxgetitemheight"></a><a name="getitemheight"></a>CComboBox::GetItemHeight

Вызов `GetItemHeight` функции участника, чтобы получить высоту элементов списка в комбо-поле.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет компонент комбо-коробки, высота которого должна быть извлечена. Если параметр *nIndex* -1, то извлекается высота элементаконтроля (или статического текста) части комбо-коробки. Если комбо-бокс имеет [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, *nIndex* определяет нулевой индекс элемента списка, высота которого должна быть извлечена. В противном случае *nIndex* должен быть установлен на 0.

### <a name="return-value"></a>Возвращаемое значение

Высота, в пикселях, указанного элемента в комбо-коробке. При возникновении ошибки возвращается значение CB_ERR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

## <a name="ccomboboxgetlbtext"></a><a name="getlbtext"></a>CComboBox::GetLBText

Получает строку из списка поле комбо-бокс.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит нулевой индекс строки списка-коробки, который будет скопирован.

*lpszText*<br/>
Указывает на буфер, который должен получить строку. Буфер должен иметь достаточно места для строки и прекращающийся нулевой символ.

*rString*<br/>
Ссылка на `CString`.

### <a name="return-value"></a>Возвращаемое значение

Длина (в байтах) строки, исключающая прекращающийся нулевой характер. Если *nIndex* не указывает действительный индекс, значение возврата CB_ERR.

### <a name="remarks"></a>Remarks

Вторая форма этой функции `CString` члена заполняет объект текстом элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

## <a name="ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a>CComboBox::GetLBTextLen

Получает длину строки в листе поле комбо-бокс.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит нулевой индекс строки списка-коробки.

### <a name="return-value"></a>Возвращаемое значение

Длина строки в байтах, исключая прекращающийся нулевой характер. Если *nIndex* не указывает действительный индекс, значение возврата CB_ERR.

### <a name="example"></a>Пример

  Смотрите пример [cComboBox::GetLBText](#getlbtext).

## <a name="ccomboboxgetlocale"></a><a name="getlocale"></a>CComboBox::GetLocale

Извлекает локал, используемый комбо-коробкой.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение идентификатора локализации (LCID) для строк в комбо-коробке.

### <a name="remarks"></a>Remarks

Локаль используется, например, для определения порядка сортировки строк в отсортированном комбо-коробке.

### <a name="example"></a>Пример

  Смотрите пример [для CComboBox::SetLocale](#setlocale).

## <a name="ccomboboxgetminvisible"></a><a name="getminvisible"></a>CComboBox::GetMinVisible

Получает минимальное количество видимых элементов в списке выпадающих в настоящее время управления комбо-бокс.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное количество видимых элементов в текущем списке выпадающих.

### <a name="remarks"></a>Remarks

Этот метод отправляет [CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) сообщение, которое описано в SDK Windows.

## <a name="ccomboboxgettopindex"></a><a name="gettopindex"></a>CComboBox::GetTopIndex

Извлекает нулевой индекс первого видимого элемента в части комбо-коробки.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс первого видимого элемента в части комбо-бокса в случае успеха CB_ERR.

### <a name="remarks"></a>Remarks

Первоначально пункт 0 находится в верхней части окна списка, но если поле списка прокрутится, другой элемент может быть в верхней части.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

## <a name="ccomboboxinitstorage"></a><a name="initstorage"></a>CComboBox::InitStorage

Выделяет память для хранения элементов коробки списка в части комбо-бокса.

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

В случае успеха, максимальное количество элементов, которые список-коробка часть комбо-бокс может хранить до перераспределения памяти необходимо, в противном случае CB_ERRSPACE, то есть не хватает памяти доступна.

### <a name="remarks"></a>Remarks

Вызов ими, прежде чем добавлять большое количество `CComboBox`элементов в часть списка-бокса.

Только Windows 95/98: параметр *wParam* ограничен 16-битовыми значениями. Это означает, что в списках не может содержаться более 32 767 элементов. Хотя количество элементов ограничено, общий размер элементов в поле списка ограничен только доступной памятью.

Эта функция помогает ускорить инициализацию списков ящиков, которые имеют большое количество элементов (более 100). Он предраспределяет указанное количество памяти так, чтобы последующие функции [AddString,](#addstring) [InsertString](#insertstring)и [Dir](#dir) отнимут как можно меньше времени. Оценки для параметров можно использовать. Если вы переоцените, выделяется дополнительная память; если вы недооцениваете, обычное распределение используется для элементов, превышающей заранее выделенную сумму.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

## <a name="ccomboboxinsertstring"></a><a name="insertstring"></a>CComboBox::InsertString

Вставляет строку в список поля со списком.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит отсчитываемый от нуля индекс позиции в списке, в которую будет вставлена строка. Если этот параметр -1, строка добавляется к концу списка.

*lpszString*<br/>
Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. При возникновении ошибки возвращается значение CB_ERR. Если для хранения новой строки недостаточно места, возвращается значение CB_ERRSPACE.

### <a name="remarks"></a>Remarks

В отличие от функции-члена [AddString](#addstring) , функция-член `InsertString` не вызывает сортировку списка со стилем [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

> [!NOTE]
> Эта функция не поддерживается `ComboBoxEx` управлением Windows. Для получения дополнительной информации об этом элементе управления, см [ComboBoxEx управления](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

## <a name="ccomboboxlimittext"></a><a name="limittext"></a>CComboBox::LimitText

Ограничивает длину байтов текста, которые пользователь может ввести в управление редактированием комбо-коробки.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Параметры

*nMaxChars*<br/>
Определяет длину (в байтах) текста, который пользователь может ввести. Если этот параметр радо 0, длина текста установлена на 65 535 байтов.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно. Если требуется комбо-бокс со стилем [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или для комбо-бокса без элемента управления, значение возврата CB_ERR.

### <a name="remarks"></a>Remarks

Если комбо-бокс не имеет [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)стиля, установление предела текста, превышающее размер элемента управления редактированием, не будет иметь никакого эффекта.

`LimitText`только ограничивает текст, в который может ввести пользователь. Он не влияет на любой текст, уже направляемый при отправке сообщения, и не влияет на длину текста, скопированного на элемент управления редактированием при выборе строки в листе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

## <a name="ccomboboxmeasureitem"></a><a name="measureitem"></a>CComboBox::MeasureItem

Вызывается рамки, когда комбо-бокс со стилем владельца рисовать создается.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpИзмеренныйПункт*<br/>
Длинный указатель на структуру [MEASUREITEMSTRUCT.](/windows/win32/api/winuser/ns-winuser-measureitemstruct)

### <a name="remarks"></a>Remarks

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию члена `MEASUREITEMSTRUCT` и заполнить структуру, чтобы сообщить Windows о размерах списка поле в комбо-поле. Если комбо-коробка создана с [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стилем, фреймворк вызывает эту функцию элемента для каждого элемента в поле списка. В противном случае этот участник называется только один раз.

Использование стиля CBS_OWNERDRAWFIXED в поле со списком, рисуемом владельцем, созданным с помощью функции-члена `CWnd`[SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem), требует дальнейших рекомендаций по программированию. Смотрите обсуждение в [Техническом примечании 14](../../mfc/tn014-custom-controls.md).

Смотрите [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) для описания `MEASUREITEMSTRUCT` структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

## <a name="ccomboboxpaste"></a><a name="paste"></a>CComboBox::Paste

Вставляет данные из Clipboard в управление элементарной обработки комбо-бокса в текущем положении курсора.

```cpp
void Paste();
```

### <a name="remarks"></a>Remarks

Данные вставляются только в том случае, если Clipboard содержит данные в CF_TEXT формате.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

## <a name="ccomboboxresetcontent"></a><a name="resetcontent"></a>CComboBox::ResetContent

Удаляет все элементы из коробки списка и отодевать управление комбо-коробкой.

```cpp
void ResetContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

## <a name="ccomboboxselectstring"></a><a name="selectstring"></a>CComboBox::SelectString

Поиск строки в поле списка комбо-бокс, и если строка найдена, выбирает строку в поле списка и копирует ее для управления отсеивательством.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*nStartAfter*<br/>
Содержит нулевой индекс элемента перед поиском первого элемента. Когда поиск достигает нижней части окна списка, он продолжается от верхней части окна списка обратно к элементу, указанному *nStartAfter.* Если -1, весь список поле ищется с самого начала.

*lpszString*<br/>
Указывает на нулевую строку, содержащую префикс для поиска. Поиск независит от случая, поэтому эта строка может содержать любую комбинацию верхних и нижних букв.

### <a name="return-value"></a>Возвращаемое значение

Индекс выбранного элемента с нулевым уровнем, если строка найдена. Если поиск был неудачным, значение возврата CB_ERR и текущий выбор не изменяется.

### <a name="remarks"></a>Remarks

Строка выбирается только в том случае, если ее начальные символы (с отправной точки) соответствуют символам строки префикса.

Обратите внимание, `FindString` что функции и функции `SelectString` `SelectString` члена находят строку, но функция члена также выбирает строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

## <a name="ccomboboxsetcuebanner"></a><a name="setcuebanner"></a>CComboBox::SetCueBanner

Устанавливает текст сигнала, который отображается для управления комбо-коробкой.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpszText*|(в) Указатель на буфер с нулевым завершением, содержащий текст сигнала.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод успешен; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Cue текст — это подсказка, отображаемый в области ввода управления комбо-коробкой. Текст сигнала отображается до тех пор, пока пользователь не предоставит ввод.

Этот метод отправляет [CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_combobox,* которая используется для программного доступа к управлению комбо-коробкой. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Пример

Следующий пример кода устанавливает сигнал баннер для управления комбо-бокс.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsetcursel"></a><a name="setcursel"></a>CComboBox::SetCurSel

Выбирает строку в поле списка комбо-бокса.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Параметры

*Nвыберите*<br/>
Уотек нулевого индекса строки для выбора. Если -1, любой текущий выбор в поле списка удаляется и элемент управления отсеиваемий удаляется.

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс элемента, выбранный в случае успешного сообщения. Значение возврата CB_ERR, если *nSelect* превышает количество элементов в списке или если *nSelect* установлен на -1, который очищает выбор.

### <a name="remarks"></a>Remarks

При необходимости поле списка прокручивает строку в поле зрения (если поле списка видно). Текст в элементаре управления комбо-бокс аменяется, чтобы отразить новый выбор. Любой предыдущий выбор в поле списка удаляется.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

## <a name="ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth

Вызовите эту функцию, чтобы установить минимально допустимую ширину, в пикселях, из списка поле комбо-бокса.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Минимальная допустимая ширина лист-бокс часть комбо-бокс, в пикселях.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, новая ширина списка поле, в противном случае CB_ERR.

### <a name="remarks"></a>Remarks

Эта функция применяется только к комбо-боксам с [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стилем.

По умолчанию минимальная допустимая ширина окна списка выпадающих составляет 0. Когда список-коробка часть комбо-коробка отображается, его ширина больше минимально допустимой ширины или ширина комбо-бокса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

## <a name="ccomboboxseteditsel"></a><a name="seteditsel"></a>CComboBox::SetEditSel

Выбирает символы в управлении редактированием комбо-коробки.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Параметры

*nStartChar*<br/>
Определяет исходную позицию. Если исходная позиция установлена до -1, то любой существующий выбор удаляется.

*nEndChar*<br/>
Определяет конечную позицию. Если исходное положение настроено на -1, то выбирается весь текст от исходного положения до последнего символа в элементе управления редактирования.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция члена успешна; в противном случае 0. Это CB_ERR, `CComboBox` если имеет [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль или не имеет список поле.

### <a name="remarks"></a>Remarks

Позиции на нулевом уровне. Чтобы выбрать первый символ элемента управления редактирования, вы указываете исходное положение 0. Конечная позиция предназначена для персонажа сразу после последнего персонажа, чтобы выбрать. Например, чтобы выбрать первые четыре символа управления редактированием, можно использовать исходное положение 0 и исходное положение 4.

> [!NOTE]
> Эта функция не поддерживается `ComboBoxEx` управлением Windows. Для получения дополнительной информации об этом элементе управления, см [ComboBoxEx управления](/windows/win32/Controls/comboboxex-controls) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [для CComboBox::GetEditSel](#geteditsel).

## <a name="ccomboboxsetextendedui"></a><a name="setextendedui"></a>CComboBox::SetExtendedUI

Позвоните `SetExtendedUI` функции участника, чтобы выбрать либо пользовательский интерфейс по умолчанию, либо расширенный пользовательский интерфейс для комбо-бокса, который имеет [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Параметры

*bExtended*<br/>
Уточняется, следует ли в комбо-коробке использовать расширенный пользовательский интерфейс или пользовательский интерфейс по умолчанию. Значение TRUE выбирает расширенный пользовательский интерфейс; значение FALSE выбирает стандартный пользовательский интерфейс.

### <a name="return-value"></a>Возвращаемое значение

CB_OKAY, если операция выполняется успешно, или CB_ERR, если произошла ошибка.

### <a name="remarks"></a>Remarks

Расширенный пользовательский интерфейс можно определить следующим образом:

- Нажав на статический элемент управления отображает список поле только для комбо-коробок с CBS_DROPDOWNLIST стилем.

- Нажатие клавиши DOWN ARROW отображает поле списка (F4 отключен).

Прокрутка в статическом элементе отключена, когда список элементов не виден (клавиши стрелки отключены).

### <a name="example"></a>Пример

  Смотрите пример [для CComboBox::GetExtendedUI](#getextendedui).

## <a name="ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent

Устанавливает ширину, в пикселях, с помощью которых список-коробка часть комбо-бокс аможет быть прокрутка горизонтально.

```cpp
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Параметры

*nExtent*<br/>
Определяет количество пикселей, с помощью которых часть комбо-коробки в списке может быть прокручивается горизонтально.

### <a name="remarks"></a>Remarks

Если ширина окна списка меньше этого значения, горизонтальная панель прокрутки будет горизонтально прокручивать элементы в поле списка. Если ширина окна списка равна или больше этого значения, горизонтальная панель прокрутки скрыта или, если комбо-бокс имеет [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, отключен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

## <a name="ccomboboxsetitemdata"></a><a name="setitemdata"></a>CComboBox::SetItemData

Устанавливает 32-битное значение, связанное с указанным элементом, в комбо-коробке.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит нулевой индекс для набора элемента.

*dwItemData*<br/>
Содержит новое значение для ассоциирования с элементом.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Используйте `SetItemDataPtr` функцию участника, если 32-разрядный элемент должен быть указателем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

## <a name="ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a>CComboBox::SetItemDataPtr

Устанавливает 32-битное значение, связанное с указанным элементом, в комбо-поле, чтобы быть указанным указателем **(недействительным).** <strong>\*</strong>

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит нулевой индекс к элементу.

*Pdata*<br/>
Содержит указатель для ассоциирования с элементом.

### <a name="return-value"></a>Возвращаемое значение

CB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Этот указатель остается действительным в течение всего срока службы комбо-бокса, даже если относительное положение элемента в комбо-коробке может измениться по мере добавления или удаления элементов. Таким образом, индекс элемента в поле может измениться, но указатель остается надежным.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

## <a name="ccomboboxsetitemheight"></a><a name="setitemheight"></a>CComboBox::SetItemHeight

Вызов `SetItemHeight` функции участника, чтобы установить высоту элементов списка в комбо-коробке или высоту редактирования-управления (или статического текста) часть комбо-коробки.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет, устанавливается ли высота элементов списка или высота элемента управления редактированием (или статического текста) части комбо-коробки.

Если комбо-бокс имеет [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиль, *nIndex* определяет нулевой индекс элемента списка, высота которого должна быть установлена; в противном случае *nIndex* должен быть 0 и будет установлена высота всех элементов списка.

Если *nIndex* -1, то высота редуктора-управления или статической текстовой части комбо-коробки должна быть установлена.

*cyItemHeight*<br/>
Определяет высоту, в пикселях, компонента комбо-коробки, идентифицированного *nIndex.*

### <a name="return-value"></a>Возвращаемое значение

CB_ERR, если индекс или высота недействительны; в противном случае 0.

### <a name="remarks"></a>Remarks

Высота элемента управления редактированием (или статического текста) комбо-коробки устанавливается независимо от высоты элементов списка. Приложение должно убедиться, что высота элемента управления редактированием (или статического текста) не меньше, чем высота конкретного элемента списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

## <a name="ccomboboxsetlocale"></a><a name="setlocale"></a>CComboBox::SetLocale

Устанавливает идентификатор локализации для этой комбо-коробки.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Параметры

*nNewLocale*<br/>
Новое значение идентификатора локализации (LCID) для настройки для комбо-коробки.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение идентификатора локализации (LCID) для этой комбо-коробки.

### <a name="remarks"></a>Remarks

Если `SetLocale` не вызывается, локализуется из системы. Этот язык по умолчанию системы может быть изменен с помощью регионального (или международного) приложения панели управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

## <a name="ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems

Устанавливает минимальное количество видимых элементов в списке выпадающих полей текущего управления комбо-боксом.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iMinVisible*|(в) Определяет минимальное количество видимых элементов.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет переменную, *m_combobox,* которая используется для программного доступа к управлению комбо-коробкой. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Пример

Следующий пример кода вставляет 20 элементов в список управления комбо-боксом. Затем указывается, что при нажатии на стрелку выпадающей элемент аудирует как минимум 10 элементов.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsettopindex"></a><a name="settopindex"></a>CComboBox::SetTopIndex

Гарантирует, что определенный элемент виден в части комбо-коробки.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Определяет нулевой индекс элемента списка-коробки.

### <a name="return-value"></a>Возвращаемое значение

Ноль в случае успеха или CB_ERR, если происходит ошибка.

### <a name="remarks"></a>Remarks

Система прокручивает поле списка до тех пор, пока ни элемент, указанный *nIndex,* не появится в верхней части окна списка, ни максимальный диапазон прокрутки не будет достигнут.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

## <a name="ccomboboxshowdropdown"></a><a name="showdropdown"></a>CComboBox::ShowDropDown

Показывает или скрывает список поле комбо-бокс, который имеет [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) или [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) стиле.

```cpp
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Параметры

*bShowIt*<br/>
Определяет, будет ли отображаемый список отображаться или скрыться. Значение TRUE показывает поле списка. Значение FALSE скрывает поле списка.

### <a name="remarks"></a>Remarks

По умолчанию, комбо-коробка этого стиля покажет поле списка.

Эта функция не влияет на комбо-коробку, созданную в стиле [CBS_SIMPLE.](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)

### <a name="example"></a>Пример

  Смотрите пример [для CComboBox::GetDroppedState](#getdroppedstate).

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
