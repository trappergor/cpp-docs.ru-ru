---
title: "Класс CMFCPreviewCtrlImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPreviewCtrlImpl
- afxwin/CMFCPreviewCtrlImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCPreviewCtrlImpl class
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
caps.latest.revision: 28
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b3ccd0d6e03f652798b45ac35d36f8bc2f63e048
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpreviewctrlimpl-class"></a>Класс CMFCPreviewCtrlImpl
Этот класс реализует окно, которое помещается в окне узла, заданного оболочкой для расширенного просмотра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|Разрушается объект элемента управления для предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Создает объект управления предварительной версии.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|Перегружен. Вызывается из обработчика просмотра широкие возможности для создания окна Windows.|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Вызывается обработчиком расширенного просмотра, когда необходимо уничтожить этот элемент управления.|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|Устанавливает фокус на данный элемент управления.|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Возвращает документ, подключенных к этому элементу управления предварительной версии.|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Сообщает, этот элемент управления перерисовка.|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Вызывается из обработчика просмотра для создания отношений между реализацией документов и управления для предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Устанавливает новый родительский объект для данного элемента управления.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Вызывается обработчиком расширенного просмотра при необходимые для установки отображения широкие возможности просмотра содержимого.|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Задает ограничивающий прямоугольник для данного элемента управления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается платформой для подготовки к просмотру в предварительной версии.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Цвет фона окна предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Цвет текста окно предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Указатель на документ, содержимое которого отображается в элементе управления.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="a-namecmfcpreviewctrlimpla-cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a>CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
Создает объект управления предварительной версии.

### <a name="syntax"></a>Синтаксис
CMFCPreviewCtrlImpl();  

## <a name="a-namecreatea-cmfcpreviewctrlimplcreate"></a><a name="create"></a>CMFCPreviewCtrlImpl::Create
Перегружен. Вызывается из обработчика просмотра широкие возможности для создания окна Windows.  
  
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
 `hWndParent`  
 Дескриптор главного окна, предоставленного оболочкой для расширенного просмотра.  
  
 `prc`  
 Задает начальный размер и положение окна.  
  
 `pContext`  
 Указатель на контекст создания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`При успешном завершении создания. в противном случае `FALSE`.  
  
## <a name="a-namedestroya-cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a>CMFCPreviewCtrlImpl::Destroy
Вызывается обработчиком расширенного просмотра, когда необходимо уничтожить этот элемент управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void Destroy();  
```  
  
## <a name="a-namedopainta-cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a>CMFCPreviewCtrlImpl::DoPaint  
Вызывается платформой для подготовки к просмотру в предварительной версии.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства для рисования.  


## <a name="a-namefocusa-cmfcpreviewctrlimplfocus"></a><a name="focus"></a>CMFCPreviewCtrlImpl::Focus  
Устанавливает фокус на данный элемент управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void Focus();  
```  
## <a name="a-namegetdocumenta-cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a>CMFCPreviewCtrlImpl::GetDocument
Возвращает документ, подключенных к этому элементу управления предварительной версии.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, содержимое которого представлен в элементе управления.

## <a name="a-namemclrbackcolora-cmfcpreviewctrlimplmclrbackcolor"></a><a name="m_clrbackcolor"></a>CMFCPreviewCtrlImpl::m_clrBackColor  
Цвет фона окна предварительного просмотра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="a-namemclrtextcolora-cmfcpreviewctrlimplmclrtextcolor"></a><a name="m_clrtextcolor"></a>CMFCPreviewCtrlImpl::m_clrTextColor
Цвет текста в окне предварительного просмотра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="a-namemfonta-cmfcpreviewctrlimplmfont--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a>CMFCPreviewCtrlImpl::m_font шрифт, используемый для отображения текста в окне предварительного просмотра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
CFont m_font;  
```  
## <a name="a-namempdocumenta-cmfcpreviewctrlimplmpdocument"></a><a name="m_pdocument"></a>CMFCPreviewCtrlImpl::m_pDocument  
Указатель на документ, содержимое которого отображается в элементе управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="a-nameredrawa-cmfcpreviewctrlimplredraw"></a><a name="redraw"></a>CMFCPreviewCtrlImpl::Redraw  
Сообщает, этот элемент управления перерисовка.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void Redraw();  
```  
## <a name="a-namesetdocumenta-cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a>CMFCPreviewCtrlImpl::SetDocument 
Вызывается из обработчика просмотра для создания отношений между реализацией документов и управления для предварительного просмотра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDocument`  
 Указатель на реализацию документа.  

## <a name="a-namesethosta-cmfcpreviewctrlimplsethost"></a><a name="sethost"></a>CMFCPreviewCtrlImpl::SetHost  
Устанавливает новый родительский объект для данного элемента управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна новый.  

## <a name="a-namesetpreviewvisualsa-cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CMFCPreviewCtrlImpl::SetPreviewVisuals  
Вызывается обработчиком расширенного просмотра при необходимые для установки отображения широкие возможности просмотра содержимого.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `clrBack`  
 Цвет фона окна предварительного просмотра.  
  
 `clrText`  
 Цвет текста окно предварительного просмотра.  
  
 `plf`  
 Шрифт, используемый для отображения текста в окне предварительного просмотра. 

##  <a name="a-namesetrecta-cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a>CMFCPreviewCtrlImpl::SetRect  
Задает ограничивающий прямоугольник для данного элемента управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `prc`  
 Указывает новый размер и положение элемента управления предварительной версии.  
  
 `bRedraw`  
 Указывает, следует ли перерисовке элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Обычно ограничивающий прямоугольник имеет значение при изменении размеров элемента управления ведущего приложения.  

## <a name="a-namedtora-cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a>CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
Разрушается объект элемента управления для предварительного просмотра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  

