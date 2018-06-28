---
title: CListView-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9087642a529911c0c0a885c4613a3dbf2e92311f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037626"
---
# <a name="clistview-class"></a>CListView-класс
Упрощает использование элемента управления "список" и [CListCtrl](../../mfc/reference/clistctrl-class.md), класс, который инкапсулирует функциональность элемента управления списка в архитектуру представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|Создает объект `CListView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|Возвращает список элементов управления, связанный с представлением.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|Удаляет указанный образ список из списка.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об этой архитектуре см [CView](../../mfc/reference/cview-class.md) класс и перекрестные ссылки, указан.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcview.h  
  
##  <a name="clistview"></a>  CListView::CListView  
 Создает объект `CListView`.  
  
```  
CListView();
```  
  
##  <a name="getlistctrl"></a>  CListView::GetListCtrl  
 Вызовите эту функцию-член для получения ссылки на элемент управления списка, связанный с представлением.  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент управления списка, связанный с представлением.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="removeimagelist"></a>  CListView::RemoveImageList  
 Удаляет указанный образ список из списка.  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>Параметры  
 *nImageList*  
 Отсчитываемый от нуля индекс образа для удаления.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC ROWLIST](../../visual-cpp-samples.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)
