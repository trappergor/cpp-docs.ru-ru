---
title: Класс CMFCToolTipInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: b38c3a62cca376ef7a19a111fe3a34c923983d1b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270219"
---
# <a name="cmfctooltipinfo-class"></a>Класс CMFCToolTipInfo

Хранит сведения о внешнем виде подсказок.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolTipInfo
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCToolTipInfo::operator =](#operator_eq)||

### <a name="data-members"></a>Элементы данных

|name|Описание:|
|----------|-----------------|
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Логическая переменная, указывающая, имеет ли всплывающая подсказка вид выноски.|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Логическая переменная, указывающая, выделяются ли заголовки всплывающих подсказок жирным шрифтом.|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Логическая переменная, указывающая, содержит ли всплывающая подсказка описание.|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Логическая переменная, указывающая, содержит ли всплывающая подсказка значок.|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Логическая переменная, указывающая, имеется ли разделитель между заголовком всплывающей подсказки и описанием.|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Логическая переменная, указывающая, закруглены ли углы всплывающей подсказки.|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Логическая переменная, указывающее, должны ли вид всплывающей подсказки контролироваться диспетчером визуального (см. в разделе [класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)).|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Цвет границы всплывающей подсказки.|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Цвет фона всплывающей подсказки.|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Цвет градиентной заливки всплывающей подсказки.|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Цвет текста всплывающей подсказки.|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Угол градиентной заливки всплывающей подсказки.|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Максимальная возможная ширина описания во всплывающей подсказке (в пикселях).|

## <a name="remarks"></a>Примечания

Используйте [класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, и [класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) друг с другом, чтобы реализовать в своем приложении настроенные всплывающие подсказки. Пример использования этих классов см. в разделе [класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md) раздела.

## <a name="example"></a>Пример

В следующем примере демонстрируется задание значений разных переменных-членов класса `CMFCToolTipInfo`.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtooltipctrl.h

##  <a name="m_bballoontooltip"></a>  CMFCToolTipInfo::m_bBalloonTooltip

Задает стиль отображения всех всплывающих подсказок.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>Примечания

Значение TRUE показывает, что всплывающие подсказки использовать стиль выноски, FALSE указывает, что всплывающие подсказки использовать стиль прямоугольной.

##  <a name="m_bboldlabel"></a>  CMFCToolTipInfo::m_bBoldLabel

Указывает, является ли шрифт текста всплывающей подсказки полужирным шрифтом.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>Примечания

Установите значение этого члена в значение true, чтобы отображаемый текст всплывающей подсказки с полужирным шрифтом, или FALSE для отображения всплывающей подсказки метки не жирный шрифт.

##  <a name="m_bdrawdescription"></a>  CMFCToolTipInfo::m_bDrawDescription

Указывает, отображаются ли подсказки каждого текст описания.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>Примечания

Установите значение этого члена в значение true, чтобы Отображаемое описание или значение FALSE, чтобы скрыть описание. Можно указать описание на всплывающей подсказке, вызвав [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)

##  <a name="m_bdrawicon"></a>  CMFCToolTipInfo::m_bDrawIcon

Указывает, является ли все всплывающие подсказки отображают значки.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>Примечания

Этот член присвоено значение TRUE, чтобы отобразить значок на каждой всплывающей подсказки, или значение FALSE для отображения подсказки без значков.

##  <a name="m_bdrawseparator"></a>  CMFCToolTipInfo::m_bDrawSeparator

Указывает, имеет ли каждый подсказки разделитель между его метки и ее описание.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>Примечания

Этот член присвоено значение TRUE для отображения разделителя между метка всплывающей подсказки и описание, или значение FALSE для отображения подсказки без разделителя.

##  <a name="m_broundedcorners"></a>  CMFCToolTipInfo::m_bRoundedCorners

Указывает, имеют ли все подсказки скругленные углы.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>Примечания

Установите значение этого члена в значение true для отображения округленное углы во всплывающих подсказках, или FALSE для отображения углов прямоугольной во всплывающих подсказках.

##  <a name="m_clrborder"></a>  CMFCToolTipInfo::m_clrBorder

Задает цвет границы для всех всплывающих подсказок.

```
COLORREF m_clrBorder;
```

##  <a name="m_clrfill"></a>  CMFCToolTipInfo::m_clrFill

Задает цвет фона всплывающей подсказки.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>Примечания

Если [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) равно -1, цвет фона всплывающей подсказки — `m_clrFill`. В противном случае `m_clrFill` цвет начало градиента и `m_clrFillGradient` цвет конца градиента. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.

##  <a name="m_clrfillgradient"></a>  CMFCToolTipInfo::m_clrFillGradient

Задает конечный цвет градиента фона для всплывающих подсказок.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>Примечания

Если `m_clrFillGradient` равно -1, имеется без градиента. В противном случае начальный цвет градиента определяется [CMFCToolTipInfo::m_clrFill](#m_clrfill) и цвет градиента Готово указан `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.

##  <a name="m_clrtext"></a>  CMFCToolTipInfo::m_clrText

Задает цвет текста для всех всплывающих подсказок.

```
COLORREF m_clrText;
```

##  <a name="m_ngradientangle"></a>  CMFCToolTipInfo::m_nGradientAngle

Задает угол, с которой рисуется градиент на заднем плане подсказки.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>Примечания

`m_nGradientAngle` Указывает угол в градусах, что градиента на фоне подсказок смещено по горизонтали. Если `m_nGradientAngle` равно 0, градиента рисуется в направлении слева направо. Если `m_nGradientAngle` — от 1 до 360, градиента поворот по часовой стрелке на это число градусов. Если `m_nGradientAngle` используется значение -1, значение по умолчанию градиента рисуется сверху вниз. Это совпадает со значением параметра `m_nGradientAngle` 90.

[CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` цвет начало градиента и [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` цвет конца градиента. Если `m_clrFillGradient` равно -1, имеется без градиента.

##  <a name="m_nmaxdescrwidth"></a>  CMFCToolTipInfo::m_nMaxDescrWidth

Указывает максимальную ширину описание, которое он отображается в каждом всплывающей подсказки. Если ширина описание превышает указанное значение, текст переносится.

```
int m_nMaxDescrWidth;
```

##  <a name="m_bvislmanagertheme"></a>  CMFCToolTipInfo::m_bVislManagerTheme

Указывает, управляет ли наглядный диспетчер приложения внешний вид всех всплывающих подсказок.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>Примечания

Если `m_bVislManagerTheme` имеет значение TRUE, каждый подсказки запрашивает новый [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) из наглядный диспетчер приложения, прежде чем они отображаются на экране и использует значения в этом объекте, чтобы определить их внешний вид. Другие члены вашей [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) игнорируются.

##  <a name="operator_eq"></a>  CMFCToolTipInfo::operator=

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>Параметры

[in] *src*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)<br/>
[Класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)
