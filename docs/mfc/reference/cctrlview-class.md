---
title: "Класс CCtrlView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- controls [MFC], common
- CCtrlView class
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
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
ms.openlocfilehash: 569044de59dc3ccd73157abc86855beef57cb558
ms.lasthandoff: 02/24/2017

---
# <a name="cctrlview-class"></a>Класс CCtrlView
Адаптирует архитектуру "документ-представление" для распространенных элементов управления, поддерживаемых Windows 98 и Windows NT (версии 3.51 и более поздние).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|Создает объект `CCtrlView`.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|Вызывается платформой для рисования с помощью заданного контекста устройств.|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|Вызывается до создания окна Windows, присоединенного к данному объекту класса `CCtrlView`.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Содержит стиль по умолчанию для класса представления.|  
|[CCtrlView::m_strClass](#m_strclass)|Содержит имя класса Windows для класса представления.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CCtrlView` и его производные [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), и [CRichEditView](../../mfc/reference/cricheditview-class.md), адаптировать архитектуру представления документов для новых общих элементов управления, поддерживаемых Windows 95/98 и Windows NT версии 3.51 и более поздней версии. Дополнительные сведения о архитектуру представления документов см. [архитектуры документ/представление](../../mfc/document-view-architecture.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cctrlview"></a>CCtrlView::CCtrlView  
 Создает объект `CCtrlView`.  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClass`  
 Имя класса Windows для класса представления.  
  
 `dwStyle`  
 Стиль класса представления.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает конструктор при создании нового окна области или разбить окно. Переопределение [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) для инициализации представления после присоединения документа. Вызов [CWnd::Create](../../mfc/reference/cwnd-class.md#create) или [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) для создания объекта Windows.  
  
##  <a name="m_strclass"></a>CCtrlView::m_strClass  
 Содержит имя класса Windows для класса представления.  
  
```  
CString m_strClass;  
```  
  
##  <a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle  
 Содержит стиль по умолчанию для класса представления.  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот стиль применяется при создании окна.  
  
##  <a name="ondraw"></a>CCtrlView::OnDraw  
 Вызывается платформой для отрисовки содержимого `CCtrlView` объекта с помощью заданного контекста устройств.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, в котором происходит рисование.  
  
### <a name="remarks"></a>Примечания  
 `OnDraw`для просмотра на экране, передавая экрана контекста устройства, заданные обычно вызывается `pDC`.  
  
##  <a name="precreatewindow"></a>CCtrlView::PreCreateWindow  
 Вызывается до создания окна Windows, присоединенного к данному объекту класса `CWnd`.  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Параметры  
 *CS*  
 Объект [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если следует продолжить создание окна; 0 в случае сбоя создания.  
  
### <a name="remarks"></a>Примечания  
 Невозможно напрямую вызвать эту функцию.  
  
 Реализация по умолчанию эта функция проверяет наличие **NULL** имя класса окна и подставляет соответствующее значение по умолчанию. Переопределение для изменения эта функция-член `CREATESTRUCT` структуры перед созданием окна.  
  
 Каждый класс, производный от `CCtrlView` добавляет собственные функциональные возможности его переопределение `PreCreateWindow`. Особенностью этих производных `PreCreateWindow` не документированы. Чтобы определить, подходящие для каждого класса и взаимозависимости между стилями стили, можно проверить исходный код MFC для базового класса приложения. Если выбрать переопределение `PreCreateWindow`, можно определить, обеспечивают ли стили, используемые в базовом классе приложения необходимые функции с помощью сведений из исходного кода MFC.  
  
 Дополнительные сведения об изменении стилей окна в разделе [изменение стилей окна созданного MFC](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CTreeView-класс](../../mfc/reference/ctreeview-class.md)   
 [CListView-класс](../../mfc/reference/clistview-class.md)   
 [CRichEditView-класс](../../mfc/reference/cricheditview-class.md)

