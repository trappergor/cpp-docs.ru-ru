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
ms.openlocfilehash: c3fd57510a38d597b827f80ab98a0be280ad31e3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254102"
---
# <a name="ccomboboxex-class"></a>Класс CComboBoxEx

Расширяет элемент управления "поле со списком", предоставляя поддержку списков изображений.

## <a name="syntax"></a>Синтаксис

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Создает объект `CComboBoxEx`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComboBoxEx::Create](#create)|Создает поле со списком и присоединяет его к `CComboBoxEx` объекта.|
|[CComboBoxEx::CreateEx](#createex)|Создает поле со списком с указанным расширенные стили Windows и присоединяет его к `ComboBoxEx` объекта.|
|[CComboBoxEx::DeleteItem](#deleteitem)|Удаляет элемент из `ComboBoxEx` элемента управления.|
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Извлекает указатель на дочерний элемент управления поля со списком.|
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Извлекает дескриптор в область редактирования элемента управления `ComboBoxEx` элемента управления.|
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, которые используются для `ComboBoxEx` элемента управления.|
|[CComboBoxEx::GetImageList](#getimagelist)|Извлекает указатель на список изображений, назначенные `ComboBoxEx` элемента управления.|
|[CComboBoxEx::GetItem](#getitem)|Получение сведений об элементе для заданного `ComboBoxEx` элемента.|
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Определяет, если пользователь изменил содержимое `ComboBoxEx` изменение элемента управления вводом.|
|[CComboBoxEx::InsertItem](#insertitem)|Вставляет новый элемент в `ComboBoxEx` элемента управления.|
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили в `ComboBoxEx` элемента управления.|
|[CComboBoxEx::SetImageList](#setimagelist)|Задает список изображений для `ComboBoxEx` элемента управления.|
|[CComboBoxEx::SetItem](#setitem)|Задает атрибуты для элемента в `ComboBoxEx` элемента управления.|
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль Расширенное поле со списком, элемент управления ".|

## <a name="remarks"></a>Примечания

С помощью `CComboBoxEx` для создания элементов управления со списком, больше не нужно реализовывать свой собственный образ, код отрисовки. Вместо этого используйте `CComboBoxEx` к образам доступа из списка изображений.

## <a name="image-list-support"></a>Поддержка списка изображений

В поле со списком стандартных владельцем поле со списком отвечает за рисование изображения, создавая поле со списком, как элемент управления рисуемого владельцем. При использовании `CComboBoxEx`, необходимо установить эти стили CBS_OWNERDRAWFIXED и CBS_HASSTRINGS, так как они подразумеваются. В противном случае необходимо написать код для выполнения операций рисования. Объект `CComboBoxEx` элемент управления поддерживает до трех образов каждого элемента: один для выбранного состояния, один для невыбранном состоянии и один для наложения изображения.

## <a name="styles"></a>Стили

`CComboBoxEx` поддерживает стили CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST и WS_CHILD. Все стили, переданный при создании окна игнорируются элементом управления. После создания окна другие поля со списком можно предоставить стили окна путем вызова `CComboBoxEx` функция-член [SetExtendedStyle](#setextendedstyle). С помощью этих стилей можно:

- Набор операций поиска в списке, чтобы учитывать регистр.

- Создать поле со списком, использующего символ косой черты («/»), обратной косой черты ("\\") и в течение периода (".") символы в качестве разделителей слов. Это позволяет пользователю переходить из word в word, нажав клавиши CTRL + стрелка.

- Задайте поля со списком управления поле для отображения или не выводит изображение. Если изображение не отображается, в поле со списком можно удалить отступ текста, который допустим для изображения.

- Создайте узкий поле со списком, включая изменение его размера, поэтому она обрезает ширина поля со списком содержащихся в нем.

Эти флаги стиля описаны далее в [использование CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="item-retention-and-callback-item-attributes"></a>Хранение элементов и атрибутов элемента обратного вызова

Сведения об элементе, например индексы элементов и изображений, необходимые значения отступов и текстовых строк, хранится в структуре Win32 [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema), как описано в пакете Windows SDK. Эта структура также содержит элементы, соответствующие флаги обратного вызова.

Подробные Общие сведения, см. в разделе [использование CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx

Эта функция-член для создания вызова `CComboBoxEx` объекта.

```
CComboBoxEx();
```

##  <a name="create"></a>  CComboBoxEx::Create

Создает поле со списком и присоединяет его к `CComboBoxEx` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает сочетание стили поля со списком, применяется к поле со списком. См. в разделе **"Примечания"** ниже дополнительные сведения о стилях.

*rect*<br/>
Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](/previous-versions/dd162897\(v=vs.85\)) структуры, которая является положение и размер поля со списком.

*pParentWnd*<br/>
Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, который является родительским окном в поле со списком (обычно `CDialog`). Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект был создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Создание `CComboBoxEx` объекта в два этапа:

1. Вызовите [CComboBoxEx](#ccomboboxex) для создания `CComboBoxEx` объекта.

1. Вызов этой функцией-членом, которая создает расширенные поля со списком Windows и присоединяет его к `CComboBoxEx` объекта.

При вызове `Create`, MFC инициализирует Общие элементы управления.

При создании поля со списком, можно указать любые или все из следующих поле со списком стилей:

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

Все стили, переданный при создании окна учитываются. `ComboBoxEx` Управления также поддерживает расширенные стили, которые предоставляют дополнительные возможности. Эти стили описаны в [ComboBoxEx управления расширенные стили](/windows/desktop/Controls/comboboxex-control-extended-styles), в пакете Windows SDK. Установка этих стилей путем вызова [SetExtendedStyle](#setextendedstyle).

Если вы хотите использовать windows расширенных стилей с элементом управления, вызовите [CreateEx](#createex) вместо `Create`.

##  <a name="createex"></a>  CComboBoxEx::CreateEx

Вызывайте эту функцию для создания расширенных поле со списком (дочернего окна) и связать его с `CComboBoxEx` объекта.

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
Стиль элемента управления поля со списком. См. в разделе [создать](#create) список стилей.

*rect*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родительским для элемента управления.

*nID*<br/>
Идентификатор элемента управления дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо `Create` применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.

`CreateEx` Создает элемент управления с помощью расширенных стилей Windows, определяемое *dwExStyle*. Необходимо задать расширенные стили конкретных Расширенное поле со списком элемента управления с помощью [SetExtendedStyle](#setextendedstyle). Например, использовать `CreateEx` такие стили заданы как WS_EX_CONTEXTHELP, но используют `SetExtendedStyle` должны стать CBES_EX_CASESENSITIVE подобные стили. Дополнительные сведения см. в разделе стили, описанную в разделе [стили расширенных элементов управления ComboBoxEx](/windows/desktop/Controls/comboboxex-control-extended-styles) в пакете Windows SDK.

##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem

Удаляет элемент из `ComboBoxEx` элемента управления.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
Отсчитываемый от нуля индекс удаляемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, оставшихся в элементе управления. Если *iIndex* является недопустимым, функция возвращает CB_ERR.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональные возможности сообщения [CBEM_DELETEITEM](/windows/desktop/Controls/cbem-deleteitem), как описано в пакете Windows SDK. При вызове DeleteItem, [WM_NOTIFY](/windows/desktop/controls/wm-notify) сообщение с уведомлением CBEN_DELETEITEM будут отправляться в родительское окно.

##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl

Вызывайте эту функцию члена, чтобы получить указатель на поле со списком в `CComboBoxEx` объекта.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CComboBox` .

### <a name="remarks"></a>Примечания

`CComboBoxEx` Элемент управления состоит из родительского окна, который инкапсулирует `CComboBox`.

`CComboBox` Объект, на которые указывает возвращаемое значение является временным и разрушается во время следующей обработки время простоя.

##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl

Вызывайте эту функцию члена, чтобы получить указатель на поле ввода поля со списком.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CEdit](../../mfc/reference/cedit-class.md) объекта.

### <a name="remarks"></a>Примечания

Объект `CComboBoxEx` элемент управления использует поле редактирования при его создании в стиле CBS_DROPDOWN.

`CEdit` Объект, на которые указывает возвращаемое значение является временным и разрушается во время следующей обработки время простоя.

##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle

Эта функция-член для получения расширенных стилей, которые используются для вызова `CComboBoxEx` элемента управления.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее расширенные стили, используемые для элемента управления полем со списком.

### <a name="remarks"></a>Примечания

См. в разделе [стили расширенных элементов управления ComboBoxEx](/windows/desktop/Controls/comboboxex-control-extended-styles) в пакете SDK для Windows, Дополнительные сведения об этих стилях.

##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList

Вызывайте эту функцию члена, чтобы получить указатель на список изображений, используемых `CComboBoxEx` элемента управления.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта. Если происходит сбой, эта функция-член возвращает значение NULL.

### <a name="remarks"></a>Примечания

`CImageList` Объект, на которые указывает возвращаемое значение является временным и разрушается во время следующей обработки время простоя.

##  <a name="getitem"></a>  CComboBoxEx::GetItem

Получение сведений об элементе для заданного `ComboBoxEx` элемента.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*pCBItem*<br/>
Указатель на [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) структуры, который будет получать сведения об элементе.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональные возможности сообщения [CBEM_GETITEM](/windows/desktop/Controls/cbem-getitem), как описано в пакете Windows SDK.

##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged

Определяет, если пользователь изменил содержимое `ComboBoxEx` изменение элемента управления вводом.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если введенное пользователем в поле ввода элемента управления; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональные возможности сообщения [CBEM_HASEDITCHANGED](/windows/desktop/Controls/cbem-haseditchanged), как описано в пакете Windows SDK.

##  <a name="insertitem"></a>  CComboBoxEx::InsertItem

Вставляет новый элемент в `ComboBoxEx` элемента управления.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*pCBItem*<br/>
Указатель на [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) структуры, который будет получать сведения об элементе. Эта структура содержит значения флага обратного вызова для элемента.

### <a name="return-value"></a>Возвращаемое значение

Индекс, по которому был вставлен новый элемент, если выполнение прошло успешно; в противном случае-1.

### <a name="remarks"></a>Примечания

При вызове `InsertItem`, [WM_NOTIFY](/windows/desktop/controls/wm-notify) сообщений с [CBEN_INSERTITEM](/windows/desktop/Controls/cben-insertitem) уведомление будет отправлено в родительское окно.

##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle

Эта функция члена задать расширенные стили, используемые для расширенного элемента управления списком.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>Параметры

*dwExMask*<br/>
Значение DWORD, указывающее, какие стили в *dwExStyles* , могут быть затронуты. Расширенные стили в *dwExMask* будет изменен. Все другие стили сохраняются как есть. Если этот параметр равен нулю, то все стили в *dwExStyles* будут применяться.

*dwExStyles*<br/>
Значение DWORD, содержащее поле со списком расширенные стили, чтобы задать для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее расширенные стили, которые ранее использовали для элемента управления.

### <a name="remarks"></a>Примечания

См. в разделе [стили расширенных элементов управления ComboBoxEx](/windows/desktop/Controls/comboboxex-control-extended-styles) в пакете SDK для Windows, Дополнительные сведения об этих стилях.

Чтобы создать поле со списком расширенного элемента управления с использованием windows расширенных стилей, используйте [CreateEx](#createex).

##  <a name="setimagelist"></a>  CComboBoxEx::SetImageList

Задает список изображений для `ComboBoxEx` элемента управления.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*pImageList*<br/>
Указатель на `CImageList` объект, содержащий изображения для использования в `CComboBoxEx` элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, содержащий изображения, ранее используемые `CComboBoxEx` элемента управления. Значение NULL, если список изображений не был ранее установлен.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональные возможности сообщения [CBEM_SETIMAGELIST](/windows/desktop/Controls/cbem-setimagelist), как описано в пакете Windows SDK. Если изменить высоту элемента управления по умолчанию, вызовите функцию Win32 [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) для изменения размеров элемента управления, после вызова метода `SetImageList`, или он будет отображаться правильно.

`CImageList` Объект, на которые указывает возвращаемое значение является временным и разрушается во время следующей обработки время простоя.

##  <a name="setitem"></a>  CComboBoxEx::SetItem

Задает атрибуты для элемента в `ComboBoxEx` элемента управления.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Параметры

*pCBItem*<br/>
Указатель на [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) структуры, который будет получать сведения об элементе.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует функциональные возможности сообщения [CBEM_SETITEM](/windows/desktop/Controls/cbem-setitem), как описано в пакете Windows SDK.

##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme

Задает визуальный стиль Расширенное поле со списком, элемент управления ".

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Параметры

*pszSubAppName*<br/>
Указатель на строку Юникода, которая содержит поле Расширенное поле со списком визуальный стиль для задания.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение не используется.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности [CBEM_SETWINDOWTHEME](/windows/desktop/Controls/cbem-setwindowtheme) сообщения, как описано в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Пример MFC MFCIE](../../overview/visual-cpp-samples.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)
