---
title: "Класс CMFCRibbonSlider | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider class
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
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
ms.openlocfilehash: 9f05ae7d0f3e1775a3321928867471749e11e679
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonslider-class"></a>Класс CMFCRibbonSlider
`CMFCRibbonSlider` Класс реализует ползунок, можно добавить строку ленты или строки состояния ленты. Элемент управления "ползунок" ленты напоминает ползунки масштаба, отображаемые в приложениях Office 2007.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Создает и инициализирует элемент управления "ползунок" ленты.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|Возвращает текущее положение ползунка.|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Возвращает максимальное значение ползунка.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Возвращает минимальное значение ползунка.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Возвращает размер шаг масштабирования для элемента управления "ползунок".|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Указывает, имеет ли ползунок масштаба кнопки.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|Задает текущее положение ползунка.|  
|[CMFCRibbonSlider::SetRange](#setrange)|Указывает диапазон ползунком, задав минимальное и максимальное значения.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Отображение или скрытие кнопки масштабирования.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Задает размер шаг масштабирования для элемента управления "ползунок".|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `SetRange` метод для настройки диапазона увеличивает масштаб для ползунка. Текущее положение ползунка можно задать с помощью `SetPos` метод.  
  
 Можно отобразить кнопки циклические масштабирования слева и справа от ползунка с помощью `SetZoomButtons` метод. По умолчанию горизонтальный ползунок, масштаб левой кнопки отображается знак «минус» и кнопка справа масштабирования отображается знак плюс.  
  
 `SetZoomIncrement` Определяет приращение, добавить или вычесть из текущей позиции, при нажатии кнопки масштабирования.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCRibbonSlider` класс, чтобы задать свойства ползунок. В примере показано `CMFCRibbonSlider` , отображения кнопки масштабирования, задать текущее положение ползунка и задать диапазон значений для элемента управления "ползунок".  
  
 [!code-cpp[NVC_MFC_RibbonApp&#12;](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonslider.h  
  
##  <a name="a-namecmfcribbonslidera--cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a>CMFCRibbonSlider::CMFCRibbonSlider  
 Создайте ползунок ленты.  
  
```  
CMFCRibbonSlider(
    UINT nID,  
    int nWidth=100);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор ползунка.  
  
 [in]. `nWidth`  
 Ползунок ширина в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Создает ползунок ленты, `nWidth` пикселов в категории панель, где будет добавлен ползунок. По умолчанию ползунок горизонтальной.  
  
##  <a name="a-namegetposa--cmfcribbonslidergetpos"></a><a name="getpos"></a>CMFCRibbonSlider::GetPos  
 Возвращает текущее положение ползунка.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее положение ползунка и положение относительно начала ползунка.  
  
##  <a name="a-namegetrangemaxa--cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a>CMFCRibbonSlider::GetRangeMax  
 Получает максимальное шаг ползунка, проходят ползунок на ползунке.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное шаг ползунка, проходят ползунок на ползунке.  
  
##  <a name="a-namegetrangemina--cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a>CMFCRibbonSlider::GetRangeMin  
 Возвращает минимальный промежуток, проходят ползунок в элементе управления "ползунок".  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальный промежуток ползунок могут проходить в элементе управления "ползунок".  
  
##  <a name="a-namegetregularsizea--cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetzoomincrementa--cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a>CMFCRibbonSlider::GetZoomIncrement  
 Получите шаг масштабирования для элемента управления "ползунок".  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Шаг масштабирования для элемента управления "ползунок".  
  
##  <a name="a-namehaszoombuttonsa--cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a>CMFCRibbonSlider::HasZoomButtons  
 Указывает, имеет ли ползунок масштаба кнопки.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если ползунок масштаба кнопок; `FALSE` в противном случае.  
  
##  <a name="a-nameondrawa--cmfcribbonsliderondraw"></a><a name="ondraw"></a>CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetposa--cmfcribbonslidersetpos"></a><a name="setpos"></a>CMFCRibbonSlider::SetPos  
 Задайте текущее положение ползунка.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPos`  
 Указывает позицию для ползунка. Позиция является относительно начала ползунка.  
  
 [in] `bRedraw`  
 Если `TRUE`, перерисовывается ползунка.  
  
##  <a name="a-namesetrangea--cmfcribbonslidersetrange"></a><a name="setrange"></a>CMFCRibbonSlider::SetRange  
 Задайте диапазон значений для элемента управления "ползунок".  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMin`  
 Указывает минимальное значение ползунка.  
  
 [in] `nMax`  
 Указывает максимальное значение ползунка.  
  
### <a name="remarks"></a>Примечания  
 Указывает диапазон значений для элемента управления slider, задав минимальное и максимальное значения.  
  
##  <a name="a-namesetzoombuttonsa--cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a>CMFCRibbonSlider::SetZoomButtons  
 Отображение или скрытие кнопки масштабирования.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in]. `bSet`  
 `TRUE`для отображения кнопки масштабирования; `FALSE` скрыть их.  
  
##  <a name="a-namesetzoomincrementa--cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a>CMFCRibbonSlider::SetZoomIncrement  
 Установите шаг масштабирования для элемента управления "ползунок".  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nZoomIncrement`  
 Задает шаг масштабирования элемента управления ползунка.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

