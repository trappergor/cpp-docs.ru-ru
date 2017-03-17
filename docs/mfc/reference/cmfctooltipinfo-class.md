---
title: "Класс CMFCToolTipInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CMFCToolTipInfo class
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
caps.latest.revision: 27
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ed15ce9f3e1abb48c0a6c4eacdf662cc2ef3f9c9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctooltipinfo-class"></a>Класс CMFCToolTipInfo
Хранит сведения о внешнем виде подсказок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolTipInfo  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolTipInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Логическая переменная, указывающая, имеет ли всплывающая подсказка вид выноски.|  
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Логическая переменная, указывающая, выделяются ли заголовки всплывающих подсказок жирным шрифтом.|  
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Логическая переменная, указывающая, содержит ли всплывающая подсказка описание.|  
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Логическая переменная, указывающая, содержит ли всплывающая подсказка значок.|  
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Логическая переменная, указывающая, имеется ли разделитель между заголовком всплывающей подсказки и описанием.|  
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Логическая переменная, указывающая, закруглены ли углы всплывающей подсказки.|  
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Логическая переменная, которая указывает, управляется ли внешний вид всплывающей подсказки, диспетчер визуального представления (см. [CMFCVisualManager класса](../../mfc/reference/cmfcvisualmanager-class.md)).|  
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Цвет границы всплывающей подсказки.|  
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Цвет фона всплывающей подсказки.|  
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Цвет градиентной заливки всплывающей подсказки.|  
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Цвет текста всплывающей подсказки.|  
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Угол градиентной заливки всплывающей подсказки.|  
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Максимальная возможная ширина описания во всплывающей подсказке (в пикселях).|  
  
## <a name="remarks"></a>Примечания  
 Используйте [от CMFCToolTipCtrl класс](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, и [CTooltipManager класса](../../mfc/reference/ctooltipmanager-class.md) вместе, чтобы реализовать настраиваемый всплывающих подсказок в приложении. Пример использования этих классов подсказки в разделе [от CMFCToolTipCtrl класс](../../mfc/reference/cmfctooltipctrl-class.md) раздела.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется задание значений разных переменных-членов класса `CMFCToolTipInfo`.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#42;](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtooltipctrl.h  
  
##  <a name="m_bballoontooltip"></a>CMFCToolTipInfo::m_bBalloonTooltip  
 Задает стиль отображения всех подсказок.  
  
```  
BOOL m_bBalloonTooltip;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE`Указывает, что подсказки использовать стиль выноски `FALSE` означает, что подсказки использоваться прямоугольной стиля.  
  
##  <a name="m_bboldlabel"></a>CMFCToolTipInfo::m_bBoldLabel  
 Указывает, является ли шрифт текста подсказки полужирным шрифтом.  
  
```  
BOOL m_bBoldLabel;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения текста подсказки жирным шрифтом или `FALSE` для отображения всплывающей подсказки метки не полужирным шрифтом.  
  
##  <a name="m_bdrawdescription"></a>CMFCToolTipInfo::m_bDrawDescription  
 Указывает, отображаются ли подсказки каждого текст описания.  
  
```  
BOOL m_bDrawDescription;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения описания, или `FALSE` скрыть описание. Можно указать описание на всплывающей подсказке, вызвав [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)  
  
##  <a name="m_bdrawicon"></a>CMFCToolTipInfo::m_bDrawIcon  
 Отображение подсказок всех значков.  
  
```  
BOOL m_bDrawIcon;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения значка на каждой подсказки или `FALSE` для отображения подсказки без значков.  
  
##  <a name="m_bdrawseparator"></a>CMFCToolTipInfo::m_bDrawSeparator  
 Указывает, имеет ли каждый подсказки разделитель между его подпись и его описание.  
  
```  
BOOL m_bDrawSeparator;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения разделителя подсказки метку и описание, или `FALSE` для отображения подсказки без разделителя.  
  
##  <a name="m_broundedcorners"></a>CMFCToolTipInfo::m_bRoundedCorners  
 Указывает, имеют ли все подсказки скругленные углы.  
  
```  
BOOL m_bRoundedCorners;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для отображения прямоугольника с закругленными углами во всплывающих подсказках, или `FALSE` для отображения углов прямоугольной во всплывающих подсказках.  
  
##  <a name="m_clrborder"></a>CMFCToolTipInfo::m_clrBorder  
 Задает цвет границы на всех подсказок.  
  
```  
COLORREF m_clrBorder;  
```  
  
##  <a name="m_clrfill"></a>CMFCToolTipInfo::m_clrFill  
 Задает цвет фона для всплывающей подсказки.  
  
```  
COLORREF m_clrFill;  
```  
  
### <a name="remarks"></a>Примечания  
 Если [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) равно -1, цвет фона для всплывающей подсказки — `m_clrFill`. В противном случае — `m_clrFill` определяет цвет начала градиента и `m_clrFillGradient` определяет цвет конца градиента. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.  
  
##  <a name="m_clrfillgradient"></a>CMFCToolTipInfo::m_clrFillGradient  
 Задает конечный цвет градиента фона для всплывающих подсказок.  
  
```  
COLORREF m_clrFillGradient;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `m_clrFillGradient` равно -1, нет нет градиента. В противном случае — начальный цвет градиента определяется [CMFCToolTipInfo::m_clrFill](#m_clrfill) и цвет градиента Готово указан `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.  
  
##  <a name="m_clrtext"></a>CMFCToolTipInfo::m_clrText  
 Указывает цвет текста всех подсказок.  
  
```  
COLORREF m_clrText;  
```  
  
##  <a name="m_ngradientangle"></a>CMFCToolTipInfo::m_nGradientAngle  
 Задает угол, по которому будет использовано градиента фона подсказки.  
  
```  
int m_nGradientAngle;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_nGradientAngle`Указывает угол в градусах, градиента фона подсказки смещается от горизонтальной. Если `m_nGradientAngle` 0, при рисовании градиент слева направо. Если `m_nGradientAngle` — от 1 до 360 градиента поворот по часовой стрелке на указанное число градусов. Если `m_nGradientAngle` -1, значение по умолчанию градиента рисуется сверху вниз. Это то же самое, как параметр `m_nGradientAngle` 90.  
  
 [CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` определяет цвет начала градиента и [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` определяет цвет конца градиента. Если `m_clrFillGradient` равно -1, нет нет градиента.  
  
##  <a name="m_nmaxdescrwidth"></a>CMFCToolTipInfo::m_nMaxDescrWidth  
 Указывает максимальную ширину описание, оно отображается в каждой всплывающей подсказки. Если ширина описание превышает указанное значение, текст переносится.  
  
```  
int m_nMaxDescrWidth;  
```  
  
##  <a name="m_bvislmanagertheme"></a>CMFCToolTipInfo::m_bVislManagerTheme  
 Указывает, управляет ли диспетчер визуального представления приложения внешний вид всех подсказок.  
  
```  
BOOL m_bVislManagerTheme;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `m_bVislManagerTheme` — `TRUE`, каждый подсказки запрашивает новый [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) из диспетчер визуального представления приложения, прежде чем они отображаются на экране и использует значения в этом объекте, чтобы определить их внешний вид. Другие члены вашей [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) игнорируются.  
  
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
 [Класс от CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

