---
title: "Класс CAtlPreviewCtrlImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlpreviewctrlimpl/ATL::CAtlPreviewCtrlImpl
- CAtlPreviewCtrlImpl
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 979dc23eabc2ba2362f7301fc34ca89016d58f37
ms.lasthandoff: 02/24/2017

---
# <a name="catlpreviewctrlimpl-class"></a>Класс CAtlPreviewCtrlImpl
Этот класс является реализацией ATL окна, которое помещается в окне узла, заданного оболочкой для расширенного просмотра.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|Разрушается объект элемента управления для предварительного просмотра.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Создает объект управления предварительной версии.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Вызывается из обработчика просмотра широкие возможности для создания окна Windows.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Вызывается обработчиком расширенного просмотра, когда необходимо уничтожить этот элемент управления.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|Устанавливает фокус на данный элемент управления.|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|Обрабатывает сообщение WM_PAINT.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Сообщает, этот элемент управления перерисовка.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Устанавливает новый родительский объект для данного элемента управления.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Вызывается обработчиком расширенного просмотра при необходимые для установки отображения широкие возможности просмотра содержимого.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Задает ограничивающий прямоугольник для данного элемента управления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается платформой для подготовки к просмотру в предварительной версии.|  
  
### <a name="protected-constants"></a>Защищенные константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Цвет фона окна предварительного просмотра.|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Цвет текста окно предварительного просмотра.|  

  
## <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl настроек](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlpreviewctrlimpl.h  
  
##  <a name="a-namecatlpreviewctrlimpla--catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 Создает объект управления предварительной версии.  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedtora--catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl  
 Разрушается объект элемента управления для предварительного просмотра.  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecreatea--catlpreviewctrlimplcreate"></a><a name="create"></a>CAtlPreviewCtrlImpl::Create  
 Вызывается из обработчика просмотра широкие возможности для создания окна Windows.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор главного окна, предоставленного оболочкой для расширенного просмотра.  
  
 `prc`  
 Задает начальный размер и положение окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedestroya--catlpreviewctrlimpldestroy"></a><a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy  
 Вызывается обработчиком расширенного просмотра, когда необходимо уничтожить этот элемент управления.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedopainta--catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint  
 Вызывается платформой для подготовки к просмотру в предварительной версии.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>Параметры  
 `hdc`  
 Дескриптор контекста устройства для рисования.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefocusa--catlpreviewctrlimplfocus"></a><a name="focus"></a>CAtlPreviewCtrlImpl::Focus  
 Устанавливает фокус на данный элемент управления.  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemclrbacka--catlpreviewctrlimplmclrback"></a><a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack  
 Цвет фона окна предварительного просмотра.  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemclrtexta--catlpreviewctrlimplmclrtext"></a><a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText  
 Цвет текста в окне предварительного просмотра.  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemplfa--catlpreviewctrlimplmplf"></a><a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf  
 Шрифт, используемый для отображения текста в окне предварительного просмотра.  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonpainta--catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>CAtlPreviewCtrlImpl::OnPaint  
 Обрабатывает сообщение WM_PAINT.  
  
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
  
##  <a name="a-nameredrawa--catlpreviewctrlimplredraw"></a><a name="redraw"></a>CAtlPreviewCtrlImpl::Redraw  
 Сообщает, этот элемент управления перерисовка.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesethosta--catlpreviewctrlimplsethost"></a><a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost  
 Устанавливает новый родительский объект для данного элемента управления.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна новый.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetpreviewvisualsa--catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals  
 Вызывается обработчиком расширенного просмотра при необходимые для установки отображения широкие возможности просмотра содержимого.  
  
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
 Цвет текста в окне предварительного просмотра.  
  
 `plf`  
 Шрифт, используемый для отображения текста в окне предварительного просмотра.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetrecta--catlpreviewctrlimplsetrect"></a><a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect  
 Задает ограничивающий прямоугольник для данного элемента управления.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>Параметры  
 `prc`  
 Указывает новый размер и положение элемента управления предварительной версии.  
  
 `bRedraw`  
 Указывает, следует ли перерисовке элемента управления.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Компоненты COM Desktop ATL](../../atl/atl-com-desktop-components.md)

