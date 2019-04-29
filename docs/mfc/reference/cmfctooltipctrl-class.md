---
title: Класс CMFCToolTipCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
ms.openlocfilehash: aaf9d9570906b7886d8ec78575c39db5d62099f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388310"
---
# <a name="cmfctooltipctrl-class"></a>Класс CMFCToolTipCtrl

Расширенная реализация всплывающей подсказки на основе класса [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md). Подсказка на основе класса `CMFCToolTipCtrl` может отображать значок, метку и описание. Можно настроить его внешний вид с помощью градиентной заливки, пользовательских цветов текста и границы, полужирного шрифта, скругленных углов или стиля всплывающего предупреждения.

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Возвращает размер значка во всплывающей подсказке.|
|[CMFCToolTipCtrl::GetParams](#getparams)|Возвращает параметры отображения всплывающей подсказки.|
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Рисует границу всплывающей подсказки.|
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Отображает значок во всплывающей подсказке.|
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Рисует заголовок всплывающей подсказки или вычисляет размер метки.|
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Рисует разделитель между меткой и описанием во всплывающей подсказке.|
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Заливает фон всплывающей подсказки.|
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Задает описание, которое отображается во всплывающей подсказке.|
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||
|[CMFCToolTipCtrl::SetLocation](#setlocation)||
|[CMFCToolTipCtrl::SetParams](#setparams)|Задает внешний вид всплывающей подсказки с помощью объекта `CMFCToolTipInfo`.|

## <a name="remarks"></a>Примечания

Используйте `CMFCToolTipCtrl`, `CMFCToolTipInfo`, и [класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) объектов друг с другом, чтобы реализовать в своем приложении настроенные всплывающие подсказки.

Например, чтобы реализовать всплывающие подсказки в виде выносок, сделайте следующее:

1. Используйте [класс CWinAppEx](../../mfc/reference/cwinappex-class.md) метод для инициализации диспетчера всплывающих подсказок в приложении.

2. Создайте структуру `CMFCToolTipInfo`, чтобы задать необходимый стиль оформления:

```
CMFCToolTipInfo params;
    params.m_bBoldLabel = FALSE;
    params.m_bDrawDescription = FALSE;
    params.m_bDrawIcon = FALSE;
    params.m_bRoundedCorners = TRUE;
    params.m_bDrawSeparator = FALSE;
    if (m_bCustomColors)
{
    params.m_clrFill = RGB (255,
    255,
    255);

    params.m_clrFillGradient = RGB (228,
    228,
    240);

    params.m_clrText = RGB (61,
    83,
    80);

    params.m_clrBorder = RGB (144,
    149,
    168);

}
```
3. Используйте [CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) метод, чтобы задать стиль оформления для всех всплывающих подсказок в приложении с помощью стили, определенные в `CMFCToolTipInfo` объекта:

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```
Для управления поведением всплывающей подсказки и ее отрисовкой вы также можете получить новый производный класс из класса `CMFCToolTipCtrl`. Чтобы задать новый класс элемента управления "Всплывающая подсказка", используйте метод `CTooltipManager::SetTooltipParams`:

```
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```
Чтобы восстановить класс элемента управления "Всплывающая подсказка" по умолчанию и сбросить оформление подсказки на стандартное, укажите значение NULL в классе среды выполнения и параметрах всплывающей подсказки в методе `SetTooltipParams`:

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>Пример

В следующем примере демонстрируется создание объекта `CMFCToolTipCtrl`, задание описания, отображаемого во всплывающей подсказке, а также задание ширины элемента управления "Всплывающая подсказка".

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtooltipctrl.h

##  <a name="cmfctooltipctrl"></a>  CMFCToolTipCtrl::CMFCToolTipCtrl

```
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>Параметры

[in] *pParams*<br/>

### <a name="remarks"></a>Примечания

##  <a name="geticonsize"></a>  CMFCToolTipCtrl::GetIconSize

Возвращает размер значка во всплывающей подсказке.

```
virtual CSize GetIconSize();
```

### <a name="return-value"></a>Возвращаемое значение

Размер значка в пикселях.

##  <a name="getparams"></a>  CMFCToolTipCtrl::GetParams

Возвращает параметры отображения всплывающей подсказки.

```
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущие параметры отображения всплывающей подсказки, которые хранятся в [класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) объекта.

##  <a name="ondrawborder"></a>  CMFCToolTipCtrl::OnDrawBorder

Рисует границу всплывающей подсказки.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rect*<br/>
[in] Ограничивающий прямоугольник всплывающей подсказки.

*clrLine*<br/>
[in] Цвет границы.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы настроить внешний вид границы всплывающей подсказки.

##  <a name="ondrawdescription"></a>  CMFCToolTipCtrl::OnDrawDescription

```
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rect*<br/>
[in] *bCalcOnly*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ondrawicon"></a>  CMFCToolTipCtrl::OnDrawIcon

Отображает значок во всплывающей подсказке.

```
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rectImage*<br/>
[in] Координаты значка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если значок рисования. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы отобразить пользовательский значок. Необходимо также переопределить [CMFCToolTipCtrl::GetIconSize](#geticonsize) для включения всплывающей подсказки обеспечить правильное вычисление макета текста и описание.

##  <a name="ondrawlabel"></a>  CMFCToolTipCtrl::OnDrawLabel

Рисует заголовок всплывающей подсказки или вычисляет размер метки.

```
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rect*<br/>
[in] Ограничивающий прямоугольник области метки.

*bCalcOnly*<br/>
[in] Значение TRUE, если метка не будет рисоваться.

### <a name="return-value"></a>Возвращаемое значение

Размер метки, в пикселях.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, если вы хотите настроить внешний вид метка всплывающей подсказки.

##  <a name="ondrawseparator"></a>  CMFCToolTipCtrl::OnDrawSeparator

Рисует разделитель между меткой и описанием во всплывающей подсказке.

```
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*x1*<br/>
[in] Горизонтальная координата в левый конец разделителя.

*x2*<br/>
[in] Горизонтальная координата справа от разделителя.

*Y*<br/>
[in] Вертикальная координата разделителя.

### <a name="remarks"></a>Примечания

Реализация по умолчанию проводит линию из точки (x1, y) до точки (x2, y).

Переопределите этот метод в производном классе, чтобы настроить внешний вид разделителя.

##  <a name="onfillbackground"></a>  CMFCToolTipCtrl::OnFillBackground

Заливает фон всплывающей подсказки.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*rect*<br/>
[in] Указывает прямоугольник, ограничивающий область для заливки.

*clrText*<br/>
[in] Цвет фона всплывающей подсказки.

*clrLine*<br/>
[in] Цвет границы и линии разделителя между элементами label и описание.

### <a name="remarks"></a>Примечания

Реализация по умолчанию заполняет прямоугольник, который задается параметром *rect* цветом или шаблону, указанному в последний вызов к [CMFCToolTipCtrl::SetParams](#setparams).

Переопределите этот метод в производном классе, если вы хотите настроить внешний вид всплывающей подсказки.

##  <a name="setdescription"></a>  CMFCToolTipCtrl::SetDescription

Задает описание, которое отображается во всплывающей подсказке.

```
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>Параметры

*strDesrciption*<br/>
[in] Текст описания.

### <a name="remarks"></a>Примечания

Текст описания отображается на всплывающей подсказки в поле разделитель.

##  <a name="setfixedwidth"></a>  CMFCToolTipCtrl::SetFixedWidth

```
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>Параметры

[in] *nWidthRegular*<br/>
[in] *nWidthLargeImage*<br/>

### <a name="remarks"></a>Примечания

##  <a name="sethotribbonbutton"></a>  CMFCToolTipCtrl::SetHotRibbonButton

```
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>Параметры

[in] *pRibbonButton*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setlocation"></a>  CMFCToolTipCtrl::SetLocation

```
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>Параметры

[in] *pt*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setparams"></a>  CMFCToolTipCtrl::SetParams

Задает внешний вид всплывающей подсказки с помощью [класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) объекта.

```
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>Параметры

*pParams*<br/>
[in] Указатель на [класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) объект, содержащий параметры отображения.

### <a name="remarks"></a>Примечания

Каждый раз, когда подсказка отображается, он отрисовывается с помощью цвета и визуальные стили, *pParams* указывает. Значение *pParams* хранится в защищенный член `m_Params`, который может осуществляться с помощью производного класса, который переопределяет [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl: : OnDrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator), или [CMFCToolTipCtrl::OnFillBackground](#onfillbackground)для сохранения указанного внешнего вида.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)<br/>
[Класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)<br/>
[Класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
