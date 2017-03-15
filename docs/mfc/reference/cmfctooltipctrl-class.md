---
title: "Класс от CMFCToolTipCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipCtrl class
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
caps.latest.revision: 33
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c4acd1cff8b3ce6fb4815ad78ad91225b385d547
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctooltipctrl-class"></a>Класс от CMFCToolTipCtrl
Расширенная реализация подсказки на основе [CToolTipCtrl-класс](../../mfc/reference/ctooltipctrl-class.md). Подсказка на основе класса `CMFCToolTipCtrl` может отображать значок, метку и описание. Можно настроить его внешний вид с помощью градиентной заливки, пользовательских цветов текста и границы, полужирного шрифта, скругленных углов или стиля всплывающего предупреждения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
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
 Используйте `CMFCToolTipCtrl`, `CMFCToolTipInfo`, и [CTooltipManager класс](../../mfc/reference/ctooltipmanager-class.md) объектов вместе, чтобы реализовать настраиваемый всплывающих подсказок в приложении.  
  
 Например, чтобы реализовать всплывающие подсказки в виде выносок, сделайте следующее:  
  
 1. Используйте [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) метод для инициализации диспетчера подсказки в приложении.  
  
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
3. Используйте [CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) метод для задания стиля оформления для всех подсказок в приложении, используя стили, определенные в `CMFCToolTipInfo` объекта:  
  
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
  
 [!code-cpp[NVC_MFC_RibbonApp&#41;](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [От CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtooltipctrl.h  
  
##  <a name="a-namecmfctooltipctrla--cmfctooltipctrlcmfctooltipctrl"></a><a name="cmfctooltipctrl"></a>CMFCToolTipCtrl::CMFCToolTipCtrl  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParams`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegeticonsizea--cmfctooltipctrlgeticonsize"></a><a name="geticonsize"></a>CMFCToolTipCtrl::GetIconSize  
 Возвращает размер значка во всплывающей подсказке.  
  
```  
virtual CSize GetIconSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер значка в пикселях.  
  
##  <a name="a-namegetparamsa--cmfctooltipctrlgetparams"></a><a name="getparams"></a>CMFCToolTipCtrl::GetParams  
 Возвращает параметры отображения всплывающей подсказки.  
  
```  
const CMFCToolTipInfo& GetParams() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущие параметры отображения всплывающей подсказки, которые хранятся в [CMFCToolTipInfo класс](../../mfc/reference/cmfctooltipinfo-class.md) объекта.  
  
##  <a name="a-nameondrawbordera--cmfctooltipctrlondrawborder"></a><a name="ondrawborder"></a>CMFCToolTipCtrl::OnDrawBorder  
 Рисует границу всплывающей подсказки.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] pDC`  
 Указатель на контекст устройства.  
  
 `[in] rect`  
 Ограничивающий прямоугольник всплывающей подсказки.  
  
 `[in] clrLine`  
 Цвет границы.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид границы всплывающей подсказки.  
  
##  <a name="a-nameondrawdescriptiona--cmfctooltipctrlondrawdescription"></a><a name="ondrawdescription"></a>CMFCToolTipCtrl::OnDrawDescription  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize OnDrawDescription(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawicona--cmfctooltipctrlondrawicon"></a><a name="ondrawicon"></a>CMFCToolTipCtrl::OnDrawIcon  
 Отображает значок во всплывающей подсказке.  
  
```  
virtual BOOL OnDrawIcon(
    CDC* pDC,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectImage`  
 Координаты значок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если значок был нарисован. В противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы отобразить пользовательский значок. Необходимо также переопределить [CMFCToolTipCtrl::GetIconSize](#geticonsize) включение всплывающей подсказки для верного вычисления макета текста и описание.  
  
##  <a name="a-nameondrawlabela--cmfctooltipctrlondrawlabel"></a><a name="ondrawlabel"></a>CMFCToolTipCtrl::OnDrawLabel  
 Рисует заголовок всплывающей подсказки или вычисляет размер метки.  
  
```  
virtual CSize OnDrawLabel(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] pDC`  
 Указатель на контекст устройства.  
  
 `[in] rect`  
 Ограничивающий прямоугольник области метки.  
  
 `[in] bCalcOnly`  
 Если `TRUE`, метки не отображаются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер метки в точках.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, если требуется настроить внешний вид метка всплывающей подсказки.  
  
##  <a name="a-nameondrawseparatora--cmfctooltipctrlondrawseparator"></a><a name="ondrawseparator"></a>CMFCToolTipCtrl::OnDrawSeparator  
 Рисует разделитель между меткой и описанием во всплывающей подсказке.  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    int x1,  
    int x2,  
    int y);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `x1`  
 Горизонтальная координата левый конец разделителя.  
  
 [in] `x2`  
 Горизонтальная координата справа от разделителя.  
  
 [in] `Y`  
 Вертикальная координата разделителя.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию рисуется линия от точки (x1, y) до точки (x2, y).  
  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид разделителя.  
  
##  <a name="a-nameonfillbackgrounda--cmfctooltipctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCToolTipCtrl::OnFillBackground  
 Заливает фон всплывающей подсказки.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect,  
    COLORREF& clrText,  
    COLORREF& clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] pDC`  
 Указатель на контекст устройства.  
  
 `[in] rect`  
 Указывает прямоугольник, ограничивающий область для заливки.  
  
 `[in] clrText`  
 Цвет фона для всплывающей подсказки.  
  
 `[in] clrLine`  
 Цвет границы и линии разделителя между метку и описание.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию заполняет прямоугольник, задаваемый `rect` цветом или шаблону, заданному в последнем вызове [CMFCToolTipCtrl::SetParams](#setparams).  
  
 Переопределите этот метод в производном классе, если требуется настроить внешний вид всплывающей подсказки.  
  
##  <a name="a-namesetdescriptiona--cmfctooltipctrlsetdescription"></a><a name="setdescription"></a>CMFCToolTipCtrl::SetDescription  
 Задает описание, которое отображается во всплывающей подсказке.  
  
```  
virtual void SetDescription(const CString strDesrciption);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] strDesrciption`  
 Текст описания.  
  
### <a name="remarks"></a>Примечания  
 Текст описания отображается на всплывающей подсказки в группе разделитель.  
  
##  <a name="a-namesetfixedwidtha--cmfctooltipctrlsetfixedwidth"></a><a name="setfixedwidth"></a>CMFCToolTipCtrl::SetFixedWidth  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetFixedWidth(
    int nWidthRegular,  
    int nWidthLargeImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nWidthRegular`  
 [in] `nWidthLargeImage`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesethotribbonbuttona--cmfctooltipctrlsethotribbonbutton"></a><a name="sethotribbonbutton"></a>CMFCToolTipCtrl::SetHotRibbonButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRibbonButton`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetlocationa--cmfctooltipctrlsetlocation"></a><a name="setlocation"></a>CMFCToolTipCtrl::SetLocation  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetLocation(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pt`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetparamsa--cmfctooltipctrlsetparams"></a><a name="setparams"></a>CMFCToolTipCtrl::SetParams  
 Определяет внешний вид всплывающей подсказки с помощью [CMFCToolTipInfo класс](../../mfc/reference/cmfctooltipinfo-class.md) объекта.  
  
```  
void SetParams(CMFCToolTipInfo* pParams);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] pParams`  
 Указатель на [CMFCToolTipInfo класс](../../mfc/reference/cmfctooltipinfo-class.md) , содержащий параметры отображения.  
  
### <a name="remarks"></a>Примечания  
 Каждый раз, когда подсказка отображается, рисуется с помощью цвета и визуальные стили, `pParams` указывает. Значение `pParams` хранится в защищенный член `m_Params`, которой может осуществляться с помощью производного класса, переопределяющего [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl::OnDrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator), или [CMFCToolTipCtrl::OnFillBackground](#onfillbackground) для сохранения указанного внешнего вида.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl-класс](../../mfc/reference/ctooltipctrl-class.md)   
 [Класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)   
 [Класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)

