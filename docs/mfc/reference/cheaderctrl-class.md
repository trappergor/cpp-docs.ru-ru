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
ms.openlocfilehash: 6b5088526ad2c1f94fdc95ec3b84ab7cf64b59e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366856"
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
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Формирует объект `CHeaderCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Очищает все фильтры для управления заголовком.|
|[CHeaderCtrl::ClearFilter](#clearfilter)|Очищает фильтр для управления заголовком.|
|[CHeaderCtrl::Создание](#create)|Создает элемент управления заголовком и `CHeaderCtrl` прикрепляет его к объекту.|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Создает прозрачную версию изображения элемента в элементе управления заголовком.|
|[CHeaderCtrl::CreateEx](#createex)|Создает элемент управления заголовком с указанными расширенными `CListCtrl` стилями Windows и прикрепляет его к объекту.|
|[CHeaderCtrl::DeleteItem](#deleteitem)|Удаляет элемент из элемента заголовка.|
|[CHeaderCtrl::DrawItem](#drawitem)|Рисует указанный элемент элемента управления заголовком.|
|[CHeaderCtrl::EditFilter](#editfilter)|Начинает редактирование указанного фильтра элемента управления заголовком.|
|[CHeaderCtrl:GetBitmapMargin](#getbitmapmargin)|Извлекает ширину поля битной карты в элемент управления заголовком.|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Получает идентификатор элемента в текущем элементе управления заголовком, который имеет фокус.|
|[CHeaderCtrl:GetImageList](#getimagelist)|Извлекает ручку списка изображений, используемого для рисования элементов заголовка в элементе заголовка.|
|[CHeaderCtrl::GetItem](#getitem)|Извлекает информацию о элементе в элемент управления заголовком.|
|[CHeaderCtrl:GetItemCount](#getitemcount)|Извлекает количество элементов в элементы управления заголовком.|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Получает информацию о прямоугольнике для указанной кнопки выпадения в элемент управления заголовком.|
|[CHeaderCtrl::GetItemRect](#getitemrect)|Извлекает прямоугольник для данного элемента в элементе заголовка.|
|[CHeaderCtrl:GetOrderArray](#getorderarray)|Извлекает слева направо порядок элементов в элементах заголовка.|
|[CHeaderCtrl:GetOverflowRect](#getoverflowrect)|Получает ограничивающий прямоугольник кнопки переполнения для текущего управления заголовком.|
|[CHeaderCtrl::HitTest](#hittest)|Определяет, какой элемент заголовка, если таковой имеется, находится в указанной точке.|
|[CHeaderCtrl::InsertItem](#insertitem)|Вставляет новый элемент в элемент управления заголовком.|
|[CHeaderCtrl::Layout](#layout)|Получает размер и положение элемента управления заголовком в данном прямоугольнике.|
|[CHeaderCtrl:OrderToIndex](#ordertoindex)|Извлекает значение индекса для элемента на основе его порядка в элементе заголовка.|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Устанавливает ширину поля битной карты в элементе управления заголовком.|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Устанавливает интервал тайм-аута между временем изменения в атрибутах фильтра и размещением `HDN_FILTERCHANGE` уведомления.|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Устанавливает фокус на указанный элемент заголовка в текущем элементе управления заголовком.|
|[CHeaderCtrl:SetHotDivider](#sethotdivider)|Изменяйте разделитель между элементами заголовка, чтобы указать ручное перетаскивание и падение элемента заголовка.|
|[CHeaderCtrl:SetImageList](#setimagelist)|Присваивайте список изображений элементу управления заголовком.|
|[CHeaderCtrl:SetItem](#setitem)|Устанавливает атрибуты указанного элемента в элемент управления заголовком.|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Устанавливает порядок элементов слева направо в элементах заголовка.|

## <a name="remarks"></a>Remarks

Элемент управления заголовком — это окно, обычно расположенное над набором столбцов текста или чисел. Он содержит название для каждого столбца, и его можно разделить на части. Пользователь может перетащить разделители, которые разделяют части, чтобы установить ширину каждого столбца. Для иллюстрации элемента управления [Header Controls](/windows/win32/Controls/header-controls)заголовком см.

Этот элемент управления `CHeaderCtrl` (и, следовательно, класс) доступен только для программ, которые работают под Windows 95/98 и Windows NT версии 3.51 и позже.

Функциональность, добавленная для Windows 95/Internet Explorer 4.0 общие элементы управления включает в себя следующее:

- Пользовательский заказ элемента заголовка.

- Перетащите и урон элемента заголовка для переупорядочения элементов заголовка. При создании `CHeaderCtrl` объекта используйте HDS_DRAGDROP стиль.

- Текст столбца заголовка постоянно просматривается во время изобрачив размера столбца. Используйте HDS_FULLDRAG стиль при `CHeaderCtrl` создании объекта.

- Заголовок горячего отслеживания, который выделяет элемент заголовка, когда указатель парит над ним. При создании `CHeaderCtrl` объекта используйте HDS_HOTTRACK стиль.

- Поддержка списка изображений. Элементы заголовка могут содержать `CImageList` изображения, хранящиеся в объекте или тексте.

Для получения дополнительной `CHeaderCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CHeaderCtrl](../../mfc/using-cheaderctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl

Формирует объект `CHeaderCtrl`.

```
CHeaderCtrl();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

## <a name="cheaderctrlclearallfilters"></a><a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters

Очищает все фильтры для управления заголовком.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter) со значением столбца -1, как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

## <a name="cheaderctrlclearfilter"></a><a name="clearfilter"></a>CHeaderCtrl::ClearFilter

Очищает фильтр для управления заголовком.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Параметры

*nКолом*<br/>
Значение столбца, указывающее, какой фильтр очистить.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER,](/windows/win32/Controls/hdm-clearfilter)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

## <a name="cheaderctrlcreate"></a><a name="create"></a>CHeaderCtrl::Создание

Создает элемент управления заголовком и `CHeaderCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления заголовком. Для описания стилей управления заголовком [см.](/windows/win32/Controls/header-control-styles)

*rect*<br/>
Определяет размер и положение элемента управления заголовком. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/previous-versions/dd162897\(v=vs.85\))

