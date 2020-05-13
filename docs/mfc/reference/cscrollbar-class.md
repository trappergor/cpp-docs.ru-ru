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
ms.openlocfilehash: 2079e12eccde42fe8c456a7852a029f44ae3cd77
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754400"
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
|[CScrollBar::CScrollBar](#cscrollbar)|Формирует объект `CScrollBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CScrollBar::Создание](#create)|Создает панель прокрутки Windows `CScrollBar` и прикрепляет ее к объекту.|
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Включает или выключает одну или обе стрелки полосы прокрутки.|
|[CScrollBar:GetScrollBarInfo](#getscrollbarinfo)|Извлекает информацию о панели `SCROLLBARINFO` прокрутки с помощью структуры.|
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Извлекает информацию о панели прокрутки.|
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Извлекает предел панели прокрутки|
|[CScrollBar::GetScrollPos](#getscrollpos)|Извлекает текущее положение ползунка.|
|[CScrollBar::GetScrollRange](#getscrollrange)|Получает текущие минимальные и максимальные позиции прокрутки-бара для данной панели прокрутки.|
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Задает сведения о полосе прокрутки.|
|[CScrollBar::SetScrollPos](#setscrollpos)|Устанавливает текущее положение окна прокрутки.|
|[CScrollBar::SetScrollRange](#setscrollrange)|Задает для указанной полосы прокрутки положения минимума и максимума.|
|[CScrollBar::ShowScrollBar](#showscrollbar)|Показывает или скрывает бар прокрутки.|

## <a name="remarks"></a>Remarks

Вы создаете управление прокруткой в два этапа. Сначала позвоните в `CScrollBar` конструктор, `CScrollBar` чтобы построить объект, а затем позвоните в функцию `CScrollBar` члена [Create,](#create) чтобы создать элемент управления прокруткой Windows и прикрепить его к объекту.

При создании `CScrollBar` объекта в диалоговом поле (через диалоговые ресурсы) объект автоматически `CScrollBar` уничтожается при закрытии диалогового окна.

Если вы `CScrollBar` создаете объект в окне, возможно, вам также придется уничтожить его.

При создании `CScrollBar` объекта в стеке он уничтожается автоматически. Если вы `CScrollBar` создаете объект на куче с помощью **новой** функции, необходимо **вызвать удаление** объекта, чтобы уничтожить его, когда пользователь завершает панель прокрутки Windows.

Если вы выделяете `CScrollBar` какую-либо `CScrollBar` память в объекте, переопределить деструктор, чтобы избавиться от выделений.

Для получения соответствующей информации об использовании `CScrollBar`см. [Controls](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cscrollbarcreate"></a><a name="create"></a>CScrollBar::Создание

Создает панель прокрутки Windows `CScrollBar` и прикрепляет ее к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль прокрутки бара. Примените любую комбинацию [стилей прокрутки-бара](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) к панели прокрутки.

*rect*<br/>
Определяет размер и положение панели прокрутки. Может быть `RECT` либо структура, либо `CRect` объект.

*pParentWnd*<br/>
Определяет родительское окно панели прокрутки, `CDialog` обычно объект. Она не должна быть NULL.

*nID*<br/>
Идентификатор управления прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы строите `CScrollBar` объект в два этапа. Во-первых, позвоните в конструктор, который строит `CScrollBar` объект; затем `Create`вызов, который создает и инициализирует связанную `CScrollBar` панель прокрутки Windows и прикрепляет ее к объекту.

Примените следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к панели прокрутки:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

- WS_GROUP К управлению группой

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

## <a name="cscrollbarcscrollbar"></a><a name="cscrollbar"></a>CScrollBar::CScrollBar

Формирует объект `CScrollBar`.

```
CScrollBar();
```

### <a name="remarks"></a>Remarks

После построения объекта `Create` позвоните функции участника для создания и инициализации панели прокрутки Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

## <a name="cscrollbarenablescrollbar"></a><a name="enablescrollbar"></a>CScrollBar::EnableScrollBar

Включает или выключает одну или обе стрелки полосы прокрутки.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>Параметры

*nArrowFlags*<br/>
Определяет, включены или отключены стрелки прокрутки и какие стрелки включены или отключены. Этот параметр может быть одним из следующих значений:

- ESB_ENABLE_BOTH Включает обе стрелки панели прокрутки.

- ESB_DISABLE_LTUP отсрабатывает левую стрелку горизонтальной панели прокрутки или стрелку вверх вертикальной панели прокрутки.

- ESB_DISABLE_RTDN отсрабатывает правую стрелку горизонтальной панели прокрутки или вниз стрелку вертикального прокрутки.

- ESB_DISABLE_BOTH отсрабатывает обе стрелки панели прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если стрелки включены или отключены в указанном виде; в противном случае 0, что указывает на то, что стрелки уже находятся в запрашиваемом состоянии или что произошла ошибка.

### <a name="example"></a>Пример

  Смотрите пример [Для CScrollBar:SetScrollRange](#setscrollrange).

## <a name="cscrollbargetscrollbarinfo"></a><a name="getscrollbarinfo"></a>CScrollBar:GetScrollBarInfo

Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLBARINFO`.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>Параметры

*pScrollInfo*<br/>
Указатель на структуру [SCROLLBARINFO.](/windows/win32/api/winuser/ns-winuser-scrollbarinfo)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена имитирует функциональность [SBM_SCROLLBARINFO](/windows/win32/Controls/sbm-getscrollbarinfo) сообщения, как описано в SDK Windows.

## <a name="cscrollbargetscrollinfo"></a><a name="getscrollinfo"></a>CScrollBar::GetScrollInfo

Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLINFO`.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>Параметры

*lpScrollInfo*<br/>
Указатель на структуру [SCROLLINFO.](/windows/win32/api/winuser/ns-winuser-scrollinfo) Дополнительную информацию об этой структуре можно узнать в SDK Windows.

*nМаск*<br/>
Определяет параметры панели прокрутки для извлечения. Обычное использование, SIF_ALL, определяет сочетание SIF_PAGE, SIF_POS, SIF_TRACKPOS и SIF_RANGE. Дополнительную информацию о значениях nMask смотрите. `SCROLLINFO`

### <a name="return-value"></a>Возвращаемое значение

Если сообщение извлекает какие-либо значения, возврат является правдой. В противном случае, это FALSE.

### <a name="remarks"></a>Remarks

`GetScrollInfo`позволяет приложениям использовать 32-битные позиции прокрутки.

Структура [SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) содержит информацию о панели прокрутки, включая минимальное и максимальное положение прокрутки, размер страницы и положение окна прокрутки (большой палец). Подробнее `SCROLLINFO` об изменении структуры по умолчанию можно просмотреть тему структуры в SDK Windows SDK.

Обработчики сообщений MFC Windows, указывающие положение панели прокрутки, «CWnd::OnHScroll и [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), предоставляют только 16 бит данных о положении. `GetScrollInfo`и `SetScrollInfo` предоставить 32 бита данных о положении прокрутки бара. Таким образом, приложение `GetScrollInfo` может `CWnd::OnHScroll` звонить `CWnd::OnVScroll` при обработке либо или для получения 32-битных данных позиции панели прокрутки.

### <a name="example"></a>Пример

  Смотрите пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrolllimit"></a><a name="getscrolllimit"></a>CScrollBar::GetScrollLimit

Извлекает максимальное положение прокрутки панели прокрутки.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Возвращаемое значение

Определяет максимальное положение панели прокрутки в случае успеха; в противном случае 0.

### <a name="example"></a>Пример

  Смотрите пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrollpos"></a><a name="getscrollpos"></a>CScrollBar::GetScrollPos

Извлекает текущее положение ползунка.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определяет текущее положение окна прокрутки в случае успеха; в противном случае 0.

### <a name="remarks"></a>Remarks

Текущее значение — это относительное значение, которое зависит от текущего диапазона прокрутки. Например, если диапазон прокрутки составляет от 100 до 200, а поле прокрутки находится в середине бара, текущее положение — 150.

### <a name="example"></a>Пример

  Смотрите пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrollrange"></a><a name="getscrollrange"></a>CScrollBar::GetScrollRange

Копирует текущие минимальные и максимальные позиции панели прокрутки для данной панели прокрутки в места, указанные *lpMinPos* и *lpMaxPos.*

```cpp
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>Параметры

*lpMinPos*<br/>
Указывает на рядпеременную переменную, которая должна получить минимальную позицию.

*lpMaxPos*<br/>
Указывает на рядпеременную переменную, которая должна получить максимальную позицию.

### <a name="remarks"></a>Remarks

Диапазон по умолчанию для управления прокруткой является пустым (оба значения 0).

### <a name="example"></a>Пример

  Смотрите пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbarsetscrollinfo"></a><a name="setscrollinfo"></a>CScrollBar::SetScrollInfo

Устанавливает информацию, `SCROLLINFO` которую утверждает структура о панели прокрутки.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*lpScrollInfo*<br/>
Указатель на структуру [SCROLLINFO.](/windows/win32/api/winuser/ns-winuser-scrollinfo)

*bRedraw*<br/>
Определяет, следует ли перерисовывать панель прокрутки, чтобы отразить новую информацию. Если *bRedraw* является правдой, панель прокрутки перерисовывается. Если это FALSE, он не перерисовывается. Панель прокрутки перерисовывается по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращение является правдой. В противном случае, это FALSE.

### <a name="remarks"></a>Remarks

Необходимо учесть значения, требуемые параметрами `SCROLLINFO` структуры, включая значения флага.

Структура `SCROLLINFO` содержит информацию о панели прокрутки, включая минимальное и максимальное положение прокрутки, размер страницы и положение окна прокрутки (большой палец). Дополнительную информацию об изменении структуры по умолчанию можно просмотреть тему структуры [SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

## <a name="cscrollbarsetscrollpos"></a><a name="setscrollpos"></a>CScrollBar::SetScrollPos

Устанавливает текущее положение окна прокрутки в указанное *nPos* и, если указано, перерисовывает панель прокрутки, чтобы отразить новое положение.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Определяет новое положение для окна прокрутки. Она должна находиться в пределах диапазона прокрутки.

*bRedraw*<br/>
Определяет, следует ли перерисовывать панель прокрутки, чтобы отразить новое положение. Если *bRedraw* является правдой, панель прокрутки перерисовывается. Если это FALSE, он не перерисовывается. Панель прокрутки перерисовывается по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Определяет предыдущее положение окна прокрутки в случае успеха; в противном случае 0.

### <a name="remarks"></a>Remarks

Установите *bRedraw* на FALSE всякий раз, когда бар прокрутки будет перерисован последующим вызовом к другой функции, чтобы избежать перерисовки панели прокрутки дважды в течение короткого интервала.

### <a name="example"></a>Пример

  Смотрите пример [Для CScrollBar:SetScrollRange](#setscrollrange).

## <a name="cscrollbarsetscrollrange"></a><a name="setscrollrange"></a>CScrollBar::SetScrollRange

Задает для указанной полосы прокрутки положения минимума и максимума.

```cpp
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*nMinPos*<br/>
Определяет минимальное положение прокрутки.

*nMaxPos*<br/>
Определяет максимальное положение прокрутки.

*bRedraw*<br/>
Определяет, следует ли перерисовывать панель прокрутки, чтобы отразить изменение. Если *bRedraw* является правдой, панель прокрутки перерисована; если FALSE, он не перерисовывается. Он перерисовывается по умолчанию.

### <a name="remarks"></a>Remarks

Установите *nMinPos* и *nMaxPos* до 0, чтобы скрыть стандартные бары прокрутки.

Не вызывайте эту функцию, чтобы скрыть бар прокрутки во время обработки сообщения уведомления прокрутки-бара.

Если вызов `SetScrollRange` немедленно следует за `SetScrollPos` вызовом функции члена, `SetScrollPos` установите *bRedraw* in to 0, чтобы предотвратить дваперектывки панели прокрутки.

Разница между значениями, указанными *nMinPos* и *nMaxPos,* не должна быть больше 32 767. Диапазон по умолчанию для управления прокруткой-бара пуст (как *nMinPos,* так и *nMaxPos* 0).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

## <a name="cscrollbarshowscrollbar"></a><a name="showscrollbar"></a>CScrollBar::ShowScrollBar

Показывает или скрывает бар прокрутки.

```cpp
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Определяет, отображается ли или скрыто бар прокрутки. Если этот параметр является правдой, отображается панель прокрутки; в противном случае он скрыт.

### <a name="remarks"></a>Remarks

Приложение не должно вызывать эту функцию, чтобы скрыть бар прокрутки при обработке сообщения уведомления прокрутки-бара.

### <a name="example"></a>Пример

  Смотрите пример [CScrollBar::Создание](#create).

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CStatic](../../mfc/reference/cstatic-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
