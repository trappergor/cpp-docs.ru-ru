---
title: Класс CTreeView | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a760e567718ad7a485ebe469903c7cbd566daccc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375402"
---
# <a name="ctreeview-class"></a>Класс CTreeView

Упрощает использование элемента управления дерева и [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), который инкапсулирует его функциональность, в архитектуру представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTreeView::CTreeView](#ctreeview)|Создает объект `CTreeView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
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
