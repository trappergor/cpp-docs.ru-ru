---
title: Класс CMFCPreviewCtrlImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a94ad813ff72eaed2642e9c78a098b999bf128fa
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040081"
---
# <a name="cmfcpreviewctrlimpl-class"></a>Класс CMFCPreviewCtrlImpl
Этот класс реализует окно, которое помещается в окне узла, заданного оболочкой для расширенного просмотра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|Разрушается объект предварительного просмотра элемента управления.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Создает объект предварительного просмотра элемента управления.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|Перегружен. Вызывается обработчиком расширенного просмотра для создания окна Windows.|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Вызывается обработчиком расширенного просмотра, когда необходимо удалить этот элемент управления.|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|Устанавливает фокус на данный элемент управления "поле ввода".|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Возвращает документ, подключенных к данному элементу управления предварительной версии.|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Сообщает, этот элемент управления для повторной отрисовки.|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Вызывается методом обработчика предварительного просмотра, чтобы создать связь между реализацией документа и предварительного просмотра элемента управления.|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Задает новый родительский объект для этого элемента управления.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Вызывается обработчиком расширенного просмотра при необходимости задайте визуальных элементов широкие возможности просмотра содержимого.|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Задает ограничивающий прямоугольник для этого элемента управления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается платформой для отрисовки на предварительную версию.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Цвет фона окна предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Цвет текста окна предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Указатель на документ, содержимое которой просматривается в элементе управления.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
Создает объект предварительного просмотра элемента управления.

### <a name="syntax"></a>Синтаксис
CMFCPreviewCtrlImpl();  

## <a name="create"></a> CMFCPreviewCtrlImpl::Create
Перегружен. Вызывается обработчиком расширенного просмотра для создания окна Windows.  
  
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
 *hWndParent*  
 Дескриптор главного окна, предоставленный оболочкой для расширенного просмотра.  
  
 *КНР*  
 Задает начальный размер и положение окна.  
  
 *pContext*  
 Указатель на контекст создания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если создание прошло успешно; в противном случае `FALSE`.  
  
## <a name="destroy"></a> CMFCPreviewCtrlImpl::Destroy
Вызывается обработчиком расширенного просмотра, когда необходимо удалить этот элемент управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void Destroy();  
```  
  
## <a name="dopaint"></a> CMFCPreviewCtrlImpl::DoPaint  
Вызывается платформой для отрисовки на предварительную версию.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *контроллер домена*  
 Указатель на контекст устройства для рисования.  


## <a name="focus"></a> CMFCPreviewCtrlImpl::Focus  
Устанавливает фокус на данный элемент управления "поле ввода".  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void Focus();  
```  
## <a name="getdocument"></a> CMFCPreviewCtrlImpl::GetDocument
Возвращает документ, подключенных к данному элементу управления предварительной версии.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, содержимое которой просматривается в элементе управления.

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
Указатель на документ, содержимое которой просматривается в элементе управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="redraw"></a> CMFCPreviewCtrlImpl::Redraw  
Сообщает, этот элемент управления для повторной отрисовки.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void Redraw();  
```  
## <a name="setdocument"></a> CMFCPreviewCtrlImpl::SetDocument 
Вызывается методом обработчика предварительного просмотра, чтобы создать связь между реализацией документа и предварительного просмотра элемента управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *pDocument*  
 Указатель для реализации документа.  

## <a name="sethost"></a> CMFCPreviewCtrlImpl::SetHost  
Задает новый родительский объект для этого элемента управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *hWndParent*  
 Дескриптор родительского окна новый.  

## <a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals  
Вызывается обработчиком расширенного просмотра при необходимости задайте визуальных элементов широкие возможности просмотра содержимого.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *clrBack*  
 Цвет фона окна предварительного просмотра.  
  
 *clrText*  
 Цвет текста окна предварительного просмотра.  
  
 *plf*  
 Шрифт, используемый для отображения текста в окне предварительного просмотра. 

##  <a name="setrect"></a> CMFCPreviewCtrlImpl::SetRect  
Задает ограничивающий прямоугольник для этого элемента управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *КНР*  
 Указывает новый размер и положение элемента управления для предварительного просмотра.  
  
 *bRedraw*  
 Указывает, следует ли перерисовке элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Обычно при изменении размера элемента управления ведущего приложения, имеет значение нового ограничивающего прямоугольника.  

## <a name="dtor"></a> CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
Разрушается объект предварительного просмотра элемента управления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  
