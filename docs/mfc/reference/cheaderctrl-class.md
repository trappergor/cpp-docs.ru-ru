---
title: Класс CHeaderCtrl
ms.date: 11/04/2016
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
ms.openlocfilehash: 56c694283c5143174b0ce7370d98a244c056bc1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496022"
---
# <a name="cheaderctrl-class"></a>Класс CHeaderCtrl

Предоставляет функциональные возможности стандартного элемента управления "заголовок" Windows.

## <a name="syntax"></a>Синтаксис

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Создает объект `CHeaderCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Удаляет все фильтры для заголовка элемента управления.|
|[CHeaderCtrl::ClearFilter](#clearfilter)|Удаляет фильтр для заголовка элемента управления.|
|[CHeaderCtrl::Create](#create)|Создает элемент управления заголовка и присоединяет его к `CHeaderCtrl` объекта.|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Создает версию прозрачное изображение элемента в элементе управления заголовка.|
|[CHeaderCtrl::CreateEx](#createex)|Создает элемент управления заголовка с указанным расширенные стили Windows и присоединяет его к `CListCtrl` объекта.|
|[CHeaderCtrl::DeleteItem](#deleteitem)|Удаляет элемент из элемента управления заголовка.|
|[CHeaderCtrl::DrawItem](#drawitem)|Рисует указанный элемент управления заголовка.|
|[CHeaderCtrl::EditFilter](#editfilter)|Запускает редактирование элемента управления заголовка указанный фильтр.|
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Получает ширину поля растрового изображения в элементе управления заголовка.|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Получает идентификатор элемента в текущий элемент управления заголовка с фокусом.|
|[CHeaderCtrl::GetImageList](#getimagelist)|Возвращает дескриптор списка изображений, используемый для рисования элементов заголовка в элементе управления заголовка.|
|[CHeaderCtrl::GetItem](#getitem)|Извлекает сведения об элементе в элементе управления заголовка.|
|[CHeaderCtrl::GetItemCount](#getitemcount)|Получает число элементов в элементе управления заголовка.|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Получает ограничивающий прямоугольник сведения для указанной кнопки раскрывающегося списка в элементе управления заголовка.|
|[CHeaderCtrl::GetItemRect](#getitemrect)|Получает ограничивающий прямоугольник для данного элемента в элементе управления заголовка.|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Получает порядок элементов в элементе заголовка слева направо.|
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Получает ограничивающий прямоугольник для кнопки переполнения для текущего элемента управления заголовка.|
|[CHeaderCtrl::HitTest](#hittest)|Определяет, какой элемент заголовка, если таковые имеются, находится в заданной точке.|
|[CHeaderCtrl::InsertItem](#insertitem)|Вставляет новый элемент в элемент управления заголовка.|
|[CHeaderCtrl::Layout](#layout)|Извлекает размер и положение элемента управления заголовка в пределах заданного прямоугольника.|
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Получает значение индекса для элемента в зависимости от их порядка в элементе управления заголовком.|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Задает ширину поля растрового изображения в элементе управления заголовка.|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Задает интервал времени ожидания между временем изменений в силу в атрибуты фильтра и учет `HDN_FILTERCHANGE` уведомлений.|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Устанавливает фокус на элемент указанного заголовка в элементе управления текущего заголовка.|
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Изменения, перетащите разделитель между элементы заголовка, чтобы вручную и drop для элемента заголовка.|
|[CHeaderCtrl::SetImageList](#setimagelist)|Назначает элемент управления заголовка списка изображений.|
|[CHeaderCtrl::SetItem](#setitem)|Устанавливает атрибуты указанного элемента в элементе управления заголовка.|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Задает слева направо порядок элементов в элементе управления заголовка.|

## <a name="remarks"></a>Примечания

Элемент управления заголовка — окно, которое обычно находится выше набора столбцов текста или цифр. Он содержит заголовок для каждого столбца, и его можно разделить на части. Пользователь может перетащить разделитель, разделяющий частей, чтобы задать ширину каждого столбца. Иллюстрация заголовка элемента управления, см. в разделе [элементы управления заголовка](/windows/desktop/Controls/header-controls).

Этот элемент управления (и, следовательно `CHeaderCtrl` класс) доступны только для программ, выполняемых в Windows 95/98 и Windows NT версии 3.51 и более поздних версиях.

Возможности, добавленные в элементах управления Windows 95/Internet Explorer 4.0 включает в себя следующее:

- Заголовок элемента пользовательскую сортировку.

- Элемент заголовка перетаскивание, для переупорядочения элементов заголовка. При создании используйте hds_dragdrop-стиль `CHeaderCtrl` объекта.

- Текст заголовка столбца постоянно можно просмотреть при изменении размера столбца. При создании используйте стиль HDS_FULLDRAG `CHeaderCtrl` объекта.

- Заголовок отслеживание, выделяющей элемента заголовка при наведении указателя на его. При создании используйте стиль HDS_HOTTRACK `CHeaderCtrl` объекта.

- Поддержка списка изображений. Элементы заголовка может содержать изображения, хранящиеся в `CImageList` объект или текст.

Дополнительные сведения об использовании `CHeaderCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CHeaderCtrl](../../mfc/using-cheaderctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="cheaderctrl"></a>  CHeaderCtrl::CHeaderCtrl

Создает объект `CHeaderCtrl`.

```
CHeaderCtrl();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

##  <a name="clearallfilters"></a>  CHeaderCtrl::ClearAllFilters

Удаляет все фильтры для заголовка элемента управления.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщение Win32 [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter) со значением столбца-1, как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

##  <a name="clearfilter"></a>  CHeaderCtrl::ClearFilter

Удаляет фильтр для заголовка элемента управления.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Параметры

*nColumn*<br/>
Столбец значение, указывающее, какой фильтр для очистки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщение Win32 [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

##  <a name="create"></a>  CHeaderCtrl::Create

Создает элемент управления заголовка и присоединяет его к `CHeaderCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль заголовка элемента управления. Описание заголовка стили элемента управления, см. в разделе [стили элемента управления заголовка](/windows/desktop/Controls/header-control-styles) в пакете Windows SDK.

*Rect*<br/>
Задает размер и положение заголовка элемента управления. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.

*pParentWnd*<br/>
Указывает родительскому окну элемента управления заголовка, обычно `CDialog`. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления заголовка.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае значение равно нулю.

### <a name="remarks"></a>Примечания

При создании `CHeaderCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает элемент управления заголовка и присоединяет его к `CHeaderCtrl` объекта.

Помимо стили элемента управления заголовка, можно использовать следующие общие стили элемента управления, чтобы определить размещает элемент управления заголовка и изменяет свои размеры (см. в разделе [общие стили элемента управления](/windows/desktop/Controls/common-control-styles) Дополнительные сведения):

- CCS_BOTTOM заставляет элемент управления располагаться в нижней части клиентской области родительского окна и задает ширину должен совпадать с родительским ширина окна.

- Выделите предотвращает CCS_NODIVIDER точки два из которых выводится в верхней части элемента управления.

- CCS_NOMOVEY заставляет элемент управления для изменения размера и переместить сам горизонтально, но не по вертикали, в ответ на сообщение WM_SIZE. Если используется стиль CCS_NORESIZE, этот стиль не применяется. Элементы управления заголовка имеют этот стиль по умолчанию.

- CCS_NOPARENTALIGN запрещает автоматическое перемещение в верхней или нижней части родительского окна элемента управления. Вместо этого элемент управления хранит его положение в родительском окне, несмотря на изменения размера родительского окна. Если также используется стиль CCS_TOP или CCS_BOTTOM, высота корректируется по умолчанию, но положение и width остаются неизменными.

- CCS_NORESIZE запрещает использовать стандартную ширину и высоту, при задании начального размера или новый размер элемента управления. Вместо этого элемент управления использует ширины и высоты, определенное в запросе для создания или изменения размера.

- CCS_TOP заставляет элемент управления располагаться в верхней части клиентской области родительского окна и задает ширину должен совпадать с родительским ширина окна.

Следующие стили окно также можно применить к элементу управления заголовка (см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) Дополнительные сведения):

- WS_CHILD создает дочернее окно. Не может использоваться со стилем WS_POPUP.

- WS_VISIBLE создает окно, которое изначально является видимым.

- WS_DISABLED создает окно, которое изначально было отключено.

- WS_GROUP указывает первый элемент управления из группы элементов управления, в которых пользователь может перемещаться от одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, определенные с помощью стиля WS_GROUP после первого элемента управления, которым принадлежат той же группе. Следующий элемент управления с помощью стиля WS_GROUP завершает группы стилей и запускается следующая команда (то есть одна команда заканчивается где начинается следующее).

- WS_TABSTOP указывает один из любого числа элементов управления, которые пользователь может перемещать с помощью клавиши TAB. Клавиша TAB перемещает пользователя к следующему элементу управления, указанного стилем WS_TABSTOP.

Если вы хотите использовать windows расширенных стилей с элементом управления, вызовите [CreateEx](#createex) вместо `Create`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

##  <a name="createex"></a>  CHeaderCtrl::CreateEx

Создает элемент управления (дочернего окна) и связать его с `CHeaderCtrl` объекта.

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
Стиль заголовка элемента управления. Описание заголовка стили элемента управления, см. в разделе [стили элемента управления заголовка](/windows/desktop/Controls/header-control-styles) в пакете Windows SDK. См. в разделе [создать](#create) список дополнительные стили.

*Rect*<br/>
Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родительским для элемента управления.

*nID*<br/>
Идентификатор элемента управления дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо `Create` применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.

##  <a name="createdragimage"></a>  CHeaderCtrl::CreateDragImage

Создает версию прозрачное изображение элемента в элементе управления заголовка.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый от нуля индекс элемента в элементе управления заголовка. Изображения, назначенного этот элемент является основой для прозрачное изображение.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, если успешно; в противном случае — NULL. Возвращаемый список содержит только один образ.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_CREATEDRAGIMAGE](/windows/desktop/Controls/hdm-createdragimage), как описано в пакете Windows SDK. Он предназначен для поддержки заголовка элемента операции перетаскивания.

`CImageList` Объекта, к которому точки возвращенный указатель является временным и будет удален в следующей обработки времени простоя.

##  <a name="deleteitem"></a>  CHeaderCtrl::DeleteItem

Удаляет элемент из элемента управления заголовка.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Указывает отсчитываемый от нуля индекс элемента для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

##  <a name="drawitem"></a>  CHeaderCtrl::DrawItem

Вызывается платформой при изменении внешнего вида изменении пользовательской отрисовки заголовка элемента управления.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) структуры, описывающий элемент для рисования.

### <a name="remarks"></a>Примечания

`itemAction` Членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CHeaderCtrl` объекта.

Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* перед этим членом завершении функции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

##  <a name="editfilter"></a>  CHeaderCtrl::EditFilter

Начинает внесение указанного фильтра элемента управления заголовка.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Параметры

*nColumn*<br/>
Столбец для изменения.

*bDiscardChanges*<br/>
Если пользователь находится в процессе редактирования фильтра значение, указывающее способ обработки пользователь редактирования изменения при [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter) отправляется сообщение.

Укажите значение TRUE, чтобы отменить изменения, внесенные пользователем, или значение FALSE, чтобы принять изменения, внесенные пользователем.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщение Win32 [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

##  <a name="getbitmapmargin"></a>  CHeaderCtrl::GetBitmapMargin

Получает ширину поля растрового изображения в элементе управления заголовка.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина поля растрового изображения в пикселях.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_GETBITMAPMARGIN](/windows/desktop/Controls/hdm-getbitmapmargin), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

##  <a name="getfocuseditem"></a>  CHeaderCtrl::GetFocusedItem

Получает индекс элемента, который имеет фокус в текущий элемент управления заголовка.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента заголовка, который имеет фокус.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_GETFOCUSEDITEM](/windows/desktop/Controls/hdm-getfocuseditem) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода показано `SetFocusedItem` и `GetFocusedItem` методы. В предыдущем разделе кода мы создали заголовок элемента управления с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. В следующем примере задает и затем подтверждает заголовок последнего столбца как элемент фокус.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="getimagelist"></a>  CHeaderCtrl::GetImageList

