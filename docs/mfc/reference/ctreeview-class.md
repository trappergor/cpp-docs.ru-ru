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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883997"
---
# <a name="ctreeview-class"></a>Класс CTreeView

Упрощает использование элемента управления "дерево" и [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), класса, который инкапсулирует функции управления деревом, с архитектурой "документ-представление" MFC.

## <a name="syntax"></a>Синтаксис

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CTreeView:: CTreeView](#ctreeview)|Формирует объект `CTreeView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CTreeView:: GetTreeCtrl](#gettreectrl)|Возвращает элемент управления "дерево", связанный с представлением.|

## <a name="remarks"></a>Remarks

Дополнительные сведения об этой архитектуре см. в обзоре класса [CView](../../mfc/reference/cview-class.md) и перекрестных ссылок, указанных здесь.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[кктрлвиев](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>Требования

**Заголовок:** афксквиев. h

##  <a name="ctreeview"></a>CTreeView:: CTreeView

Формирует объект `CTreeView`.

```
CTreeView();
```

##  <a name="gettreectrl"></a>CTreeView:: GetTreeCtrl

Возвращает ссылку на элемент управления "дерево", связанный с представлением.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>См. также раздел

[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Класс CTreeCtrl](../../mfc/reference/ctreectrl-class.md)
