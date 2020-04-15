---
title: Класс CAtlPreviewCtrlImpl
ms.date: 11/04/2016
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
ms.openlocfilehash: 1ccd01bc4d48dc088538f4799b595cce3fb910ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321358"
---
# <a name="catlpreviewctrlimpl-class"></a>Класс CAtlPreviewCtrlImpl

Этот класс представляет собой реализацию окна ATL, которое помещается на окно хоста, предоставляемое Shell для Rich Preview.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::::CAtlPreviewCtrlImpl](#dtor)|Уничтожает объект управления предварительным просмотром.|
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Строит объект управления предварительным просмотром.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::Создание](#create)|Для создания окна Windows был вызван обработчик Rich Preview.|
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Вызывается Rich Preview обработчик, когда он должен уничтожить этот контроль.|
|[CAtlPreviewCtrlImpl:Фокус](#focus)|Устанавливает фокус на этот элемент управления.|
|[CAtlPreviewCtrlImpl::Onpaint](#onpaint)|Обрабатывает WM_PAINT сообщение.|
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Говорит этому элементу перерисовать.|
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Устанавливает новый элемент управления.|
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Вызывается Rich Preview обработчик, когда он должен установить визуальные эффекты богатого содержимого предварительного просмотра.|
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Устанавливает новый прямоугольник для этого элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается инфраструктурой для отобрагиваемого предварительного просмотра.|

### <a name="protected-constants"></a>Защищенные константы

|Имя|Описание|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Фоновый цвет окна предварительного просмотра.|
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Текстовый цвет окна предварительного просмотра.|

## <a name="remarks"></a>Remarks

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL::CWindowImpl\<CAtlPreviewCtrlImpl>](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlpreviewctrlimpl.h

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl

Строит объект управления предварительным просмотром.

```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>CAtlPreviewCtrlImpl::::CAtlPreviewCtrlImpl

Уничтожает объект управления предварительным просмотром.

```
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplcreate"></a><a name="create"></a>CAtlPreviewCtrlImpl::Создание

Для создания окна Windows был вызван обработчик Rich Preview.

```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Ручка к окну хоста, поставляемая Shell для Rich Preview.

*Кнр*<br/>
Определяет начальный размер и положение окна.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimpldestroy"></a><a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy

Вызывается Rich Preview обработчик, когда он должен уничтожить этот контроль.

```
virtual void Destroy();
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint

Вызывается инфраструктурой для отобрагиваемого предварительного просмотра.

```
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>Параметры

*Hdc*<br/>
Ручка к контексту устройства для рисования.

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplfocus"></a><a name="focus"></a>CAtlPreviewCtrlImpl:Фокус

Устанавливает фокус на этот элемент управления.

```
virtual void Focus();
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplm_clrback"></a><a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack

Фоновый цвет окна предварительного просмотра.

```
COLORREF m_clrBack;
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplm_clrtext"></a><a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText

Текстовый цвет окна предварительного просмотра.

```
COLORREF m_clrText;
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplm_plf"></a><a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf

Шрифт, используемый для отображения текста в окне предварительного просмотра.

```
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>CAtlPreviewCtrlImpl::Onpaint

Обрабатывает WM_PAINT сообщение.

```
LRESULT OnPaint(
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*nMsg*<br/>
Установить WM_PAINT.

*wParam*<br/>
Этот параметр не используется.

*lParam*<br/>
Этот параметр не используется.

*bHandled*<br/>
Когда эта функция возвращается, она содержит TRUE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 0.

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplredraw"></a><a name="redraw"></a>CAtlPreviewCtrlImpl::Redraw

Говорит этому элементу перерисовать.

```
virtual void Redraw();
```

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplsethost"></a><a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost

Устанавливает новый элемент управления.

```
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Дескриптор нового родительского окна.

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals

Вызывается Rich Preview обработчик, когда он должен установить визуальные эффекты богатого содержимого предварительного просмотра.

```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>Параметры

*clrBack*<br/>
Фоновый цвет окна предварительного просмотра.

*clrText*<br/>
Текстовый цвет окна предварительного просмотра.

*Plf*<br/>
Шрифт, используемый для отображения текста в окне предварительного просмотра.

### <a name="remarks"></a>Remarks

## <a name="catlpreviewctrlimplsetrect"></a><a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect

Устанавливает новый прямоугольник для этого элемента управления.

```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>Параметры

*Кнр*<br/>
Определяет новый размер и положение элемента предварительного просмотра.

*bRedraw*<br/>
Определяет, следует ли перерисовывать элемент управления.

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