Возвращает дескриптор списка изображений, используемый для рисования элементов заголовка в элементе управления заголовка.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_GETIMAGELIST](/windows/desktop/Controls/hdm-getimagelist), как описано в пакете Windows SDK. `CImageList` Объекта, к которому точки возвращенный указатель является временным и будет удален в следующей обработки времени простоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

##  <a name="getitem"></a>  CHeaderCtrl::GetItem

Извлекает сведения об элементе управления заголовка.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Указывает отсчитываемый от нуля индекс извлекаемого элемента.

*pHeaderItem*<br/>
Указатель на [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) структуру, которая получает новый элемент. Эта структура используется с `InsertItem` и `SetItem` функций-членов. Установлены все флаги `mask` элемент убедитесь, что значения в соответствующих элементах должным образом заполняются при возврате. Если `mask` элемента устанавливается равным нулю, значения в других элементах структура не имеет смысла.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

##  <a name="getitemcount"></a>  CHeaderCtrl::GetItemCount

Получает число элементов в элементе управления заголовка.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов управления заголовка, если выполнение прошло успешно; в противном случае - 1.

### <a name="example"></a>Пример

  См. в примере [CHeaderCtrl::DeleteItem](#deleteitem).

##  <a name="getitemdropdownrect"></a>  CHeaderCtrl::GetItemDropDownRect

Получает ограничивающий прямоугольник кнопки раскрывающегося списка для элемента заголовка в элементе управления текущего заголовка.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iItem*|[in] Отсчитываемый от нуля индекс, стиль которого является HDF_SPLITBUTTON ю элемента заголовка. Дополнительные сведения см. в разделе `fmt` членом [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) структуры.|
|*lpRect*|[out] Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру для получения ограничивающего прямоугольника сведения.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если функция выполнена успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_GETITEMDROPDOWNRECT](/windows/desktop/Controls/hdm-getitemdropdownrect) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода показано `GetItemDropDownRect` метод. В предыдущем разделе кода мы создали заголовок элемента управления с пятью столбцами. В следующем примере кода рисует объемный прямоугольник вокруг места в первом столбце, который зарезервирован для раскрывающегося списка кнопки заголовка.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