*pParentWnd*<br/>
Определяет родительское окно управления заголовком, обычно `CDialog`. Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор элемента управления заголовком.

### <a name="return-value"></a>Возвращаемое значение

Незерно, если инициализация была успешной; в противном случае ноль.

### <a name="remarks"></a>Remarks

Вы строите `CHeaderCtrl` объект в два этапа. Сначала позвоните в конструктор, `Create`а затем вызов, который создает элемент `CHeaderCtrl` управления заголовком и прикрепляет его к объекту.

В дополнение к стилям управления заголовком, вы можете использовать следующие общие стили управления, чтобы определить, как позиции управления заголовком и изменяет себя (см. [Общие стили управления](/windows/win32/Controls/common-control-styles) для получения дополнительной информации):

- CCS_BOTTOM Вызывает, что элемент управления позиционируется в нижней части клиентской области родительского окна и устанавливает ширину родительского окна такой же, как ширина родительского окна.

- CCS_NODIVIDER предотвращает нарисование двухпиксельной подсветки в верхней части элемента управления.

- CCS_NOMOVEY вызывает возможность изогания элемента управления и перемещения себя горизонтально, но не вертикально, в ответ на WM_SIZE сообщение. Если используется стиль CCS_NORESIZE, этот стиль не применяется. Элементы управления заголовком имеют этот стиль по умолчанию.

- CCS_NOPARENTALIGN предотвращает автоматическое перемещение элемента управления в верхнюю или нижнюю часть родительского окна. Вместо этого элемент управления сохраняет свое положение в родительском окне, несмотря на изменения в размере родительского окна. Если используется стиль CCS_TOP или CCS_BOTTOM, высота корректируется по умолчанию, но положение и ширина остаются неизменными.

- CCS_NORESIZE предотвращает использование элемента управления шириной и высотой по умолчанию при установлении его первоначального размера или нового размера. Вместо этого элемент управления использует ширину и высоту, указанные в запросе на создание или размер.

- CCS_TOP Вызывает, что элемент управления позиционируется в верхней части клиентской области родительского окна и устанавливает ширину родительского окна такой же, как ширина родительского окна.

Вы также можете применить следующие стили окна для управления заголовком (см. [Стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) для получения дополнительной информации):

- WS_CHILD создает окно ребенка. Не может быть использован с WS_POPUP стилем.

- WS_VISIBLE создает окно, которое изначально видно.

