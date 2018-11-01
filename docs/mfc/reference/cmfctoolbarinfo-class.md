---
title: Класс CMFCToolBarInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
ms.openlocfilehash: e1e460fe3efb5401227e91f49d8f7c4f6689fa27
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651169"
---
# <a name="cmfctoolbarinfo-class"></a>Класс CMFCToolBarInfo

Содержит идентификаторы ресурса изображений панели инструментов в различных состояниях. `CMFCToolBarInfo` — Это вспомогательный класс, который используется как параметр [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) метод.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarInfo
```

## <a name="members"></a>Участники

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|Идентификатор ресурса точечного рисунка панели инструментов, который содержит изображения регулярных (холодные) панели инструментов.|
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|Идентификатор ресурса точечного рисунка панели инструментов, содержащее изображения отключенные панели инструментов.|
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|Идентификатор ресурса точечного рисунка панели инструментов, который содержит изображения выбранной панели инструментов ("Горячий").|
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|Идентификатор ресурса точечного рисунка панели инструментов, который содержит изображениям значков панели инструментов большой и регулярно.|
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|Идентификатор ресурса точечного рисунка панели инструментов, который содержит большие, отключить изображениям значков панели инструментов.|
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|Идентификатор ресурса точечного рисунка панели инструментов, который содержит большие, выбрать изображениям значков панели инструментов.|
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|Идентификатор ресурса точечного рисунка панели инструментов, который содержит отключенным изображениям значков меню.|
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|Идентификатор ресурса точечного рисунка панели инструментов, который содержит изображения меню.|

## <a name="remarks"></a>Примечания

Битовая карта инструментов полностью состоит из изображений на панели инструментов small (кнопки) фиксированного размера. Каждый идентификатор ресурса, который хранится в `CMFCToolBarInfo` объект — это битовая карта, содержит полный набор инструментов образов в одном состоянии (для примере выбран отключено, большие, образы или меню).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbar.h

##  <a name="m_uicoldresid"></a>  CMFCToolBarInfo::m_uiColdResID

Указывает идентификатор ресурса для всех образов обычной кнопки панели инструментов.

```
UINT m_uiColdResID;
```

##  <a name="m_uidisabledresid"></a>  CMFCToolBarInfo::m_uiDisabledResID

Указывает идентификатор ресурса для изображений недоступна кнопка панели инструментов.

```
UINT m_uiDisabledResID;
```

##  <a name="m_uihotresid"></a>  CMFCToolBarInfo::m_uiHotResID

Указывает идентификатор ресурса для всех образов выделенной кнопки на панели инструментов.

```
UINT m_uiHotResID
```

##  <a name="m_uilargecoldresid"></a>  CMFCToolBarInfo::m_uiLargeColdResID

Указывает идентификатор ресурса для всех изображений больших обычной кнопки панели инструментов.

```
UINT m_uiLargeColdResID
```

##  <a name="m_uilargedisabledresid"></a>  CMFCToolBarInfo::m_uiLargeDisabledResID

Указывает идентификатор ресурса для всех изображений больших отключенной кнопки панели инструментов.

```
UINT m_uiLargeDisabledResID;
```

##  <a name="m_uilargehotresid"></a>  CMFCToolBarInfo::m_uiLargeHotResID

Указывает идентификатор ресурса для всех больших изображений выделенной панели инструментов.

```
UINT m_uiLargeHotResID;
```

##  <a name="m_uimenudisabledresid"></a>  CMFCToolBarInfo::m_uiMenuDisabledResID

Указывает идентификатор ресурса для изображений, недоступным для команды панели инструментов.

```
UINT m_uiMenuDisabledResID;
```

##  <a name="m_uimenuresid"></a>  CMFCToolBarInfo::m_uiMenuResID

Указывает идентификатор ресурса для всех обычным изображениям значков меню элемента панели инструментов.

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
