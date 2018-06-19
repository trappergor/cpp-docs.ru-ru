---
title: Класс CAtlPreviewCtrlImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 926076115a19b8c9669ec03958d841f08417e89c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362191"
---
# <a name="catlpreviewctrlimpl-class"></a>Класс CAtlPreviewCtrlImpl
Этот класс представляет собой реализацию ATL окна, которое помещается в окне узла, заданного оболочкой для расширенного просмотра.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|Разрушается объект предварительного просмотра элемента управления.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Создает объект предварительного просмотра элемента управления.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Вызывается обработчиком расширенного просмотра для создания окна Windows.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Вызывается обработчиком расширенного просмотра, когда необходимо удалить этот элемент управления.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|Устанавливает фокус на данный элемент управления "поле ввода".|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|Обрабатывает сообщения WM_PAINT.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Сообщает, этот элемент управления для повторной отрисовки.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Задает новый родительский объект для этого элемента управления.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Вызывается обработчиком расширенного просмотра при необходимости задайте визуальных элементов широкие возможности просмотра содержимого.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Задает ограничивающий прямоугольник для этого элемента управления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается платформой для отрисовки на предварительную версию.|  
  
### <a name="protected-constants"></a>Защищенные константы  
  
|name|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Цвет фона окна предварительного просмотра.|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Цвет текста окна предварительного просмотра.|  

  
## <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl >](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlpreviewctrlimpl.h  
  
##  <a name="catlpreviewctrlimpl"></a>  CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 Создает объект предварительного просмотра элемента управления.  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="dtor"></a>  CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl  
 Разрушается объект предварительного просмотра элемента управления.  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>  CAtlPreviewCtrlImpl::Create  
 Вызывается обработчиком расширенного просмотра для создания окна Windows.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор главного окна, предоставленный оболочкой для расширенного просмотра.  
  
 `prc`  
 Задает начальный размер и положение окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="destroy"></a>  CAtlPreviewCtrlImpl::Destroy  
 Вызывается обработчиком расширенного просмотра, когда необходимо удалить этот элемент управления.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="dopaint"></a>  CAtlPreviewCtrlImpl::DoPaint  
 Вызывается платформой для отрисовки на предварительную версию.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>Параметры  
 `hdc`  
 Дескриптор контекста устройства для рисования.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="focus"></a>  CAtlPreviewCtrlImpl::Focus  
 Устанавливает фокус на данный элемент управления "поле ввода".  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_clrback"></a>  CAtlPreviewCtrlImpl::m_clrBack  
 Цвет фона окна предварительного просмотра.  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_clrtext"></a>  CAtlPreviewCtrlImpl::m_clrText  
 Цвет текста окна предварительного просмотра.  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_plf"></a>  CAtlPreviewCtrlImpl::m_plf  
 Шрифт, используемый для отображения текста в окне предварительного просмотра.  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onpaint"></a>  CAtlPreviewCtrlImpl::OnPaint  
 Обрабатывает сообщения WM_PAINT.  
  
```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Параметры  
 `nMsg`  
 Значение WM_PAINT.  
  
 `wParam`  
 Этот параметр не используется.  
  
 `lParam`  
 Этот параметр не используется.  
  
 `bHandled`  
 Если эта функция возвращает значение, он содержит `TRUE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="redraw"></a>  CAtlPreviewCtrlImpl::Redraw  
 Сообщает, этот элемент управления для повторной отрисовки.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sethost"></a>  CAtlPreviewCtrlImpl::SetHost  
 Задает новый родительский объект для этого элемента управления.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна новый.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpreviewvisuals"></a>  CAtlPreviewCtrlImpl::SetPreviewVisuals  
 Вызывается обработчиком расширенного просмотра при необходимости задайте визуальных элементов широкие возможности просмотра содержимого.  
  
```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```  
  
### <a name="parameters"></a>Параметры  
 `clrBack`  
 Цвет фона окна предварительного просмотра.  
  
 `clrText`  
 Цвет текста окна предварительного просмотра.  
  
 `plf`  
 Шрифт, используемый для отображения текста в окне предварительного просмотра.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setrect"></a>  CAtlPreviewCtrlImpl::SetRect  
 Задает ограничивающий прямоугольник для этого элемента управления.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>Параметры  
 `prc`  
 Указывает новый размер и положение элемента управления для предварительного просмотра.  
  
 `bRedraw`  
 Указывает, следует ли перерисовке элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
