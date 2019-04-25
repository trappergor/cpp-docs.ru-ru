---
title: Класс CTreeView
ms.date: 11/04/2016
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
ms.openlocfilehash: fec8379a3944d981672754274f50dd4e60f71b61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323600"
---
# <a name="ctreeview-class"></a>Класс CTreeView

Упрощает использование элемента управления дерева и [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), который инкапсулирует его функциональность, в архитектуру представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CTreeView::CTreeView](#ctreeview)|Создает объект `CTreeView`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CTreeView::GetTreeCtrl](#gettreectrl)|Возвращает дерево, связанный с представлением.|

## <a name="remarks"></a>Примечания

Дополнительные сведения об этой архитектуре см. в обзоре, для [CView](../../mfc/reference/cview-class.md) класс и перекрестные ссылки, указанных там.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>Требования

**Заголовок:** afxcview.h

##  <a name="ctreeview"></a>  CTreeView::CTreeView

Создает объект `CTreeView`.

```
CTreeView();
```

##  <a name="gettreectrl"></a>  CTreeView::GetTreeCtrl

Возвращает ссылку на дерево управления, связанный с представлением.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>См. также

[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Класс CTreeCtrl](../../mfc/reference/ctreectrl-class.md)
