---
title: Класс CHtmlEditView
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: c03d580b1b01fd0d0e858278d8b752c3e4b115b9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413385"
---
# <a name="chtmleditview-class"></a>Класс CHtmlEditView

Предоставляет функции платформы редактирования WebBrowser в контексте архитектуры документов или представлений MFC.

## <a name="syntax"></a>Синтаксис

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Создает объект `CHtmlEditView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CHtmlEditView::Create](#create)|Создает новый объект окна.|
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Возвращает `IHTMLDocument2` интерфейс на текущий документ.|
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Извлекает имя документа по умолчанию для этого представления.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>Требования

**Заголовок:** afxhtml.h

##  <a name="chtmleditview"></a>  CHtmlEditView::CHtmlEditView

Создает объект `CHtmlEditView`.

```
CHtmlEditView();
```

##  <a name="create"></a>  CHtmlEditView::Create

Создает новый объект окна.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
Указывает строку нуль-символом, с именем класса Windows. Имя класса может быть любое имя, зарегистрированное [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальной функции или `RegisterClass` функции Windows. Если значение равно NULL, используется по умолчанию [CFrameWnd](../../mfc/reference/cframewnd-class.md) атрибуты.

*lpszWindowName*<br/>
Указывает символ, завершающаяся нулем строка, представляющая имя окна.

*dwStyle*<br/>
Указывает атрибуты стиля окна. По умолчанию задаются стили WS_VISIBLE и WS_CHILD Windows.

*rect*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структуры, указывающий размер и положение окна. *RectDefault* значение позволяет Windows указать размер и положение нового окна.

*pParentWnd*<br/>
Указатель на родительское окно элемента управления.

*nID*<br/>
Идентификатор представления. По умолчанию значение AFX_IDW_PANE_FIRST.

*pContext*<br/>
Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). Значение NULL по умолчанию.

### <a name="remarks"></a>Примечания

Этот метод также будет вызывать автономной WebBrowser `Navigate` метод для загрузки документа по умолчанию (см. в разделе [CHtmlEditView::GetStartDocument](#getstartdocument)).

##  <a name="getdhtmldocument"></a>  CHtmlEditView::GetDHtmlDocument

Возвращает `IHTMLDocument2` интерфейс на текущий документ.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Параметры

*ppDocument*<br/>
[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) интерфейс.

##  <a name="getstartdocument"></a>  CHtmlEditView::GetStartDocument

Извлекает имя документа по умолчанию для этого представления.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>См. также

[Пример HTMLEdit](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