##  <a name="getitemrect"></a>  CHeaderCtrl::GetItemRect

Получает ограничивающий прямоугольник для данного элемента в элементе управления заголовка.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый от нуля индекс элемента управления заголовка.

*lpRect*<br/>
Указатель на адрес [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает данные ограничивающий прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Этот метод реализует поведение сообщение Win32 [HDM_GETITEMRECT](/windows/desktop/Controls/hdm-getitemrect), как описано в пакете Windows SDK.

##  <a name="getorderarray"></a>  CHeaderCtrl::GetOrderArray

Получает порядок элементов в элементе заголовка слева направо.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Параметры

*piArray*<br/>
Указатель на адрес буфера, который получает значения индекса из элементов в элементе управления заголовка, в том порядке, в котором они появляются в направлении слева направо.

*iCount*<br/>
Число элементов управления заголовка. Должно быть неотрицательным.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_GETORDERARRAY](/windows/desktop/Controls/hdm-getorderarray), как описано в пакете Windows SDK. Он предназначен для поддержки упорядочение элементов заголовка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

##  <a name="getoverflowrect"></a>  CHeaderCtrl::GetOverflowRect

Получает ограничивающий прямоугольник кнопки переполнения в текущем элементе управления заголовком.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpRect*|[out] Указатель на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает данные ограничивающий прямоугольник.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если функция выполнена успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если элемент управления заголовка содержит больше элементов, чем могут отображаться одновременно, элемент управления может отображать кнопки переполнения, прокручивает к элементам, которые не видны. Элемент управления заголовка должен иметь HDS_OVERFLOW и HDF_SPLITBUTTON ю стили для отображения кнопки переполнения. Ограничивающий прямоугольник включает кнопку переполнения и существует только в том случае, если отображается кнопка переполнения. Дополнительные сведения см. в разделе [стили элемента управления заголовка](/windows/desktop/Controls/header-control-styles).

