---
title: Класс CHtmlEditView | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10f474ce860bf5d9071a93f17654123f4777efa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367348"
---
# <a name="chtmleditview-class"></a>Класс CHtmlEditView
Предоставляет функции платформы редактирования WebBrowser в контексте архитектуры документов или представлений MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Создает объект `CHtmlEditView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|Создает новый объект окна.|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Возвращает **IHTMLDocument2** интерфейс для текущего документа.|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Возвращает имя документа по умолчанию для этого представления.|  
  
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
 `lpszClassName`  
 Указывает строку символом null, с именем класса Windows. Имя класса может быть любое имя, зарегистрированное в [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальной функции или **RegisterClass** функции Windows. Если **NULL**, использует предопределенные по умолчанию [CFrameWnd](../../mfc/reference/cframewnd-class.md) атрибуты.  
  
 `lpszWindowName`  
 Указатель на завершающуюся значением null строка, представляющая имя окна.  
  
 `dwStyle`  
 Задает атрибуты стилей окна. По умолчанию **WS_VISIBLE** и **WS_CHILD** заданы стили Windows.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определяя размер и положение окна. `rectDefault` Значение позволяет Windows указать размер и положение нового окна.  
  
 `pParentWnd`  
 Указатель на родительское окно элемента управления.  
  
 `nID`  
 Идентификатор представления. Значение по умолчанию, **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). **Значение NULL,** по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Этот метод также вызывает автономной WebBrowser **Navigate** метод, чтобы загрузить документ по умолчанию (в разделе [CHtmlEditView::GetStartDocument](#getstartdocument)).  
  
##  <a name="getdhtmldocument"></a>  CHtmlEditView::GetDHtmlDocument  
 Возвращает **IHTMLDocument2** интерфейс для текущего документа.  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppDocument`  
 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) интерфейса.  
  
##  <a name="getstartdocument"></a>  CHtmlEditView::GetStartDocument  
 Возвращает имя документа по умолчанию для этого представления.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>См. также  
 [Образец HTMLEdit](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


