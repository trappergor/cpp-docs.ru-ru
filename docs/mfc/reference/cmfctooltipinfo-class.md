---
title: "Класс CMFCToolTipInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cda5da1b989ccc41a2f3136473dbe08200e091bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Логическая переменная, которая указывает, должны ли вид всплывающей подсказки контролироваться диспетчером визуального (см. [CMFCVisualManager класса](../../mfc/reference/cmfcvisualmanager-class.md)).|  
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Цвет границы всплывающей подсказки.|  
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Цвет фона всплывающей подсказки.|  
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Цвет градиентной заливки всплывающей подсказки.|  
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Цвет текста всплывающей подсказки.|  
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Угол градиентной заливки всплывающей подсказки.|  
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Максимальная возможная ширина описания во всплывающей подсказке (в пикселях).|  
  
## <a name="remarks"></a>Примечания  
 Используйте [класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, и [CTooltipManager класса](../../mfc/reference/ctooltipmanager-class.md) друг с другом, чтобы реализовать в своем приложении настроенные всплывающие подсказки. Пример использования этих классов см. в разделе [класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md) раздела.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется задание значений разных переменных-членов класса `CMFCToolTipInfo`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtooltipctrl.h  
  
##  <a name="m_bballoontooltip"></a>CMFCToolTipInfo::m_bBalloonTooltip  
 Задает стиль отображения для всех всплывающих подсказок.  
  
```  
BOOL m_bBalloonTooltip;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE`Указывает, что всплывающие подсказки использовать стиль выноски `FALSE` показывает, что всплывающие подсказки использовать прямоугольный стиля.  
  
##  <a name="m_bboldlabel"></a>CMFCToolTipInfo::m_bBoldLabel  
 Указывает, является ли полужирный шрифт текста всплывающей подсказки.  
  
```  
BOOL m_bBoldLabel;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения текста всплывающей подсказки с полужирным шрифтом или `FALSE` для отображения меток всплывающей подсказки с жирный шрифт.  
  
##  <a name="m_bdrawdescription"></a>CMFCToolTipInfo::m_bDrawDescription  
 Указывает, отображаются ли подсказки каждого текст описания.  
  
```  
BOOL m_bDrawDescription;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения описания или `FALSE` скрыть описание. Можно указать описание на всплывающей подсказке, вызвав [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)  
  
##  <a name="m_bdrawicon"></a>CMFCToolTipInfo::m_bDrawIcon  
 Отображение всех всплывающих подсказок значков.  
  
```  
BOOL m_bDrawIcon;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения значков на каждой подсказки или `FALSE` отображать подсказки без значков.  
  
##  <a name="m_bdrawseparator"></a>CMFCToolTipInfo::m_bDrawSeparator  
 Указывает, имеет ли каждый подсказки разделители между его метку и его описание.  
  
```  
BOOL m_bDrawSeparator;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения разделителем метка всплывающей подсказки и описание, или `FALSE` отображать подсказки без разделителя.  
  
##  <a name="m_broundedcorners"></a>CMFCToolTipInfo::m_bRoundedCorners  
 Указывает, имеют ли все подсказки скругленные углы.  
  
```  
BOOL m_bRoundedCorners;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения прямоугольника с закругленными углами в подсказки или `FALSE` для отображения углов прямоугольной во всплывающих подсказках.  
  
##  <a name="m_clrborder"></a>CMFCToolTipInfo::m_clrBorder  
 Задает цвет границы для всех всплывающих подсказок.  
  
```  
COLORREF m_clrBorder;  
```  
  
##  <a name="m_clrfill"></a>CMFCToolTipInfo::m_clrFill  
 Задает цвет фона всплывающей подсказки.  
  
```  
COLORREF m_clrFill;  
```  
  
### <a name="remarks"></a>Примечания  
 Если [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) равно -1, цвет фона всплывающей подсказки — `m_clrFill`. В противном случае `m_clrFill` определяет начало градиента цвет и `m_clrFillGradient` задает цвет конца градиента. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.  
  
##  <a name="m_clrfillgradient"></a>CMFCToolTipInfo::m_clrFillGradient  
 Задает конечный цвет градиента фона для всплывающих подсказок.  
  
```  
COLORREF m_clrFillGradient;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `m_clrFillGradient` равно -1, нет нет градиента. В противном случае задается начальный цвет градиента [CMFCToolTipInfo::m_clrFill](#m_clrfill) и цвет градиента Готово указан `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.  
  
##  <a name="m_clrtext"></a>CMFCToolTipInfo::m_clrText  
 Указывает цвет текста для всех всплывающих подсказок.  
  
```  
COLORREF m_clrText;  
```  
  
##  <a name="m_ngradientangle"></a>CMFCToolTipInfo::m_nGradientAngle  
 Задает угол, по которому будет использовано градиента фона для всплывающих подсказок.  
  
```  
int m_nGradientAngle;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_nGradientAngle`Указывает угол в градусах, градиента фона подсказок смещается от по горизонтали. Если `m_nGradientAngle` равно 0, градиента выводится слева направо. Если `m_nGradientAngle` — от 1 до 360, градиента поворот по часовой стрелке на это число градусов. Если `m_nGradientAngle` -1, значение по умолчанию градиента рисуется сверху вниз. Это то же самое, что параметр `m_nGradientAngle` 90.  
  
 [CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` определяет начало градиента цвет и [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` задает цвет конца градиента. Если `m_clrFillGradient` равно -1, нет нет градиента.  
  
##  <a name="m_nmaxdescrwidth"></a>CMFCToolTipInfo::m_nMaxDescrWidth  
 Задает максимальную ширину описание, оно отображается в каждой всплывающей подсказки. Если ширина описание превышает указанное значение, текст переносится.  
  
```  
int m_nMaxDescrWidth;  
```  
  
##  <a name="m_bvislmanagertheme"></a>CMFCToolTipInfo::m_bVislManagerTheme  
 Указывает, управляет ли диспетчер визуального представления приложения внешний вид всех всплывающих подсказок.  
  
```  
BOOL m_bVislManagerTheme;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `m_bVislManagerTheme` — `TRUE`, каждый подсказки запрашивает новый [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) из наглядный диспетчер приложения, прежде чем они отображаются на экране и использует значения в этом объекте, чтобы определить их внешний вид. Другие члены вашей [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) игнорируются.  
  
##  <a name="operator_eq"></a>CMFCToolTipInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)   
 [Класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)
