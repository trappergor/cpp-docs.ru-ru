---
title: Класс CMFCImageEditorPaletteBar
ms.date: 11/04/2016
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
ms.openlocfilehash: 6812f3f425186484ef892d7f5c626c0dfce0f863
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302990"
---
# <a name="cmfcimageeditorpalettebar-class"></a>Класс CMFCImageEditorPaletteBar

Предоставляет функциональные возможности панели палитры в диалоговое окно редактора изображений.

## <a name="syntax"></a>Синтаксис

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|Возвращает высоту кнопки панели инструментов. (Переопределяет [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Определяет, может ли отображать кнопки, которые имеют дополнительные границы панели инструментов. (Переопределяет [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|

### <a name="remarks"></a>Примечания

Этот класс не предназначен для использования непосредственно из программного кода.

Инфраструктура использует этот класс для отображения панели палитры в диалоговом окне редактора изображений. Дополнительные сведения о диалоговом окне редактора изображений, см. в разделе [класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afximageeditordialog.h

##  <a name="getrowheight"></a>  CMFCImageEditorPaletteBar::GetRowHeight

Возвращает высоту кнопки панели инструментов.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Высота каждой кнопки на панели инструментов.

##  <a name="isbuttonextrasizeavailable"></a>  CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable

Определяет, может ли отображать кнопки, которые имеют дополнительные границы панели инструментов.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение FALSE.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)
