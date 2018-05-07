---
title: Класс CCtrlView | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3503f59096d3879f986b2a8c99bdb9823ef4e24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cctrlview-class"></a>Класс CCtrlView
Адаптирует архитектуру "документ-представление" для распространенных элементов управления, поддерживаемых Windows 98 и Windows NT (версии 3.51 и более поздние).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|Создает объект `CCtrlView`.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|Вызывается платформой для отрисовки, с помощью заданного контекста устройств.|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|Вызывается до создания окна Windows, присоединенного к данному объекту класса `CCtrlView`.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Содержит стиль по умолчанию для класса представления.|  
|[CCtrlView::m_strClass](#m_strclass)|Содержит имя класса Windows для класса представления.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CCtrlView` и его производные [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), и [CRichEditView](../../mfc/reference/cricheditview-class.md), адаптировать архитектуру представления документов для новых общих элементов управления поддерживаются Windows 95/98 и Windows NT 3.51 и более поздних версиях. Дополнительные сведения о архитектуру представления документов см. в разделе [архитектуры Document/View](../../mfc/document-view-architecture.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cctrlview"></a>  CCtrlView::CCtrlView  
 Создает объект `CCtrlView`.  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClass`  
 Имя класса Windows класса представления.  
  
 `dwStyle`  
 Стиль класса представления.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает конструктор, когда создается новый объект окна или разделить окна. Переопределить [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) для инициализации представления после присоединения документа. Вызовите [CWnd::Create](../../mfc/reference/cwnd-class.md#create) или [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) для создания объекта Windows.  
  
##  <a name="m_strclass"></a>  CCtrlView::m_strClass  
 Содержит имя класса Windows для класса представления.  
  
```  
CString m_strClass;  
```  
  
##  <a name="m_dwdefaultstyle"></a>  CCtrlView::m_dwDefaultStyle  
 Содержит стиль по умолчанию для класса представления.  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот стиль применяется при создании окна.  
  
##  <a name="ondraw"></a>  CCtrlView::OnDraw  
 Вызывается платформой для отрисовки содержимого `CCtrlView` объекта с помощью заданного контекста устройств.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, в котором происходит рисование.  
  
### <a name="remarks"></a>Примечания  
 `OnDraw` обычно вызывается для отображения на экране, передавая экрана контекста устройства, заданные `pDC`.  
  
##  <a name="precreatewindow"></a>  CCtrlView::PreCreateWindow  
 Вызывается до создания окна Windows, присоединенного к данному объекту класса `CWnd`.  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Параметры  
 *cs*  
 Объект [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если следует продолжить создание окна; 0 для указания сбой при создании.  
  
### <a name="remarks"></a>Примечания  
 Невозможно напрямую вызвать эту функцию.  
  
 Реализация по умолчанию эта функция проверяет наличие **NULL** имя класса окна и замещает соответствующее значение по умолчанию. Переопределить эту функцию-член для изменения `CREATESTRUCT` структуру перед созданием окна.  
  
 Каждый класс, производный от `CCtrlView` добавляет свои собственные функции для его переопределения `PreCreateWindow`. Макеты этих наследниками `PreCreateWindow` не документированы. Чтобы определить подходящие для каждого класса и взаимозависимости между стили стили, можно проверить исходный код MFC для базового класса приложения. Если выбрать переопределение `PreCreateWindow`, чтобы выяснить, обеспечивают ли стили, используемые в базовом классе приложения необходимые функции с помощью сведений из исходного кода MFC.  
  
 Дополнительные сведения об изменении стилей окна см. в разделе [изменение стилей окна, созданные с MFC](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CTreeView-класс](../../mfc/reference/ctreeview-class.md)   
 [CListView-класс](../../mfc/reference/clistview-class.md)   
 [Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