- WS_DISABLED создает окно, которое изначально отключено.

- WS_GROUP определяет первый элемент управления группой элементов управления, в котором пользователь может перемещаться от одного элемента управления к другому со клавишами стрелки. Все элементы управления, определяемые со стилем WS_GROUP после первого элемента управления принадлежат одной и той же группе. Следующий элемент управления со стилем WS_GROUP завершает группу стилей и запускает следующую группу (т.е. одна группа заканчивается там, где начинается следующая).

- WS_TABSTOP определяет один из любого количества элементов управления, с помощью которых пользователь может перемещаться с помощью ключа TAB. Ключ TAB перемещает пользователя к следующему элементу управления, указанному WS_TABSTOP стилем.

Если вы хотите использовать расширенные стили `Create`окон с вашим управлением, позвоните [CreateEx](#createex) вместо .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

## <a name="cheaderctrlcreateex"></a><a name="createex"></a>CHeaderCtrl::CreateEx

Создает элемент управления (детское окно) `CHeaderCtrl` и ассоциирует его с объектом.

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
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Стиль управления заголовком. Для описания стилей управления заголовком [см.](/windows/win32/Controls/header-control-styles) Смотрите [Создать](#create) список дополнительных стилей.

*rect*<br/>
Ссылка на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` `Create` вместо того, чтобы применять расширенные стили Windows, указанные в предисловии расширенного стиля Windows **WS_EX_.**

## <a name="cheaderctrlcreatedragimage"></a><a name="createdragimage"></a>CHeaderCtrl::CreateDragImage

Создает прозрачную версию изображения элемента в элементе управления заголовком.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс элемента с нулевым уровнем в элементе управления заголовком. Изображение, назначенное этому элементу, является основой для прозрачного изображения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList](../../mfc/reference/cimagelist-class.md) в случае успеха; в противном случае NULL. Возвращается список содержит только одно изображение.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_CREATEDRAGIMAGE,](/windows/win32/Controls/hdm-createdragimage)как описано в SDK Windows. Он предоставляется для поддержки перетаскивания и падения элемента заголовка.

Объект, `CImageList` на который указывает возвращенный указатель, является временным объектом и удаляется при следующей обработке простоя.

## <a name="cheaderctrldeleteitem"></a><a name="deleteitem"></a>CHeaderCtrl::DeleteItem

Удаляет элемент из элемента заголовка.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Уотек нулевого индекса элемента для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

## <a name="cheaderctrldrawitem"></a><a name="drawitem"></a>CHeaderCtrl::DrawItem

Вызывается в рамках, когда визуальный аспект управления заголовком владельца-чертежа изменяется.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) описывающую элемент, который будет окрашен.

### <a name="remarks"></a>Remarks

Член `itemAction` `DRAWITEMSTRUCT` структуры определяет действие чертежа, которое должно быть выполнено.

По умолчанию эта функция-член ничего не делает. Переопределить эту функцию элемента для `CHeaderCtrl` реализации чертежа для объекта владельца-рисования.

Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста дисплея, поставляемые в *lpDrawItemStruct,* прежде чем эта функция участника прекратится.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

## <a name="cheaderctrleditfilter"></a><a name="editfilter"></a>CHeaderCtrl::EditFilter

Начинает отсекречивать указанный фильтр элемента управления заголовком.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Параметры

*nКолом*<br/>
Колонка для отослаить.

*bDiscardChanges*<br/>
Значение, которое определяет, как обрабатывать изменения редактирования пользователя, если пользователь находится в процессе редактирования фильтра при отправке [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter) сообщения.

Укажите TRUE, чтобы отказаться от изменений, внесенных пользователем, или FALSE, чтобы принять изменения, внесенные пользователем.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод реализует поведение сообщения Win32 [HDM_EDITFILTER,](/windows/win32/Controls/hdm-editfilter)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

## <a name="cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a>CHeaderCtrl:GetBitmapMargin

Извлекает ширину поля битной карты в элемент управления заголовком.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина поля биткарты в пикселях.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_GETBITMAPMARGIN,](/windows/win32/Controls/hdm-getbitmapmargin)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

## <a name="cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem

Получает индекс элемента, который имеет фокус в текущем элементе управления заголовком.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс элемента заголовка, который имеет фокус.

### <a name="remarks"></a>Remarks

Этот метод отправляет [HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_headerCtrl`переменную, которая используется для доступа к текущему элементу управления заголовком. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

Следующий пример кода `SetFocusedItem` демонстрирует `GetFocusedItem` и методы. В предыдущем разделе кода мы создали элемент управления заголовком с пятью столбцов. Тем не менее, можно перетащить сепаратор столбца, чтобы столбец не был виден. Следующий пример устанавливает, а затем подтверждает последний заголовок столбца в качестве элемента фокусировки.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlgetimagelist"></a><a name="getimagelist"></a>CHeaderCtrl:GetImageList

Извлекает ручку списка изображений, используемого для рисования элементов заголовка в элементе заголовка.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList.](../../mfc/reference/cimagelist-class.md)

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_GETIMAGELIST,](/windows/win32/Controls/hdm-getimagelist)как описано в SDK Windows. Объект, `CImageList` на который указывает возвращенный указатель, является временным объектом и удаляется при следующей обработке простоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

