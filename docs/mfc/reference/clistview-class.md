---
title: "CListView-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- CListView class
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
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
ms.openlocfilehash: ebf6c93aa6d88d1942af4ecb9e3373fa57d84b65
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="clistview-class"></a>CListView-класс
Упрощает использование элемента управления списком и [CListCtrl](../../mfc/reference/clistctrl-class.md), класс, инкапсулирующий функциональные возможности управления списком, архитектуру представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|Создает объект `CListView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|Возвращает список элементов управления, связанный с представлением.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|Удаляет список указанное изображение в представлении списка.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об этой архитектуре см [CView](../../mfc/reference/cview-class.md) класс и перекрестные ссылки, Цитируемые существует.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcview.h  
  
##  <a name="clistview"></a>CListView::CListView  
 Создает объект `CListView`.  
  
```  
CListView();
```  
  
##  <a name="getlistctrl"></a>CListView::GetListCtrl  
 Вызовите эту функцию-член для получения ссылки на элемент управления списка, связанный с представлением.  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент управления списка, связанный с представлением.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCListView&#7;](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="removeimagelist"></a>CListView::RemoveImageList  
 Удаляет список указанное изображение в представлении списка.  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `nImageList`  
 Отсчитываемый от нуля индекс образа для удаления.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC ROWLIST](../../visual-cpp-samples.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)