Этот метод отправляет [HDM_GETOVERFLOWRECT](/windows/desktop/Controls/hdm-getoverflowrect) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода показано `GetOverflowRect` метод. В предыдущем разделе кода мы создали заголовок элемента управления с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. Если некоторые столбцы не отображаются, в элементе управления заголовком Рисует кнопку переполнения. В следующем примере кода рисует объемный прямоугольник вокруг расположение кнопки переполнения.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

##  <a name="hittest"></a>  CHeaderCtrl::HitTest

Определяет, какой элемент заголовка, если таковые имеются, находится в заданной точке.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*phdhti*|[in, out] Указатель на [HDHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_hd_hittestinfo) структура, которая указывает точка для проверки и получает результаты теста.|

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента заголовка, если таковое имеется, в указанной позиции; в противном случае — значение -1.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_HITTEST](/windows/desktop/Controls/hdm-hittest) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода показано `HitTest` метод. В предыдущем разделе этого примера кода мы создали заголовок элемента управления с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. В этом примере возвращает индекс столбца, если она видна и -1, если столбец не отображается.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

##  <a name="insertitem"></a>  CHeaderCtrl::InsertItem

Вставляет новый элемент в элемент управления "Заголовок" по указанному индексу.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Отсчитываемый от нуля индекс вставляемого элемента. Если значение равно нулю, элемент вставляется в начале заголовка элемента управления. Если значение превышает максимальное значение, элемент вставляется в конец элемента управления заголовка.