## <a name="cheaderctrlgetitem"></a><a name="getitem"></a>CHeaderCtrl::GetItem

Извлекает информацию о элементе управления заголовком.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Уфиксирует нулевой индекс элемента для извлечения.

*pHeaderItem*<br/>
Указатель на структуру [HDITEM,](/windows/win32/api/commctrl/ns-commctrl-hditemw) которая получает новый элемент. Эта структура используется `InsertItem` с `SetItem` функциями и функциями членов. Любые флаги, установленные `mask` в элементе, гарантируют, что значения в соответствующих элементах должным образом заполняются по возвращении. Если `mask` элемент настроен до нуля, значения в других элементах структуры бессмысленны.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

## <a name="cheaderctrlgetitemcount"></a><a name="getitemcount"></a>CHeaderCtrl:GetItemCount

Извлекает количество элементов в элементы управления заголовком.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов управления заголовком в случае успеха; в противном случае - 1.

### <a name="example"></a>Пример

  Смотрите пример [CHeaderCtrl::DeleteItem](#deleteitem).

## <a name="cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect

Получает ограничивающий прямоугольник кнопки выпадения вниз для элемента заголовка в текущем элементе управления заголовком.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iItem*|(в) Нулевой индекс элемента заголовка, стиль которого находится HDF_SPLITBUTTON. Для получения дополнительной `fmt` информации [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) см.|
|*lpRect*|(ваут) Указатель на структуру [RECT](/previous-versions/dd162897\(v=vs.85\)) для получения информации о граничащих прямоугольниках.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если эта функция является успешной; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_headerCtrl`переменную, которая используется для доступа к текущему элементу управления заголовком. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

Следующий пример кода `GetItemDropDownRect` демонстрирует метод. В предыдущем разделе кода мы создали элемент управления заголовком с пятью столбцов. Следующий пример кода рисует 3D прямоугольник вокруг местоположения на первом столбце, зарезервированном для кнопки выпадения заголовка.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

## <a name="cheaderctrlgetitemrect"></a><a name="getitemrect"></a>CHeaderCtrl::GetItemRect

Извлекает прямоугольник для данного элемента в элементе заголовка.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс с нулевым уровнем элемента управления заголовком.

*lpRect*<br/>
Указатель на адрес структуры [RECT,](/previous-versions/dd162897\(v=vs.85\)) которая получает информацию о граничащих прямоугольниках.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Этот метод реализует поведение сообщения Win32 [HDM_GETITEMRECT,](/windows/win32/Controls/hdm-getitemrect)как описано в SDK Windows.

## <a name="cheaderctrlgetorderarray"></a><a name="getorderarray"></a>CHeaderCtrl:GetOrderArray

Извлекает слева направо порядок элементов в элементах заголовка.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Параметры

*piArray*<br/>
Указатель на адрес буфера, который получает значения индекса элементов в управлении заголовком, в порядке, в котором они отображаются слева направо.

*iCount*<br/>
Количество элементов управления заголовком. Должно быть, неотрицательный.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_GETORDERARRAY,](/windows/win32/Controls/hdm-getorderarray)как описано в SDK Windows. Он предоставляется для поддержки заказа заголовка элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

## <a name="cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a>CHeaderCtrl:GetOverflowRect

Получает ограничивающий прямоугольник кнопки переполнения текущего элемента управления заголовком.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*lpRect*|(ваут) Указатель на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) которая получает информацию о граничащих прямоугольниках.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если эта функция является успешной; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Если элемент управления заголовком содержит больше элементов, чем может быть одновременно отображено, элемент ы может отображать кнопку переполнения, которая прокручивается к элементам, которые не видны. Управление заголовком должно иметь HDS_OVERFLOW и HDF_SPLITBUTTON стили для отображения кнопки переполнения. Прямоугольник, ограничивающий, закрывает кнопку переполнения и существует только при отображении кнопки переполнения. Для получения дополнительной [Header Control Styles](/windows/win32/Controls/header-control-styles)информации см.

Этот метод отправляет [HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_headerCtrl`переменную, которая используется для доступа к текущему элементу управления заголовком. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

Следующий пример кода `GetOverflowRect` демонстрирует метод. В предыдущем разделе кода мы создали элемент управления заголовком с пятью столбцов. Тем не менее, можно перетащить сепаратор столбца, чтобы столбец не был виден. Если некоторые столбцы не видны, управление заголовком рисует кнопку переполнения. Следующий пример кода рисует 3D прямоугольник вокруг расположения кнопки переполнения.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

## <a name="cheaderctrlhittest"></a><a name="hittest"></a>CHeaderCtrl::HitTest

Определяет, какой элемент заголовка, если таковой имеется, находится в указанной точке.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*phdhti*|(в, вне) Указатель на структуру [HDHITTESTINFO,](/windows/win32/api/commctrl/ns-commctrl-hdhittestinfo) которая определяет точку для тестирования и получает результаты теста.|

### <a name="return-value"></a>Возвращаемое значение

Индекс заголовка на нулевой основе, если таковой имеется, в указанном положении; в противном случае, -1.

### <a name="remarks"></a>Remarks

Этот метод отправляет [HDM_HITTEST](/windows/win32/Controls/hdm-hittest) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_headerCtrl`переменную, которая используется для доступа к текущему элементу управления заголовком. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

Следующий пример кода `HitTest` демонстрирует метод. В предыдущем разделе этого примера кода мы создали элемент управления заголовком с пятью столбцов. Тем не менее, можно перетащить сепаратор столбца, чтобы столбец не был виден. Этот пример сообщает индекс столбца, если он виден, и -1, если столбец не виден.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

## <a name="cheaderctrlinsertitem"></a><a name="insertitem"></a>CHeaderCtrl::InsertItem

Вставляет новый элемент в элемент управления заголовком в указанном индексе.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Отсчитываемый от нуля индекс вставляемого элемента. Если значение равно нулю, элемент вставляется в начале элемента заголовка. Если значение превышает максимальное значение, элемент вставляется в конце элемента управления заголовком.

*phdi*<br/>
Указатель на структуру [HDITEM,](/windows/win32/api/commctrl/ns-commctrl-hditemw) содержащую информацию о элементе, который будет вставлен.

### <a name="return-value"></a>Возвращаемое значение

Индекс новинки в случае успеха; в противном случае - 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

## <a name="cheaderctrllayout"></a><a name="layout"></a>CHeaderCtrl::Layout

Получает размер и положение элемента управления заголовком в данном прямоугольнике.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Параметры

*pHeaderLayout*<br/>
Указатель на структуру [HDLAYOUT,](/windows/win32/api/commctrl/ns-commctrl-hdlayout) которая содержит информацию, используемую для настройки размера и положения элемента управления заголовком.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция используется для определения соответствующих размеров для нового элемента управления заголовком, который должен занимать данный прямоугольник.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

## <a name="cheaderctrlordertoindex"></a><a name="ordertoindex"></a>CHeaderCtrl:OrderToIndex

Извлекает значение индекса для элемента на основе его порядка в элементе заголовка.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Параметры

*nOrder*<br/>
Нулевой ордер, который элемент отображается в элементе заголовка, слева направо.

### <a name="return-value"></a>Возвращаемое значение

Индекс элемента, основанный на его порядке в управлении заголовком. Индекс считается слева направо, начиная с 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение [макроHDM_ORDERTOINDEX](/windows/win32/controls/hdm-ordertoindex)Win32, как описано в Windows SDK. Он предоставляется для поддержки заказа заголовка элемента.

## <a name="cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin

Устанавливает ширину поля битной карты в элементе управления заголовком.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина, указанная в пикселях, поля, которая окружает битную карту в существующем элементе управления заголовком.

### <a name="return-value"></a>Возвращаемое значение

Ширина поля биткарты в пикселях.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_SETBITMAPMARGIN,](/windows/win32/Controls/hdm-setbitmapmargin)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

## <a name="cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout

Устанавливает интервал тайм-аута между временем изменения в атрибутах фильтра и размещением [HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange) уведомления.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Параметры

*dwTimeOut*<br/>
Значение тайм-аута в миллисекундах.

### <a name="return-value"></a>Возвращаемое значение

Изменяется индекс управления фильтром.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_SETFILTERCHANGETIMEOUT,](/windows/win32/Controls/hdm-setfilterchangetimeout)как описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

## <a name="cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem

Устанавливает фокус на указанный элемент заголовка в текущем элементе управления заголовком.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*iItem*|(в) Нулевой индекс элемента заголовка.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

Следующий пример кода определяет `m_headerCtrl`переменную, которая используется для доступа к текущему элементу управления заголовком. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Пример

Следующий пример кода `SetFocusedItem` демонстрирует `GetFocusedItem` и методы. В предыдущем разделе кода мы создали элемент управления заголовком с пятью столбцов. Тем не менее, можно перетащить сепаратор столбца, чтобы столбец не был виден. Следующий пример устанавливает, а затем подтверждает последний заголовок столбца в качестве элемента фокусировки.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlsethotdivider"></a><a name="sethotdivider"></a>CHeaderCtrl:SetHotDivider

Изменяйте разделитель между элементами заголовка, чтобы указать ручное перетаскивание и падение элемента заголовка.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Положение указателя. Контроль заголовка выделяет соответствующий разделитель в зависимости от положения указателя.

*Nindex*<br/>
Индекс выделенного разделителя.

### <a name="return-value"></a>Возвращаемое значение

Индекс выделенного разделителя.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_SETHOTDIVIDER,](/windows/win32/Controls/hdm-sethotdivider)как описано в SDK Windows. Он предоставляется для поддержки перетаскивания и падения элемента заголовка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

## <a name="cheaderctrlsetimagelist"></a><a name="setimagelist"></a>CHeaderCtrl:SetImageList

Присваивайте список изображений элементу управления заголовком.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Параметры

*pImageList*<br/>
Указатель на `CImageList` объект, содержащий список изображений, который будет назначен элементу управления заголовком.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CImageList,](../../mfc/reference/cimagelist-class.md) ранее назначенный элементу управления заголовком.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение сообщения Win32 [HDM_SETIMAGELIST,](/windows/win32/Controls/hdm-setimagelist)как описано в SDK Windows. Объект, `CImageList` на который указывает возвращенный указатель, является временным объектом и удаляется при следующей обработке простоя.

### <a name="example"></a>Пример

  Смотрите пример [для CHeaderCtrl::GetImageList](#getimagelist).

## <a name="cheaderctrlsetitem"></a><a name="setitem"></a>CHeaderCtrl:SetItem

Устанавливает атрибуты указанного элемента в элемент управления заголовком.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Индекс нулевой основе элемента, которым нужно манипулировать.

*pHeaderItem*<br/>
Указатель на структуру [HDITEM,](/windows/win32/api/commctrl/ns-commctrl-hditemw) содержащую информацию о новом элементе.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [для CHeaderCtrl::GetItem](#getitem).

## <a name="cheaderctrlsetorderarray"></a><a name="setorderarray"></a>CHeaderCtrl::SetOrderArray

Устанавливает порядок элементов слева направо в элементах заголовка.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Параметры

*iCount*<br/>
Количество элементов управления заголовком.

*piArray*<br/>
Указатель на адрес буфера, который получает значения индекса элементов в управлении заголовком, в порядке, в котором они отображаются слева направо.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена реализует поведение [макроHDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray)Win32, как описано в Windows SDK. Он предоставляется для поддержки заказа заголовка элемента.

### <a name="example"></a>Пример

  Смотрите пример [для CHeaderCtrl::GetOrderArray](#getorderarray).

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CTabCtrl](../../mfc/reference/ctabctrl-class.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)<br/>
[Класс CImageList](../../mfc/reference/cimagelist-class.md)
