---
title: "Класс CHtmlEditView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CHtmlEditView class
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d0194d48fe214d7c90b24ff8ce4ef10116cd536a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditview-class"></a>Класс CHtmlEditView
Предоставляет функции платформы редактирования WebBrowser в контексте архитектуры документов или представлений MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Создает объект `CHtmlEditView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|Создает новый объект окна.|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Возвращает **IHTMLDocument2** интерфейс для текущего документа.|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Получает имя документа по умолчанию для этого представления.|  
  
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
  
##  <a name="chtmleditview"></a>CHtmlEditView::CHtmlEditView  
 Создает объект `CHtmlEditView`.  
  
```  
CHtmlEditView();
```  
  
##  <a name="create"></a>CHtmlEditView::Create  
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
 Указывает строку символом null, что имена классов Windows. Имя класса может быть любое имя, зарегистрированное в [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальной функции или **RegisterClass** функции Windows. Если **NULL**, использует предопределенные по умолчанию [CFrameWnd](../../mfc/reference/cframewnd-class.md) атрибуты.  
  
 `lpszWindowName`  
 Указывает символ нулем строка, представляющая имя окна.  
  
 `dwStyle`  
 Задает атрибуты стилей окна. По умолчанию **WS_VISIBLE** и **WS_CHILD** заданы стили Windows.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определяя размер и положение окна. `rectDefault` Значение позволяет Windows указать размер и положение нового окна.  
  
 `pParentWnd`  
 Указатель на родительское окно элемента управления.  
  
 `nID`  
 Идентификатор представления. По умолчанию значение **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). **Значение NULL,** по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Этот метод также будет вызывать автономной WebBrowser **перехода** метод для загрузки документа по умолчанию (см. [CHtmlEditView::GetStartDocument](#getstartdocument)).  
  
##  <a name="getdhtmldocument"></a>CHtmlEditView::GetDHtmlDocument  
 Возвращает **IHTMLDocument2** интерфейс для текущего документа.  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppDocument`  
 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) интерфейса.  
  
##  <a name="getstartdocument"></a>CHtmlEditView::GetStartDocument  
 Получает имя документа по умолчанию для этого представления.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>См. также  
 [Образец HTMLEdit](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