*phdi*<br/>
Указатель на [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) структуру, содержащую сведения об элементе для вставки.

### <a name="return-value"></a>Возвращаемое значение

Индекс нового элемента, если выполнение прошло успешно; в противном случае - 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

##  <a name="layout"></a>  CHeaderCtrl::Layout

Извлекает размер и положение элемента управления заголовка в пределах заданного прямоугольника.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Параметры

*pHeaderLayout*<br/>
Указатель на [HDLAYOUT](/windows/desktop/api/commctrl/ns-commctrl-_hd_layout) структуру, которая содержит сведения, используемые для задания, размер и положение элемента управления заголовка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция используется для определения соответствующего измерения для нового элемента управления заголовка, который должен занимать заданного прямоугольника.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

##  <a name="ordertoindex"></a>  CHeaderCtrl::OrderToIndex

Получает значение индекса для элемента в зависимости от их порядка в элементе управления заголовком.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Параметры

*nOrder*<br/>
Отсчитываемый от нуля порядок, элемент отображается в элементе управления заголовка слева направо.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента, на основании их порядка в элементе управления заголовком. Индекс подсчитывает слева направо, начиная с 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение макроса Win32 [HDM_ORDERTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb775355), как описано в пакете Windows SDK. Он предназначен для поддержки упорядочение элементов заголовка.

##  <a name="setbitmapmargin"></a>  CHeaderCtrl::SetBitmapMargin

Задает ширину поля растрового изображения в элементе управления заголовка.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина в пикселях, поля, которая окружает растрового изображения в пределах существующего элемента управления заголовка.

