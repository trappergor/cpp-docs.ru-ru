---
title: Класс CMFCPreviewCtrlImpl
ms.date: 11/04/2016
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
ms.openlocfilehash: f66ed8478023bd42e185da4f21740d1de2536140
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403637"
---
# <a name="cmfcpreviewctrlimpl-class"></a>Класс CMFCPreviewCtrlImpl

Этот класс реализует окно, которое помещается в окне узла, заданного оболочкой для расширенного просмотра.

## <a name="syntax"></a>Синтаксис

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl](#dtor)|Разрушается объект предварительного просмотра элемента управления.|
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Создает объект управления предварительной версии.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::Create](#create)|Перегружен. Вызывается обработчик просмотра широкие возможности для создания окна Windows.|
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Вызывается обработчиком расширенного просмотра, проявляющуюся при необходимости удаления этого элемента управления.|
|[CMFCPreviewCtrlImpl::Focus](#focus)|Устанавливает фокус на элемент управления "поле ввода".|
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Возвращает документ, подключенных к этому элементу управления предварительной версии.|
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Сообщает этот элемент управления для повторной отрисовки поверхности.|
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Вызывается обработчик просмотра, чтобы создать связь между реализацией документа и элемента управления просмотра.|
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Задает новый родительский элемент для данного элемента управления.|
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Вызывается обработчиком расширенного просмотра проявляющуюся при необходимости задать визуальные элементы из широкие возможности просмотра содержимого.|
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Задает новый ограничивающий прямоугольник для данного элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается платформой для визуализации предварительного просмотра.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Цвет фона окна предварительного просмотра.|
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Цвет текста окна предварительного просмотра.|
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Указатель на документ, содержимое которого отображается в элементе управления.|

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl

Создает объект управления предварительной версии.

### <a name="syntax"></a>Синтаксис

CMFCPreviewCtrlImpl();

## <a name="create"></a> CMFCPreviewCtrlImpl::Create

Перегружен. Вызывается обработчик просмотра широкие возможности для создания окна Windows.

### <a name="syntax"></a>Синтаксис

```
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc
);
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc,
   CCreateContext* pContext
);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Дескриптор главного окна, предоставленный оболочкой для расширенного просмотра.

*КНР*<br/>
Задает первоначальный размер и положение окна.

*pContext*<br/>
Указатель на контекст создания.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если создание прошло успешно; в противном случае — значение FALSE.

## <a name="destroy"></a> CMFCPreviewCtrlImpl::Destroy

Вызывается обработчиком расширенного просмотра, проявляющуюся при необходимости удаления этого элемента управления.

### <a name="syntax"></a>Синтаксис

```
virtual void Destroy();
```

## <a name="dopaint"></a> CMFCPreviewCtrlImpl::DoPaint

Вызывается платформой для визуализации предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства для рисования.

## <a name="focus"></a> CMFCPreviewCtrlImpl::Focus

Устанавливает фокус на элемент управления "поле ввода".

### <a name="syntax"></a>Синтаксис

```
virtual void Focus();
```

## <a name="getdocument"></a> CMFCPreviewCtrlImpl::GetDocument

Возвращает документ, подключенных к этому элементу управления предварительной версии.

### <a name="syntax"></a>Синтаксис

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, содержимое которых представлен в элементе управления.

## <a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl::m_clrBackColor

Цвет фона окна предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
COLORREF m_clrBackColor;
```

## <a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl::m_clrTextColor

Цвет текста окна предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
COLORREF m_clrTextColor;
```

## <a name="m_font"></a> CMFCPreviewCtrlImpl::m_font шрифт, используемый для отображения текста в окне предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
CFont m_font;
```

## <a name="m_pdocument"></a> CMFCPreviewCtrlImpl::m_pDocument

Указатель на документ, содержимое которого отображается в элементе управления.

### <a name="syntax"></a>Синтаксис

```
ATL::IDocument* m_pDocument;
```

## <a name="redraw"></a> CMFCPreviewCtrlImpl::Redraw

Сообщает этот элемент управления для повторной отрисовки поверхности.

### <a name="syntax"></a>Синтаксис

```
virtual void Redraw();
```

## <a name="setdocument"></a> CMFCPreviewCtrlImpl::SetDocument

Вызывается обработчик просмотра, чтобы создать связь между реализацией документа и элемента управления просмотра.

### <a name="syntax"></a>Синтаксис

```
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>Параметры

*pDocument*<br/>
Указатель на реализацию документа.

## <a name="sethost"></a> CMFCPreviewCtrlImpl::SetHost

Задает новый родительский элемент для данного элемента управления.

### <a name="syntax"></a>Синтаксис

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Дескриптор нового родительского окна.

## <a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals

Вызывается обработчиком расширенного просмотра проявляющуюся при необходимости задать визуальные элементы из широкие возможности просмотра содержимого.

### <a name="syntax"></a>Синтаксис

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>Параметры

*clrBack*<br/>
Цвет фона окна предварительного просмотра.

*clrText*<br/>
Цвет текста окна предварительного просмотра.

*plf*<br/>
Шрифт, используемый для отображения текста в окне предварительного просмотра.

##  <a name="setrect"></a> CMFCPreviewCtrlImpl::SetRect

Задает новый ограничивающий прямоугольник для данного элемента управления.

### <a name="syntax"></a>Синтаксис

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>Параметры

*КНР*<br/>
Указывает новый размер и положение элемента управления предварительной версии.

*bRedraw*<br/>
Указывает ли перерисовки элемента управления.

### <a name="remarks"></a>Примечания

Обычно новый ограничивающий прямоугольник имеет значение при изменении размера элемента управления ведущего приложения.

## <a name="dtor"></a> CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl

Разрушается объект предварительного просмотра элемента управления.

### <a name="syntax"></a>Синтаксис

```
virtual ~CMFCPreviewCtrlImpl();
```
