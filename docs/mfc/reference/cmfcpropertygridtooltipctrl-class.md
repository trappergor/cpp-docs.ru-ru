---
title: Класс Кмфкпропертигридтултипктрл
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
ms.openlocfilehash: f1b6f626b5f9844c73cd2225a7d6311f5b2f7d4f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505096"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>Класс Кмфкпропертигридтултипктрл

Реализует элемент управления ToolTip, который [класс кмфкпропертигридктрл](../../mfc/reference/cmfcpropertygridctrl-class.md) использует для вывода всплывающих подсказок.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|name|Описание|
|[Кмфкпропертигридтултипктрл:: Кмфкпропертигридтултипктрл](#cmfcpropertygridtooltipctrl)|Создает объект `CMFCPropertyGridToolTipCtrl`.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|name|Описание|
|[Кмфкпропертигридтултипктрл:: Create](#create)|Создает окно для элемента управления ToolTip.|
|[Кмфкпропертигридтултипктрл::D еактивате](#deactivate)|Деактивирует и скрывает элемент управления ToolTip.|
|[Кмфкпропертигридтултипктрл:: Жетластрект](#getlastrect)|Возвращает координаты последней положения элемента управления ToolTip.|
|[Кмфкпропертигридтултипктрл:: Hide](#hide)|Скрывает элемент управления ToolTip.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Задает интервал между текстом подсказки и границей окна подсказки.|
|[Кмфкпропертигридтултипктрл:: Track](#track)|Отображает элемент управления ToolTip.|

## <a name="remarks"></a>Примечания

Подсказки отображаются при наведении указателя мыши на имя свойства. Класс [кмфкпропертигридтултипктрл](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) отображает подсказку, чтобы она была легко читаема пользователем. Как правило, расположение подсказки определяется положением указателя. С помощью этого класса всплывающая подсказка отображается над именем свойства и напоминает расширение естественного свойства, чтобы имя свойства было полностью видимым.

MFC автоматически создает этот элемент управления и использует его в [классе кмфкпропертигридктрл](../../mfc/reference/cmfcpropertygridctrl-class.md).

## <a name="example"></a>Пример

В следующем примере показано, как создать объект `CMFCPropertyGridToolTipCtrl` класса и как отобразить элемент управления ToolTip.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[кмфкпропертигридтултипктрл](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкспропертигридтултипктрл. h

##  <a name="cmfcpropertygridtooltipctrl"></a>Кмфкпропертигридтултипктрл:: Кмфкпропертигридтултипктрл

Создает объект `CMFCPropertyGridToolTipCtrl`.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

##  <a name="create"></a>Кмфкпропертигридтултипктрл:: Create

Создает окно для элемента управления ToolTip.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*пвндпарент*<br/>
окне Указатель на родительское окно.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно было успешно создано; в противном случае — значение FALSE.

##  <a name="deactivate"></a>Кмфкпропертигридтултипктрл::D еактивате

Деактивирует и скрывает элемент управления ToolTip.

```
void Deactivate();
```

### <a name="remarks"></a>Примечания

Этот метод задает для последней позицией и текста пустые значения, чтобы будущие вызовы [кмфкпропертигридтултипктрл:: Track](#track) отображали подсказку.

##  <a name="getlastrect"></a>Кмфкпропертигридтултипктрл:: Жетластрект

Возвращает координаты последней положения элемента управления ToolTip.

```
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

*rect*<br/>
заполняет Содержит последнюю точку элемента управления ToolTip.

##  <a name="hide"></a>Кмфкпропертигридтултипктрл:: Hide

Скрывает элемент управления ToolTip.

```
void Hide();
```

##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin

Задает интервал между текстом подсказки и границей окна подсказки.

```
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>Параметры

*нтекстмаргин*<br/>
окне Задает интервал между текстом элемента управления ToolTip и границей окна подсказки. Значение по умолчанию — 10 пикселей.

##  <a name="track"></a>Кмфкпропертигридтултипктрл:: Track

Отображает элемент управления ToolTip.

```
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
окне Задает расположение и размер элемента управления ToolTip.

*стртекст*<br/>
окне Задает текст, отображаемый во всплывающей подсказке.

### <a name="remarks"></a>Примечания

Этот метод отображает элемент управления ToolTip в позиции и размере, заданном параметром *Rect*. Если расположение, размер и текст не изменялись с момента последнего вызова этого метода, этот метод не оказывает никакого влияния.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
