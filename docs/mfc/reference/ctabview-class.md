---
title: "Класс CTabView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
dev_langs:
- C++
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adbb5d92387634356f1185cee73d5969944ac27a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctabview-class"></a>Класс CTabView
`CTabView` Класс упрощает использование класса элемента управления tab ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) в приложениях, использующих архитектуру документ/представление MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|Добавляет новое представление вкладок элемента управления.|  
|[CTabView::FindTab](#findtab)|Возвращает индекс указанного представления в набор вкладок.|  
|[CTabView::GetActiveView](#getactiveview)|Возвращает указатель на текущего активного представления|  
|[CTabView::GetTabControl](#gettabcontrol)|Возвращает ссылку на набор вкладок, связанный с представлением.|  
|[CTabView::RemoveView](#removeview)|Удаляет представление из вкладок элемента управления.|  
|[CTabView::SetActiveView](#setactiveview)|Делает активным представления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|Вызывается платформой при создании представления вкладки для определения, имеет ли представление вкладка общих горизонтальной полосы прокрутки.|  
|[CTabView::OnActivateView](#onactivateview)|Вызывается платформой при представлении вкладка становится активным или неактивным.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс позволяет легко перевести представление со вкладками в приложении документов и представлений. `CTabView`— `CView`-производного класса, который содержит встроенный `CMFCTabCtrl` объекта. `CTabView`обрабатывает все сообщения, необходимые для поддержки `CMFCTabCtrl` объекта. Просто создайте класс, наследующий `CTabView` и подключить его в приложение, а затем добавьте `CView`-производные классы с помощью `AddView` метод. Управления "Вкладка" отображается эти представления в виде вкладок.  
  
 Например, может потребоваться документа, могут быть представлены различными способами: как электронную таблицу, диаграмму, редактируемую форму и т. д. Можно создавать отдельные представления, графические данные, при необходимости, вставьте их в вашей `CTabView`-производного объекта и настроить их с вкладками без дополнительного кодирования.  
  
 [Образец TabbedView: Приложения для представления с вкладками MFC](../../visual-cpp-samples.md) иллюстрирует использование `CTabView`.  
  
## <a name="example"></a>Пример  
 В следующем примере показан способ `CTabView` используется в образце TabbedView.  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTabView.h  
  
##  <a name="addview"></a>CTabView::AddView  
 Добавляет представление вкладок элемента управления.  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pViewClass`  
 Указатель на класс среды выполнения inserted представления.  
  
 [in] `strViewLabel`  
 Указывает текст вкладки.  
  
 [in] `iIndex`  
 Задает отсчитываемый от нуля позиция, с которой нужно вставить представление. Если позиция равна -1 в конце вставляется новая вкладка.  
  
 [in] `pContext`  
 Указатель на `CCreateContext` представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс представления, если метод завершается успешно. В противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для добавления представления к вкладок, внедренных в кадре.  
  
##  <a name="findtab"></a>CTabView::FindTab  
 Возвращает индекс указанного представления в набор вкладок.  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hWndView`  
 Дескриптор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс представления, если он найден; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения индекс представления с указанным дескриптором.  
  
##  <a name="getactiveview"></a>CTabView::GetActiveView  
 Возвращает указатель в настоящее время активное представление.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель на активное представление или `NULL` Если нет активных представления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettabcontrol"></a>CTabView::GetTabControl  
 Возвращает ссылку на набор вкладок, связанный с представлением.  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на набор вкладок, связанный с представлением.  
  
##  <a name="isscrollbar"></a>CTabView::IsScrollBar  
 Вызывается платформой при создании представления вкладки для определения, имеет ли представление вкладка общих горизонтальной полосы прокрутки.  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладка представления должны создаваться вместе с полоса прокрутки общего. В противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при `CTabView` создан объект.  
  
 Переопределить `IsScrollBar` метод в `CTabView`-производного класса и возврата `TRUE` Если нужно создать представление, имеющее общего горизонтальной полосы прокрутки.  
  
##  <a name="onactivateview"></a>CTabView::OnActivateView  
 Вызывается платформой при представлении вкладка становится активным или неактивным.  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `view`  
 Указатель на представление.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в `CTabView`-производный класс для обработки этого уведомления.  
  
##  <a name="removeview"></a>CTabView::RemoveView  
 Удаляет представление из вкладок элемента управления.  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTabNum`  
 Индекс удаляемого представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс удален представления, если метод завершается успешно. В противном случае значение -1.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setactiveview"></a>CTabView::SetActiveView  
 Делает активным представления.  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTabNum`  
 Отсчитываемый от нуля индекс представления вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанное представление сделан активным, `FALSE` Если недопустимый индекс представления.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [Класс CView](../../mfc/reference/cview-class.md)
