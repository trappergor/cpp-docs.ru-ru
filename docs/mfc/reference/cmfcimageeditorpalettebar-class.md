---
title: CMFCImageEditorEditorОпалПалпатистБар Класс
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
ms.openlocfilehash: 33d4bc0c72718d028031ac11bc67da6aec5e4907
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374424"
---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorEditorОпалПалпатистБар Класс

Обеспечивает функциональность панели палитры в диалоговом окне редактора изображений.

## <a name="syntax"></a>Синтаксис

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCImageEditorИсточникПалтбар::GetRowHeight](#getrowheight)|Возвращает высоту кнопок панели инструментов. (Переопределяет [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCImageEditorEditorPalettePaletteBar::IsbuttonExtraSizeAvailable](#isbuttonextrasizeavailable)|Определяет, может ли панель инструментов отображать кнопки, которые имеют расширенные границы. (Переопределяет [CMFCToolBar::IsbuttonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|

### <a name="remarks"></a>Remarks

Данный класс не предназначен для непосредственного использования в коде.

Платформа использует этот класс для отображения панели палитры в диалоговом окне редактора изображений. Для получения дополнительной информации о диалоговом окне редактора изображений [см.](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCImageEditorEditorПалт-бар](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afximageeditordialog.h

## <a name="cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a>CMFCImageEditorИсточникПалтбар::GetRowHeight

Возвращает высоту кнопок панели инструментов.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Высота каждой кнопки на панели инструментов.

## <a name="cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFCImageEditorEditorPalettePaletteBar::IsbuttonExtraSizeAvailable

Определяет, может ли панель инструментов отображать кнопки, которые имеют расширенные границы.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает FALSE.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorEditorДиоредакторКласс](../../mfc/reference/cmfcimageeditordialog-class.md)
