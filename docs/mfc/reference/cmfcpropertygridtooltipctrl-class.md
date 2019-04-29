---
title: Класс CMFCPropertyGridToolTipCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
ms.openlocfilehash: 6c14ed1f11a7a414332b34566a314459d76b911b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310478"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>Класс CMFCPropertyGridToolTipCtrl

Реализует подсказку, управления, [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) используется для отображения подсказки.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|name|Описание|
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Создает объект `CMFCPropertyGridToolTipCtrl`.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|name|Описание|
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Создает окно для элемента управления tooltip.|
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Отключает и скрывает элемент управления tooltip.|
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Возвращает координаты последней позиции элемента управления tooltip.|
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Скрывает элемент управления tooltip.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Задает расстояние между текстом всплывающей подсказки и границы окна всплывающей подсказки.|
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Отображает элемент управления tooltip.|

## <a name="remarks"></a>Примечания

Всплывающие подсказки отображаются при наведении указателя на имя свойства. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) класс отображает подсказку, так как это читаемые пользователем. Как правило положение всплывающей подсказки определяется положением указателя. С помощью этого класса, подсказка отображается над имя свойства и напоминает расширение естественным свойство, так что имя свойства становится полностью видимым.

MFC автоматически создает этот элемент управления и использует его в [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCPropertyGridToolTipCtrl` , а также для отображения элемента управления tooltip.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertygridtooltipctrl.h

##  <a name="cmfcpropertygridtooltipctrl"></a>  CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl

Создает объект `CMFCPropertyGridToolTipCtrl`.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

##  <a name="create"></a>  CMFCPropertyGridToolTipCtrl::Create

Создает окно для элемента управления tooltip.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Указатель на родительское окно.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно был успешно создан; в противном случае — значение FALSE.

##  <a name="deactivate"></a>  CMFCPropertyGridToolTipCtrl::Deactivate

Отключает и скрывает элемент управления tooltip.

```
void Deactivate();
```

### <a name="remarks"></a>Примечания

Этот метод задает положение и текст последнего пустых значениях необходимо знать, таким образом, чтобы вызовы будущего [CMFCPropertyGridToolTipCtrl::Track](#track) отображения всплывающей подсказки.

##  <a name="getlastrect"></a>  CMFCPropertyGridToolTipCtrl::GetLastRect

Возвращает координаты последней позиции элемента управления tooltip.

```
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

*rect*<br/>
[out] Содержит последней позиции элемента управления tooltip.

##  <a name="hide"></a>  CMFCPropertyGridToolTipCtrl::Hide

Скрывает элемент управления tooltip.

```
void Hide();
```

##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin

Задает расстояние между текстом всплывающей подсказки и границы окна всплывающей подсказки.

```
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>Параметры

*nTextMargin*<br/>
[in] Задает расстояние между текст всплывающей подсказки элемента управления и границей окна всплывающей подсказки. Значение по умолчанию — 10 пикселей.

##  <a name="track"></a>  CMFCPropertyGridToolTipCtrl::Track

Отображает элемент управления tooltip.

```
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
[in] Указывает положение и размер элемента управления tooltip.

*strText*<br/>
[in] Задает текст, отображаемый во всплывающей подсказке.

### <a name="remarks"></a>Примечания

Этот метод отображает элемент управления всплывающей подсказки в положение и размер, указанный параметром *rect*. Если позиция, размер и текст не изменились с момента последнего этот метод был вызван, этот метод не действует.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
