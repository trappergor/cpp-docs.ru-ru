---
title: CmFCPropertyGridToolToolTipCtrl класс
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
ms.openlocfilehash: 94d75f914e5f7928d08dd2a87997ab02c4f16832
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361790"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CmFCPropertyGridToolToolTipCtrl класс

Реализует инструментарий управления, что [CMFCPropertyGridCtrl класса](../../mfc/reference/cmfcpropertygridctrl-class.md) использует для отображения инструментов.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCPropertyGridGridToolTipCtrl::CMFCPropertyGridToolToolCtrl](#cmfcpropertygridtooltipctrl)|Формирует объект `CMFCPropertyGridToolTipCtrl`.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCPropertyGridGridToolTipCtrl::Создание](#create)|Создает окно для управления набором инструментов.|
|[CMFCPropertyGridToolTipCtrl::Dэактив](#deactivate)|Деактивирует и скрывает элемент управления.|
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Возвращает координаты последней позиции управления набором инструментов.|
|[CMFCPropertyGridGridToolTipCtrl::Скрыть](#hide)|Скрывает элемент управления инструментом.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCPropertyGridGridToolTipCtrl::SetTextMargin](#settextmargin)|Устанавливает расстояние между текстом tooltip и границей окна tooltip.|
|[CMFCPropertyGridGridToolTipCtrl::Track](#track)|Отображает элемент управления набором инструментов.|

## <a name="remarks"></a>Remarks

Наборы инструментов отображаются, когда указатель опирается на имя свойства. Класс [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) отображает набор инструментов, чтобы он был легко читаемым пользователем. Обычно положение инструмента определяется положением указателя. Используя этот класс, набор инструментов отображается над именем свойства и напоминает расширение естественного свойства, так что имя свойства будет полностью видимым.

MFC автоматически создает этот элемент управления и использует его в [классе CMFCPropertyGridCtrl.](../../mfc/reference/cmfcpropertygridctrl-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCPropertyGridToolTipCtrl` построить объект класса и как отобразить элемент управления набором инструментов.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPropertyGridGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertygridtooltipctrl.h

## <a name="cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridGridToolTipCtrl::CMFCPropertyGridToolToolCtrl

Формирует объект `CMFCPropertyGridToolTipCtrl`.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

## <a name="cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a>CMFCPropertyGridGridToolTipCtrl::Создание

Создает окно для управления набором инструментов.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на родительское окно.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если окно было успешно создано; в противном случае, FALSE.

## <a name="cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Dэактив

Деактивирует и скрывает элемент управления.

```
void Deactivate();
```

### <a name="remarks"></a>Remarks

Этот метод устанавливает последнюю позицию и текст для пустых значений, так что будущие звонки [на CMFCPropertyGridToolTipCtrl::Track](#track) отображение инструмента.

## <a name="cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect

Возвращает координаты последней позиции управления набором инструментов.

```
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(ваут) Содержит последнюю позицию элемента управления инструментом.

## <a name="cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a>CMFCPropertyGridGridToolTipCtrl::Скрыть

Скрывает элемент управления инструментом.

```
void Hide();
```

## <a name="cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a>CMFCPropertyGridGridToolTipCtrl::SetTextMargin

Устанавливает расстояние между текстом tooltip и границей окна tooltip.

```
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>Параметры

*nTextMargin*<br/>
(в) Определяет расстояние между текстом управления набором инструментов и границей окна tooltip. Значение по умолчанию составляет 10 пикселей.

## <a name="cmfcpropertygridtooltipctrltrack"></a><a name="track"></a>CMFCPropertyGridGridToolTipCtrl::Track

Отображает элемент управления набором инструментов.

```
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Определяет положение и размер управления набором инструментов.

*strText*<br/>
(в) Упоняет текст, который будет отображаться в наборе инструментов.

### <a name="remarks"></a>Remarks

Этот метод отображает элемент управления инструментом в положении и размер, указанный *rect.* Если положение, размер и текст не изменились с момента последнего вызова этого метода, этот метод не имеет эффекта.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
