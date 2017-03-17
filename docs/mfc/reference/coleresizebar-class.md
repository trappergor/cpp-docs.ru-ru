---
title: "Класс COleResizeBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- OLE items, resizing
- in-place items
- in-place items, resizing
- resizing in-place OLE items
- control bars, resizing
- COleResizeBar class
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
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
ms.openlocfilehash: 99ba53c771d018b8c69c5951703b9d6f7b4afe9b
ms.lasthandoff: 02/24/2017

---
# <a name="coleresizebar-class"></a>Класс COleResizeBar
Тип панели элементов управления, который поддерживает изменение размера элементов OLE "на месте".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|Создает объект `COleResizeBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|Создает и инициализирует дочернего окна Windows и связывает его `COleResizeBar` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleResizeBar`объекты отображаются как [CRectTracker](../../mfc/reference/crecttracker-class.md) со штриховой границей и внешней маркеры изменения размера.  
  
 `COleResizeBar`объекты обычно embedded входят фреймового окна объектов, производных от [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) класса.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coleresizebar"></a>COleResizeBar::COleResizeBar  
 Создает объект `COleResizeBar`.  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов **создать** для создания объекта панель изменения размера.  
  
##  <a name="create"></a>COleResizeBar::Create  
 Создает дочернего окна и связывает его с `COleResizeBar` объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно изменения размера строки.  
  
 `dwStyle`  
 Указывает [стиль окна](../../mfc/reference/window-styles.md) атрибуты.  
  
 `nID`  
 Идентификатор дочернего полосу изменения размера окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если был создан полосу изменения размера; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

