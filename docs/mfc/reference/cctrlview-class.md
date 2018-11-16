---
title: Класс CCtrlView
ms.date: 11/04/2016
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
ms.openlocfilehash: bc202afa357dcb9d75a0dd73a3128b7b3f0cc14e
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693403"
---
# <a name="cctrlview-class"></a>Класс CCtrlView

Адаптирует архитектуру "документ-представление" для распространенных элементов управления, поддерживаемых Windows 98 и Windows NT (версии 3.51 и более поздние).

## <a name="syntax"></a>Синтаксис

```
class CCtrlView : public CView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|Создает объект `CCtrlView`.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[CCtrlView::OnDraw](#ondraw)|Вызывается платформой для рисования с помощью заданного контекста устройств.|
|[CCtrlView::PreCreateWindow](#precreatewindow)|Вызывается до создания окна Windows, присоединенного к данному объекту класса `CCtrlView`.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Содержит стиль по умолчанию для класса представления.|
|[CCtrlView::m_strClass](#m_strclass)|Содержит имя класса Windows для класса представления.|

## <a name="remarks"></a>Примечания

Класс `CCtrlView` и его производные [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), и [CRichEditView](../../mfc/reference/cricheditview-class.md), адаптировать архитектуру представления документов, чтобы новые общие элементы управления поддерживаются Windows 95/98 и Windows NT 3.51 и более поздних версиях. Дополнительные сведения о архитектуру представления документов, см. в разделе [архитектуры Document/View](../../mfc/document-view-architecture.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cctrlview"></a>  CCtrlView::CCtrlView

Создает объект `CCtrlView`.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*lpszClass*<br/>
Имя класса Windows класса представления.

*dwStyle*<br/>
Стиль класса представления.

### <a name="remarks"></a>Примечания

Конструктор вызывается платформой при создании нового окна области или разделить окна. Переопределить [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) для инициализации представления после присоединения документа. Вызовите [CWnd::Create](../../mfc/reference/cwnd-class.md#create) или [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) для создания объекта Windows.

##  <a name="m_strclass"></a>  CCtrlView::m_strClass

Содержит имя класса Windows для класса представления.

```
CString m_strClass;
```

##  <a name="m_dwdefaultstyle"></a>  CCtrlView::m_dwDefaultStyle

Содержит стиль по умолчанию для класса представления.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>Примечания

Этот стиль применяется при создании окна.

##  <a name="ondraw"></a>  CCtrlView::OnDraw

Вызывается платформой для отрисовки содержимого `CCtrlView` с помощью заданного контекста устройств.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства, в котором происходит рисование.

### <a name="remarks"></a>Примечания

`OnDraw` обычно вызывается для отображения на экране, передача контекста экрана устройства, указываемого параметром *pDC*.

##  <a name="precreatewindow"></a>  CCtrlView::PreCreateWindow

Вызывается до создания окна Windows, присоединенного к данному объекту класса `CWnd`.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Объект [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если следует продолжить создание окна; 0, указывающее на ошибку создания.

### <a name="remarks"></a>Примечания

Никогда не вызывать эту функцию напрямую.

Реализация по умолчанию эта функция проверяет имя класса окна значение NULL и заменяет соответствующее значение по умолчанию. Переопределите эту функцию-член для изменения `CREATESTRUCT` структуры перед созданием окна.

Каждый класс, производный от `CCtrlView` добавляет свои собственные функции для его переопределения `PreCreateWindow`. По умолчанию эти наследниками `PreCreateWindow` не документированы. Чтобы определить, стили, подходящие для каждого класса и взаимозависимости между стилями, можно просмотреть исходный код MFC для базового класса приложения. Если вы решили переопределить `PreCreateWindow`, можно определить, обеспечивают ли стилей, которые используются в базовом классе приложения необходимые функции, используя информацию, собранную из исходного кода MFC.

Дополнительные сведения об изменении стилей окна, см. в разделе [изменение стилей окна созданного MFC](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>См. также

[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CTreeView](../../mfc/reference/ctreeview-class.md)<br/>
[Класс CListView](../../mfc/reference/clistview-class.md)<br/>
[Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
