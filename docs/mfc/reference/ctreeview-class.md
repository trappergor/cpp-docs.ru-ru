---
title: "Класс CTreeView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- directory lists
- tree view controls
- file lists [C++]
- CTreeView class, common controls
- CTreeView class
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: 22
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
ms.openlocfilehash: c317d91a07b5cb45b58ec4c4af2e9ee0f3b24e28
ms.lasthandoff: 02/24/2017

---
# <a name="ctreeview-class"></a>CTreeView-класс
Упрощает использование элемента управления иерархического и [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), класс, инкапсулирующий функциональные возможности управления дерева, архитектуру представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTreeView::CTreeView](#ctreeview)|Создает объект `CTreeView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](#gettreectrl)|Возвращает дерево, связанный с представлением.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об этой архитектуре см [CView](../../mfc/reference/cview-class.md) класс и перекрестные ссылки, Цитируемые существует.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcview.h  
  
##  <a name="ctreeview"></a>CTreeView::CTreeView  
 Создает объект `CTreeView`.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>CTreeView::GetTreeCtrl  
 Возвращает ссылку на дерево управления, связанный с представлением.  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>См. также  
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl-класс](../../mfc/reference/ctreectrl-class.md)

