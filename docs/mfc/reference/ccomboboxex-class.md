---
title: Класс CComboBoxEx
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: 7d46f175a62cda7f1ff08327830f1dffe2967727
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865552"
---
# <a name="ccomboboxex-class"></a>Класс CComboBoxEx

Расширяет элемент управления "поле со списком", предоставляя поддержку списков изображений.

## <a name="syntax"></a>Синтаксис

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CComboBoxEx:: CComboBoxEx](#ccomboboxex)|Формирует объект `CComboBoxEx`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CComboBoxEx:: Create](#create)|Создает поле со списком и прикрепляет его к объекту `CComboBoxEx`.|
|[CComboBoxEx:: Креатикс](#createex)|Создает поле со списком с заданными расширенными стилями Windows и прикрепляет его к объекту `ComboBoxEx`.|
|[CComboBoxEx::D Елетеитем](#deleteitem)|Удаляет элемент из элемента управления `ComboBoxEx`.|
|[CComboBoxEx:: Жеткомбобоксктрл](#getcomboboxctrl)|Извлекает указатель на элемент управления дочернего поля со списком.|
|[CComboBoxEx:: Жетедитктрл](#geteditctrl)|Получает маркер для элемента управления "поле ввода" элемента управления `ComboBoxEx`.|
|[CComboBoxEx:: Жетекстендедстиле](#getextendedstyle)|Извлекает расширенные стили, используемые для элемента управления `ComboBoxEx`.|
|[CComboBoxEx::/ImageList](#getimagelist)|Извлекает указатель на список изображений, назначенный элементу управления `ComboBoxEx`.|
|[CComboBoxEx:: DataItem](#getitem)|Извлекает сведения об элементе для заданного `ComboBoxEx` элемента.|
|[CComboBoxEx:: Хаседитчанжед](#haseditchanged)|Определяет, изменил ли пользователь содержимое элемента управления "поле ввода `ComboBoxEx`", введя.|
|[CComboBoxEx:: InsertItem](#insertitem)|Вставляет новый элемент в элемент управления `ComboBoxEx`.|
|[CComboBoxEx:: Сетекстендедстиле](#setextendedstyle)|Задает расширенные стили в элементе управления `ComboBoxEx`.|
|[CComboBoxEx:: Сетимажелист](#setimagelist)|Задает список изображений для элемента управления `ComboBoxEx`.|
|[CComboBoxEx:: Сетитем](#setitem)|Задает атрибуты элемента в элементе управления `ComboBoxEx`.|
|[CComboBoxEx:: SetWindowTheme](#setwindowtheme)|Задает визуальный стиль расширенного элемента управления "поле со списком".|

## <a name="remarks"></a>Remarks

С помощью `CComboBoxEx` для создания элементов управления "поле со списком" больше не нужно реализовывать собственный код рисования изображений. Вместо этого используйте `CComboBoxEx` для доступа к изображениям из списка изображений.

## <a name="image-list-support"></a>Поддержка списка изображений

В стандартном поле со списком владелец поля со списком отвечает за Рисование изображения путем создания поля со списком в качестве элемента управления, рисуемого владельцем. При использовании `CComboBoxEx`не нужно задавать стили рисования CBS_OWNERDRAWFIXED и CBS_HASSTRINGS, так как они являются подразумеваемыми. В противном случае необходимо написать код для выполнения операций рисования. Элемент управления `CComboBoxEx` поддерживает до трех изображений на элемент: один для выбранного состояния, один для невыбранного состояния, а другой для изображения оверлея.

## <a name="styles"></a>Стили

`CComboBoxEx` поддерживает стили CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST и WS_CHILD. Все остальные стили, переданные при создании окна, игнорируются элементом управления. После создания окна можно указать другие стили поля со списком, вызвав функцию-член `CComboBoxEx` [сетекстендедстиле](#setextendedstyle). С помощью этих стилей можно:

- Задайте для строк поиска в списке регистр символов.

- Создайте элемент управления "поле со списком", в котором используется косая черта ("/"), обратная косая черта ("\\") и точка (".") в качестве разделителей слов. Это позволяет пользователям переходить от Word к Word с помощью сочетания клавиш CTRL + стрелка.

- Задайте для элемента управления "поле со списком" значение "отображать" или "не отображать изображение". Если изображение не отображается, поле со списком может удалить отступ текста, который соответствует изображению.

- Создайте небольшой элемент управления "поле со списком", в том числе его размер, чтобы он был вырезан в расширенном поле со списком, которое оно содержит.

Эти флаги стиля описаны далее в разделе [Использование CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="item-retention-and-callback-item-attributes"></a>Атрибуты хранения элементов и элементов обратного вызова

Сведения об элементе, такие как индексы для элементов и изображений, значения отступов и текстовые строки, хранятся в структуре Win32 [комбобоксекситем](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw), как описано в Windows SDK. Структура также содержит элементы, соответствующие флагам обратного вызова.

Подробное описание концептуального обсуждения см. в разделе [Использование CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="ccomboboxex"></a>CComboBoxEx:: CComboBoxEx

Вызовите эту функцию-член, чтобы создать объект `CComboBoxEx`.

```
CComboBoxEx();
```

##  <a name="create"></a>CComboBoxEx:: Create

Создает поле со списком и прикрепляет его к объекту `CComboBoxEx`.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает сочетание стилей полей со списком, применяемых к полю со списками. Дополнительные сведения о стилях см. в разделе **Примечания** ниже.

*rect*<br/>
Ссылка на объект [крект](../../atl-mfc-shared/reference/crect-class.md) или структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , которая является положением и размером поля со списком.

*ппарентвнд*<br/>
Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном поля со списком (обычно `CDialog`). Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект успешно создан; в противном случае — 0.

### <a name="remarks"></a>Remarks

Создайте объект `CComboBoxEx` в два этапа:

1. Вызовите [CComboBoxEx](#ccomboboxex) для создания объекта `CComboBoxEx`.

1. Вызовите эту функцию члена, которая создает расширенное поле со списком Windows и присоединяет его к объекту `CComboBoxEx`.

При вызове `Create`MFC инициализирует общие элементы управления.

При создании поля со списком можно указать любые или все из следующих стилей поля со списком:

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

Все остальные стили, переданные при создании окна, игнорируются. Элемент управления `ComboBoxEx` также поддерживает расширенные стили, предоставляющие дополнительные возможности. Эти стили описаны в разделе [ComboBoxEx Control Extended Styles](/windows/win32/Controls/comboboxex-control-extended-styles)в Windows SDK. Задайте эти стили, вызвав [сетекстендедстиле](#setextendedstyle).

Если вы хотите использовать расширенные стили Windows с элементом управления, вызовите [креатикс](#createex) вместо `Create`.

##  <a name="createex"></a>CComboBoxEx:: Креатикс

Вызовите эту функцию, чтобы создать расширенный элемент управления "поле со списком" (дочернее окно) и связать его с объектом `CComboBoxEx`.

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
Стиль элемента управления "поле со списком". Список стилей см. в разделе [CREATE](#create) .

*rect*<br/>
Ссылка на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , описывающую размер и расположение создаваемого окна в клиентских координатах *ппарентвнд*.

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*nID*<br/>
Идентификатор дочернего окна элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` вместо `Create` для применения расширенных стилей Windows, заданных **WS_EX_** в формате расширенного стиля Windows.

`CreateEx` создает элемент управления с расширенными стилями Windows, заданным параметром *двексстиле*. Необходимо задать расширенные стили, относящиеся к расширенному элементу управления "поле со списком", с помощью [сетекстендедстиле](#setextendedstyle). Например, используйте `CreateEx`, чтобы задать такие стили, как WS_EX_CONTEXTHELP, но используйте `SetExtendedStyle` для установки таких стилей, как CBES_EX_CASESENSITIVE. Дополнительные сведения см. в описании стилей в разделе [ComboBoxEx Control Extended Styles](/windows/win32/Controls/comboboxex-control-extended-styles) в Windows SDK.

##  <a name="deleteitem"></a>CComboBoxEx::D Елетеитем

Удаляет элемент из элемента управления `ComboBoxEx`.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>Параметры

*ииндекс*<br/>
Отсчитываемый от нуля индекс удаляемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, остающихся в элементе управления. Если *ииндекс* является недопустимым, функция возвращает CB_ERR.

### <a name="remarks"></a>Remarks

Эта функция члена реализует функциональность сообщения [CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem), как описано в Windows SDK. При вызове DeleteItem в родительское окно будет отправлено [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение с CBEN_DELETEITEMным уведомлением.

##  <a name="getcomboboxctrl"></a>CComboBoxEx:: Жеткомбобоксктрл

Вызовите эту функцию-член для получения указателя на элемент управления "поле со списком" в объекте `CComboBoxEx`.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CComboBox`.

### <a name="remarks"></a>Remarks

Элемент управления `CComboBoxEx` состоит из родительского окна, которое инкапсулирует `CComboBox`.

Объект `CComboBox`, на который указывает возвращаемое значение, является временным объектом и уничтожается во время следующей обработки простоя.

##  <a name="geteditctrl"></a>CComboBoxEx:: Жетедитктрл

Вызовите эту функцию-член, чтобы получить указатель на элемент управления Edit для поля со списком.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CEdit](../../mfc/reference/cedit-class.md) .

### <a name="remarks"></a>Remarks

Элемент управления `CComboBoxEx` использует поле ввода при его создании с использованием стиля CBS_DROPDOWN.

Объект `CEdit`, на который указывает возвращаемое значение, является временным объектом и уничтожается во время следующей обработки простоя.

##  <a name="getextendedstyle"></a>CComboBoxEx:: Жетекстендедстиле

Вызовите эту функцию-член, чтобы получить расширенные стили, используемые для элемента управления `CComboBoxEx`.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD, содержащее расширенные стили, используемые для элемента управления "поле со списком".

### <a name="remarks"></a>Remarks

Дополнительные сведения об этих стилях см. в разделе [ComboBoxEx Control Extended Styles](/windows/win32/Controls/comboboxex-control-extended-styles) в Windows SDK.

##  <a name="getimagelist"></a>CComboBoxEx::/ImageList

Вызовите эту функцию-член, чтобы получить указатель на список изображений, используемый элементом управления `CComboBoxEx`.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) . В случае сбоя эта функция члена возвращает значение NULL.

### <a name="remarks"></a>Remarks

Объект `CImageList`, на который указывает возвращаемое значение, является временным объектом и уничтожается во время следующей обработки простоя.

##  <a name="getitem"></a>CComboBoxEx:: DataItem

Извлекает сведения об элементе для заданного `ComboBoxEx` элемента.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*пкбитем*<br/>
Указатель на структуру [комбобоксекситем](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) , которая будет принимать сведения об элементе.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует функциональность сообщения [CBEM_GETITEM](/windows/win32/Controls/cbem-getitem), как описано в Windows SDK.

##  <a name="haseditchanged"></a>CComboBoxEx:: Хаседитчанжед

Определяет, изменил ли пользователь содержимое элемента управления "поле ввода `ComboBoxEx`", введя.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь ввел в поле ввода элемента управления; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует функциональность сообщения [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged), как описано в Windows SDK.

##  <a name="insertitem"></a>CComboBoxEx:: InsertItem

Вставляет новый элемент в элемент управления `ComboBoxEx`.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*пкбитем*<br/>
Указатель на структуру [комбобоксекситем](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) , которая будет принимать сведения об элементе. Эта структура содержит значения флагов обратного вызова для элемента.

### <a name="return-value"></a>Возвращаемое значение

Индекс, по которому новый элемент был вставлен в случае успеха; в противном случае — 1.

### <a name="remarks"></a>Remarks

При вызове `InsertItem`в родительское окно будет отправлено [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение с уведомлением об [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) .

##  <a name="setextendedstyle"></a>CComboBoxEx:: Сетекстендедстиле

Вызовите эту функцию-член, чтобы задать расширенные стили, используемые для расширенного элемента управления поля со списком.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>Параметры

*двексмаск*<br/>
Значение типа DWORD, указывающее, какие стили в *двексстилес* должны быть затронуты. Будут изменены только расширенные стили в *двексмаск* . Все остальные стили будут поддерживаться как есть. Если этот параметр равен нулю, будут затронуты все стили в *двексстилес* .

*двексстилес*<br/>
Значение типа DWORD, содержащее поле со списком, элементы управления расширенными стилями, заданными для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD, содержащее расширенные стили, которые ранее использовались для элемента управления.

### <a name="remarks"></a>Remarks

Дополнительные сведения об этих стилях см. в разделе [ComboBoxEx Control Extended Styles](/windows/win32/Controls/comboboxex-control-extended-styles) в Windows SDK.

Для создания расширенного элемента управления "поле со списком" с расширенными стилями Windows используйте [креатикс](#createex).

##  <a name="setimagelist"></a>CComboBoxEx:: Сетимажелист

Задает список изображений для элемента управления `ComboBoxEx`.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*пимажелист*<br/>
Указатель на объект `CImageList`, содержащий изображения для использования с элементом управления `CComboBoxEx`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий изображения, которые ранее использовались элементом управления `CComboBoxEx`. Значение NULL, если список изображений ранее не был задан.

### <a name="remarks"></a>Remarks

Эта функция члена реализует функциональность сообщения [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist), как описано в Windows SDK. Если изменить высоту элемента управления редактирования по умолчанию, вызовите функцию Win32 [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) , чтобы изменить размер элемента управления после вызова `SetImageList`, или он будет отображаться неправильно.

Объект `CImageList`, на который указывает возвращаемое значение, является временным объектом и уничтожается во время следующей обработки простоя.

##  <a name="setitem"></a>CComboBoxEx:: Сетитем

Задает атрибуты элемента в элементе управления `ComboBoxEx`.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*пкбитем*<br/>
Указатель на структуру [комбобоксекситем](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) , которая будет принимать сведения об элементе.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует функциональность сообщения [CBEM_SETITEM](/windows/win32/Controls/cbem-setitem), как описано в Windows SDK.

##  <a name="setwindowtheme"></a>CComboBoxEx:: SetWindowTheme

Задает визуальный стиль расширенного элемента управления "поле со списком".

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*псзсубаппнаме*<br/>
Указатель на строку в Юникоде, содержащую расширенный визуальный стиль поля со списком для задания.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение не используется.

### <a name="remarks"></a>Remarks

Эта функция члена эмулирует функциональность [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) сообщения, как описано в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Пример MFCIE для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)
