---
title: Класс CScrollBar
ms.date: 11/04/2016
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
ms.openlocfilehash: d677d72b7e758fcdaa7df0e2918e9bbec3e18ee9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263121"
---
# <a name="cscrollbar-class"></a>Класс CScrollBar

Предоставляет функции элемента управления полосой прокрутки Windows.

## <a name="syntax"></a>Синтаксис

```
class CScrollBar : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CScrollBar::CScrollBar](#cscrollbar)|Создает объект `CScrollBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CScrollBar::Create](#create)|Создает полосу прокрутки Windows и присоединяет его к `CScrollBar` объекта.|
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Включает или выключает одну или обе стрелки полосы прокрутки.|
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Извлекает сведения о полосы с помощью прокрутки `SCROLLBARINFO` структуры.|
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Извлекает сведения о полосе прокрутки.|
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Извлекает ограничение полосы прокрутки|
|[CScrollBar::GetScrollPos](#getscrollpos)|Извлекает текущее положение ползунка.|
|[CScrollBar::GetScrollRange](#getscrollrange)|Извлекает текущие положения минимальное и максимальное полосы прокрутки для указанной полосы прокрутки.|
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Задает сведения о полосе прокрутки.|
|[CScrollBar::SetScrollPos](#setscrollpos)|Задает текущее положение ползунка.|
|[CScrollBar::SetScrollRange](#setscrollrange)|Задает для указанной полосы прокрутки положения минимума и максимума.|
|[CScrollBar::ShowScrollBar](#showscrollbar)|Показывает или скрывает полосу прокрутки.|

## <a name="remarks"></a>Примечания

Создание элемента управления полосы прокрутки в два этапа. Во-первых, вызовите конструктор `CScrollBar` для создания `CScrollBar` объекта, а затем вызовите [создать](#create) функцию-член для создания элемента управления полосы прокрутки Windows и присоединить его к `CScrollBar` объекта.

Если вы создаете `CScrollBar` объекта в диалоговом окне (с помощью ресурса диалогового окна), `CScrollBar` автоматически удаляются, когда пользователь закрывает диалоговое окно.

Если вы создаете `CScrollBar` объекта в окне, также может потребоваться уничтожить его.

Если вы создаете `CScrollBar` объект в стеке, он будет удален автоматически. При создании `CScrollBar` объект в куче с помощью **новый** функцию, необходимо вызвать **удалить** в объекте уничтожить его, когда пользователь закроет полосу прокрутки Windows.

Если выделять память в `CScrollBar` объекта, переопределить `CScrollBar` деструктор для удаления из выделений.

Дополнительные сведения об использовании `CScrollBar`, см. в разделе [элементов управления](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="create"></a>  CScrollBar::Create

Создает полосу прокрутки Windows и присоединяет его к `CScrollBar` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Указывает прокрутку стиль элемента диаграммы. Применить любое сочетание [стили полосы прокрутки](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) к полосе прокрутки.

*rect*<br/>
Указывает размер полосы прокрутки и положение. Может быть либо `RECT` структуры или `CRect` объекта.

*pParentWnd*<br/>
Указывает прокрутку линейки родительского окна, обычно `CDialog` объекта. Он не должен иметь значение NULL.

*nID*<br/>
Идентификатор элемента управления полосы прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CScrollBar` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CScrollBar` объект; затем вызвать `Create`, который создает и инициализирует связанный полосу прокрутки Windows и присоединяет его к `CScrollBar` объекта.

Примените следующий [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) полосу прокрутки:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_GROUP для группировки элементов управления

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

##  <a name="cscrollbar"></a>  CScrollBar::CScrollBar

Создает объект `CScrollBar`.

```
CScrollBar();
```

### <a name="remarks"></a>Примечания

После создания объекта, вызовите `Create` функция-член для создания и инициализации полосу прокрутки Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

##  <a name="enablescrollbar"></a>  CScrollBar::EnableScrollBar

Включает или выключает одну или обе стрелки полосы прокрутки.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>Параметры

*nArrowFlags*<br/>
Указывает ли стрелками включены или отключены, и какие стрелки включены или отключены. Этот параметр может принимать одно из следующих значений:

- ESB_ENABLE_BOTH позволяет обе стрелки полосы прокрутки.

- ESB_DISABLE_LTUP отключает стрелку влево для горизонтальной полосы прокрутки или со стрелкой вверх для вертикальной полосы прокрутки.

- ESB_DISABLE_RTDN отключает со стрелкой вправо для горизонтальной полосы прокрутки или стрелку вниз для вертикальной полосы прокрутки.

- ESB_DISABLE_BOTH отключает обе стрелки полосы прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если включены или отключены, как указано; стрелки в противном случае — 0, означающее, что стрелки уже запрошенное состояние или произошла ошибка.

### <a name="example"></a>Пример

  См. в примере [CScrollBar::SetScrollRange](#setscrollrange).

##  <a name="getscrollbarinfo"></a>  CScrollBar::GetScrollBarInfo

Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLBARINFO`.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>Параметры

*pScrollInfo*<br/>
Указатель на [SCROLLBARINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollbarinfo) структуры.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности [SBM_SCROLLBARINFO](/windows/desktop/Controls/sbm-getscrollbarinfo) сообщения, как описано в пакете Windows SDK.

##  <a name="getscrollinfo"></a>  CScrollBar::GetScrollInfo

Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLINFO`.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>Параметры

*lpScrollInfo*<br/>
Указатель на [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) структуры. См. в Windows SDK, Дополнительные сведения об этой структуре.

*nMask*<br/>
Параметры панели прокрутки для извлечения. Типичное применение SIF_ALL, задает сочетание SIF_PAGE, SIF_POS, SIF_TRACKPOS и SIF_RANGE. См. в разделе `SCROLLINFO` Дополнительные сведения о nMask значения.

### <a name="return-value"></a>Возвращаемое значение

Если сообщение получено все значения, возвращаемое значение TRUE. В противном случае — FALSE.

### <a name="remarks"></a>Примечания

`GetScrollInfo` позволяет приложениям использовать позиции прокрутки 32-разрядной.

[SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) структура содержит сведения о полосы прокрутки, включая минимальной и максимальной прокрутки положения, размера страницы и положение ползунка полосы прокрутки (бегунка). См. в разделе `SCROLLINFO` раздел структуры в пакете SDK для Windows, Дополнительные сведения об изменении структуры значения по умолчанию.

Обработчики, которые указывают расположение полосы прокрутки, сообщения MFC Windows [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) и [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), предоставляют только 16 битов данных позиции. `GetScrollInfo` и `SetScrollInfo` предоставляют 32 бита полосы данных позиции прокрутки. Таким образом, приложение может вызвать `GetScrollInfo` при обработке либо `CWnd::OnHScroll` или `CWnd::OnVScroll` для получения данных положение панели прокрутки 32-разрядной.

### <a name="example"></a>Пример

  См. в примере [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrolllimit"></a>  CScrollBar::GetScrollLimit

Получает максимальное положение полосы прокрутки прокрутка.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Возвращаемое значение

Указывает положение полосы прокрутки, если выполнение прошло успешно; в противном случае 0.

### <a name="example"></a>Пример

  См. в примере [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrollpos"></a>  CScrollBar::GetScrollPos

Извлекает текущее положение ползунка.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Задает текущее положение ползунка полосы прокрутки в случае успешного выполнения; в противном случае 0.

### <a name="remarks"></a>Примечания

Текущая позиция находится относительное значение, которое зависит от текущего диапазона прокрутки. Например если полосы прокрутки находится в середине панели прокрутки диапазон — от 100 до 200, текущая позиция находится 150.

### <a name="example"></a>Пример

  См. в примере [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrollrange"></a>  CScrollBar::GetScrollRange

Копирует текущие положения минимальное и максимальное полосы прокрутки для указанной полосы прокрутки в расположениях, указанных *lpMinPos* и *lpMaxPos*.

```
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>Параметры

*lpMinPos*<br/>
Указатель на целочисленную переменную, который должен получить позиции минимума.

*lpMaxPos*<br/>
Указатель на целочисленную переменную, который должен получить положение.

### <a name="remarks"></a>Примечания

Диапазон по умолчанию для элемента управления полосы прокрутки пуст (оба значения равны 0).

### <a name="example"></a>Пример

  См. в примере [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="setscrollinfo"></a>  CScrollBar::SetScrollInfo

Задает сведения, `SCROLLINFO` структура поддерживает о полосе прокрутки.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*lpScrollInfo*<br/>
Указатель на [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) структуры.

*bRedraw*<br/>
Указывает, следует ли заново полосу прокрутки, с учетом новых данных. Если *bRedraw* имеет значение TRUE, перерисовывается полосу прокрутки. Если он имеет значение FALSE, он не будет перерисован. По умолчанию перерисовывается полосу прокрутки.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращается значение TRUE. В противном случае — FALSE.

### <a name="remarks"></a>Примечания

Необходимо указать значения, необходимые `SCROLLINFO` структуру параметров, включая значения флага.

`SCROLLINFO` Структура содержит сведения о полосы прокрутки, включая минимальной и максимальной прокрутки положения, размера страницы и положение ползунка полосы прокрутки (бегунка). См. в разделе [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) раздел структуры в пакете SDK для Windows, Дополнительные сведения об изменении структуры значения по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

##  <a name="setscrollpos"></a>  CScrollBar::SetScrollPos

Задает текущее положение ползунка значению, указанному *nPos* и, если указано, перерисовывает полосу прокрутки в соответствии с новым положением.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Задает новое положение для полосы прокрутки. Он должен быть в пределах диапазона прокрутки.

*bRedraw*<br/>
Указывает, перерисовки ли полосы прокрутки в соответствии с новым положением. Если *bRedraw* имеет значение TRUE, перерисовывается полосу прокрутки. Если он имеет значение FALSE, он не будет перерисован. По умолчанию перерисовывается полосу прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Задает положение предыдущего полосы прокрутки, если выполнение прошло успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Задайте *bRedraw* значение FALSE при каждом полосу прокрутки перерисовывается при последующих вызовах в другую функцию, чтобы избежать необходимости полосы прокрутки, перерисовывается дважды в течение короткого промежутка.

### <a name="example"></a>Пример

  См. в примере [CScrollBar::SetScrollRange](#setscrollrange).

##  <a name="setscrollrange"></a>  CScrollBar::SetScrollRange

Задает для указанной полосы прокрутки положения минимума и максимума.

```
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*nMinPos*<br/>
Указывает минимальное положение прокрутки.

*nMaxPos*<br/>
Указывает максимально позиции прокрутки.

*bRedraw*<br/>
Указывает, перерисовки ли полосы прокрутки в соответствии с изменениями. Если *bRedraw* имеет значение TRUE, перерисовывается полосы прокрутки; Если значение равно FALSE, не перерисовке. Перерисовке по умолчанию.

### <a name="remarks"></a>Примечания

Задайте *nMinPos* и *nMaxPos* равным 0, чтобы скрыть полос прокрутки standard.

Не вызывайте эту функцию, чтобы скрыть полосу прокрутки при обработке сообщения уведомления полосы прокрутки.

Если в вызове `SetScrollRange` сразу за вызов `SetScrollPos` значение функции-члена *bRedraw* в `SetScrollPos` равным 0, чтобы предотвратить перерисовываться дважды полосу прокрутки.

Разница между значениями, заданными с *nMinPos* и *nMaxPos* не должно быть больше 32 767. Диапазон по умолчанию для элемента управления полосы прокрутки пуст (оба *nMinPos* и *nMaxPos* равны 0).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

##  <a name="showscrollbar"></a>  CScrollBar::ShowScrollBar

Показывает или скрывает полосу прокрутки.

```
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Указывает, является ли полоса прокрутки видима или скрыта. Если этот параметр имеет значение TRUE, полоса прокрутки отображается; в противном случае он скрыт.

### <a name="remarks"></a>Примечания

Приложение не должно вызывать эту функцию, чтобы скрыть полосу прокрутки при обработке сообщения уведомления полосы прокрутки.

### <a name="example"></a>Пример

  См. в примере [CScrollBar::Create](#create).

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