### <a name="return-value"></a>Возвращаемое значение

Ширина поля растрового изображения в пикселях.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_SETBITMAPMARGIN](/windows/desktop/Controls/hdm-setbitmapmargin), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

##  <a name="setfilterchangetimeout"></a>  CHeaderCtrl::SetFilterChangeTimeout

Задает интервал времени ожидания между временем изменений в силу в атрибуты фильтра и учет [HDN_FILTERCHANGE](/windows/desktop/Controls/hdn-filterchange) уведомлений.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Параметры

*dwTimeOut*<br/>
Значение времени ожидания в миллисекундах.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента управления фильтра изменяется.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_SETFILTERCHANGETIMEOUT](/windows/desktop/Controls/hdm-setfilterchangetimeout), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

##  <a name="setfocuseditem"></a>  CHeaderCtrl::SetFocusedItem

Устанавливает фокус на элемент указанного заголовка в элементе управления текущего заголовка.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iItem*|[in] Отсчитываемый от нуля индекс элемента заголовка.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [HDM_SETFOCUSEDITEM](/windows/desktop/Controls/hdm-setfocuseditem) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

В следующем примере кода показано `SetFocusedItem` и `GetFocusedItem` методы. В предыдущем разделе кода мы создали заголовок элемента управления с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. В следующем примере задает и затем подтверждает заголовок последнего столбца как элемент фокус.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="sethotdivider"></a>  CHeaderCtrl::SetHotDivider

Изменения, перетащите разделитель между элементы заголовка, чтобы вручную и drop для элемента заголовка.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Положение указателя. Элемент управления заголовка выделяет соответствующий разделитель на основе положения указателя.

*nIndex*<br/>
Индекс выделенной разделителя.

### <a name="return-value"></a>Возвращаемое значение

Индекс выделенной разделителя.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_SETHOTDIVIDER](/windows/desktop/Controls/hdm-sethotdivider), как описано в пакете Windows SDK. Он предназначен для поддержки заголовка элемента операции перетаскивания.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

##  <a name="setimagelist"></a>  CHeaderCtrl::SetImageList

Назначает элемент управления заголовка списка изображений.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*pImageList*<br/>
Указатель на `CImageList` объект, содержащий список изображений, присваиваемое в элементе управления заголовком.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, ранее назначенные элементу управления заголовка.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [HDM_SETIMAGELIST](/windows/desktop/Controls/hdm-setimagelist), как описано в пакете Windows SDK. `CImageList` Объекта, к которому точки возвращенный указатель является временным и будет удален в следующей обработки времени простоя.

### <a name="example"></a>Пример

  См. в примере [CHeaderCtrl::GetImageList](#getimagelist).

##  <a name="setitem"></a>  CHeaderCtrl::SetItem

Устанавливает атрибуты указанного элемента в элементе управления заголовка.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Отсчитываемый от нуля индекс элемента для обработки.

*pHeaderItem*<br/>
Указатель на [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) структуру, содержащую сведения о новый элемент.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [CHeaderCtrl::GetItem](#getitem).

##  <a name="setorderarray"></a>  CHeaderCtrl::SetOrderArray

Задает слева направо порядок элементов в элементе управления заголовка.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Параметры

*iCount*<br/>
Число элементов управления заголовка.

*piArray*<br/>
Указатель на адрес буфера, который получает значения индекса из элементов в элементе управления заголовка, в том порядке, в котором они появляются в направлении слева направо.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение макроса Win32 [HDM_SETORDERARRAY](/windows/desktop/Controls/hdm-setorderarray), как описано в пакете Windows SDK. Он предназначен для поддержки упорядочение элементов заголовка.

### <a name="example"></a>Пример

  См. в примере [CHeaderCtrl::GetOrderArray](#getorderarray).

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CTabCtrl](../../mfc/reference/ctabctrl-class.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)<br/>
[Класс CImageList](../../mfc/reference/cimagelist-class.md)
