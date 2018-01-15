---
title: "CTreeView-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs: C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7530569d5e5313ebfcbdaf92ebd245962b9e443c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctreeview-class"></a>CTreeView-класс
Упрощает использование элемента управления дерева и [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), класс, который инкапсулирует функциональность элемента управления дерева в архитектуру представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTreeView::CTreeView](#ctreeview)|Создает объект `CTreeView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](#gettreectrl)|Возвращает дерево элемента управления, связанного с представлением.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об этой архитектуре см [CView](../../mfc/reference/cview-class.md) класс и перекрестные ссылки, указан.  
  
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
 Возвращает ссылку на дерево, связанный с представлением.  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>См. также  
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Класс CTreeCtrl](../../mfc/reference/ctreectrl-class.md)
