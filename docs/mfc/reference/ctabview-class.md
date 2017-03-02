---
title: "Класс CTabView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabView
dev_langs:
- C++
helpviewer_keywords:
- CTabView class
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
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
ms.openlocfilehash: 20f5745c3784e771d6ec95f7d4dc363142c687f8
ms.lasthandoff: 02/24/2017

---
# <a name="ctabview-class"></a>Класс CTabView
`CTabView` Класс упрощает использование класса элемента управления вкладки ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) в приложениях, использующих архитектуру документ/представление MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|Добавляет новое представление вкладок элемента управления.|  
|[CTabView::FindTab](#findtab)|Возвращает индекс указанного представления в элементе управления вкладками.|  
|[CTabView::GetActiveView](#getactiveview)|Возвращает указатель активного представления|  
|[CTabView::GetTabControl](#gettabcontrol)|Возвращает ссылку на вкладок, связанный с представлением.|  
|[CTabView::RemoveView](#removeview)|Удаляет представление из вкладок элемента управления.|  
|[CTabView::SetActiveView](#setactiveview)|Активизация представления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|Вызывается инфраструктурой при создании представление вкладки, чтобы определить, имеет ли представление вкладки общей горизонтальной полосы прокрутки.|  
|[CTabView::OnActivateView](#onactivateview)|Вызывается платформой, когда представление вкладки становится активным или неактивным.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс позволяет легко поместить представление со вкладками в приложении документов и представлений. `CTabView`— `CView`-производного класса, который содержит встроенный `CMFCTabCtrl` объекта. `CTabView`обрабатывает все сообщения, необходимые для поддержки `CMFCTabCtrl` объекта. Просто наследуйте класс от `CTabView` и подключить его в приложение, а затем добавьте `CView`-производных классов с помощью `AddView` метод. Вкладок элемента управления отображается эти представления в виде вкладок.  
  
 Например, может потребоваться документа, могут быть представлены различными способами: как электронную таблицу, диаграмму, редактируемую форму и т. д. Можно создавать отдельные представления графические данные, при необходимости, вставить их в своей `CTabView`-производного объекта и их с вкладками без дополнительного кодирования.  
  
 [Образец TabbedView: Приложение для представления с вкладками MFC](../../visual-cpp-samples.md) иллюстрирует использование `CTabView`.  
  
## <a name="example"></a>Пример  
 В следующем примере показан способ `CTabView` в образце TabbedView используется.  
  
 [!code-cpp[NVC_MFC_TabbedView&#1;](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTabView.h  
  
##  <a name="a-nameaddviewa--ctabviewaddview"></a><a name="addview"></a>CTabView::AddView  
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
 Указатель на класс среды выполнения вставленного представления.  
  
 [in] `strViewLabel`  
 Указывает текст вкладки.  
  
 [in] `iIndex`  
 Задает отсчитываемый от нуля позиция для вставки представления. Если позиция равна -1 в конце вставляется новая вкладка.  
  
 [in] `pContext`  
 Указатель на `CCreateContext` представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс представления, если этот метод завершается успешно. В противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для добавления представления вкладок, внедренный в кадре.  
  
##  <a name="a-namefindtaba--ctabviewfindtab"></a><a name="findtab"></a>CTabView::FindTab  
 Возвращает индекс указанного представления в элементе управления вкладками.  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hWndView`  
 Дескриптор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс представления, если он найден; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения индекса представления с указанным дескриптором.  
  
##  <a name="a-namegetactiveviewa--ctabviewgetactiveview"></a><a name="getactiveview"></a>CTabView::GetActiveView  
 Возвращает указатель активного представления.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель на активное представление или `NULL` Если нет активного представления.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabcontrola--ctabviewgettabcontrol"></a><a name="gettabcontrol"></a>CTabView::GetTabControl  
 Возвращает ссылку на вкладок, связанный с представлением.  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на вкладок, связанный с представлением.  
  
##  <a name="a-nameisscrollbara--ctabviewisscrollbar"></a><a name="isscrollbar"></a>CTabView::IsScrollBar  
 Вызывается инфраструктурой при создании представление вкладки, чтобы определить, имеет ли представление вкладки общей горизонтальной полосы прокрутки.  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если представление вкладки должны создаваться вместе с общего прокрутки. В противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при `CTabView` создается объект.  
  
 Переопределение `IsScrollBar` метод в `CTabView`-производного класса и возврата `TRUE` Если вы хотите создать представление, имеющее общей горизонтальной полосы прокрутки.  
  
##  <a name="a-nameonactivateviewa--ctabviewonactivateview"></a><a name="onactivateview"></a>CTabView::OnActivateView  
 Вызывается платформой, когда представление вкладки становится активным или неактивным.  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `view`  
 Указатель на представление.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в `CTabView`-производный класс для обработки этого уведомления.  
  
##  <a name="a-nameremoveviewa--ctabviewremoveview"></a><a name="removeview"></a>CTabView::RemoveView  
 Удаляет представление из вкладок элемента управления.  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTabNum`  
 Индекс удаляемого представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс удален представления, если этот метод завершается успешно. В противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetactiveviewa--ctabviewsetactiveview"></a><a name="setactiveview"></a>CTabView::SetActiveView  
 Активизация представления.  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTabNum`  
 Отсчитываемый от нуля индекс представление вкладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанное представление был активизирован, `FALSE` Если индекс представления является недопустимым.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)

