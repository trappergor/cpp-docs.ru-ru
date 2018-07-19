---
title: Класс CAtlPreviewCtrlImpl | Документация Майкрософт
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
ms.openlocfilehash: 9d0d1e35e3c2a7d9467024afdf3d415478cd7de1
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884981"
---
# <a name="catlpreviewctrlimpl-class"></a>Класс CAtlPreviewCtrlImpl
Этот класс является реализацией ATL окна, которое помещается в окне узла, заданного оболочкой для расширенного просмотра.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|Разрушается объект предварительного просмотра элемента управления.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Создает объект управления предварительной версии.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Вызывается обработчик просмотра широкие возможности для создания окна Windows.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Вызывается обработчиком расширенного просмотра, проявляющуюся при необходимости удаления этого элемента управления.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|Устанавливает фокус на элемент управления "поле ввода".|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|Обрабатывает сообщение WM_PAINT.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Сообщает этот элемент управления для повторной отрисовки поверхности.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Задает новый родительский элемент для данного элемента управления.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Вызывается обработчиком расширенного просмотра проявляющуюся при необходимости задать визуальные элементы из широкие возможности просмотра содержимого.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Задает новый ограничивающий прямоугольник для данного элемента управления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается платформой для визуализации предварительного просмотра.|  
  
### <a name="protected-constants"></a>Защищенные константы  
  
|name|Описание:|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
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
 Создает объект управления предварительной версии.  
  
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
 Вызывается обработчик просмотра широкие возможности для создания окна Windows.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>Параметры  
 *hWndParent*  
 Дескриптор главного окна, предоставленный оболочкой для расширенного просмотра.  
  
 *КНР*  
 Задает первоначальный размер и положение окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="destroy"></a>  CAtlPreviewCtrlImpl::Destroy  
 Вызывается обработчиком расширенного просмотра, проявляющуюся при необходимости удаления этого элемента управления.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="dopaint"></a>  CAtlPreviewCtrlImpl::DoPaint  
 Вызывается платформой для визуализации предварительного просмотра.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>Параметры  
 *hdc*  
 Дескриптор контекста устройства для рисования.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="focus"></a>  CAtlPreviewCtrlImpl::Focus  
 Устанавливает фокус на элемент управления "поле ввода".  
  
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
 Обрабатывает сообщение WM_PAINT.  
  
```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Параметры  
 *nMsg*  
 Присвоено WM_PAINT.  
  
 *wParam*  
 Этот параметр не используется.  
  
 *lParam*  
 Этот параметр не используется.  
  
 *bHandled*  
 Когда эта функция возвращает значение, он содержит значение TRUE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="redraw"></a>  CAtlPreviewCtrlImpl::Redraw  
 Сообщает этот элемент управления для повторной отрисовки поверхности.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sethost"></a>  CAtlPreviewCtrlImpl::SetHost  
 Задает новый родительский элемент для данного элемента управления.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 *hWndParent*  
 Дескриптор нового родительского окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpreviewvisuals"></a>  CAtlPreviewCtrlImpl::SetPreviewVisuals  
 Вызывается обработчиком расширенного просмотра проявляющуюся при необходимости задать визуальные элементы из широкие возможности просмотра содержимого.  
  
```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```  
  
### <a name="parameters"></a>Параметры  
 *clrBack*  
 Цвет фона окна предварительного просмотра.  
  
 *clrText*  
 Цвет текста окна предварительного просмотра.  
  
 *plf*  
 Шрифт, используемый для отображения текста в окне предварительного просмотра.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setrect"></a>  CAtlPreviewCtrlImpl::SetRect  
 Задает новый ограничивающий прямоугольник для данного элемента управления.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>Параметры  
 *КНР*  
 Указывает новый размер и положение элемента управления предварительной версии.  
  
 *bRedraw*  
 Указывает ли перерисовки элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
