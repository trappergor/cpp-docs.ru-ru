---
title: Класс CMFCRibbonSlider | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4264f26028db4c581fe1dc143905ac0ffc8f66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372701"
---
# <a name="cmfcribbonslider-class"></a>Класс CMFCRibbonSlider
`CMFCRibbonSlider` Класс реализует элемент управления "ползунок", который можно добавить на панель ленты или строки состояния ленты. Элемент управления "ползунок" ленты напоминает ползунки масштаба, отображаемые в приложениях Office 2007.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Создает и инициализирует элемент управления "ползунок" ленты.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|Возвращает текущую позицию элемента управления "ползунок".|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Возвращает максимальное значение ползунка.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Возвращает минимальное значение ползунка.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Возвращает размер увеличения масштаба для элемента управления "ползунок".|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Указывает, имеет ли ползунком кнопок масштаба.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|Задает текущую позицию элемента управления "ползунок".|  
|[CMFCRibbonSlider::SetRange](#setrange)|Указывает диапазон элемента управления "ползунок", задав минимальное и максимальное значения.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Показывает или скрывает кнопки масштабирования.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Задает размер увеличения масштаба для элемента управления "ползунок".|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `SetRange` метод для настройки диапазона увеличивает масштаб для ползунка. Текущее положение ползунка можно задать с помощью `SetPos` метод.  
  
 Можно отобразить циклические масштаба кнопки в левой и правой части элемента управления "ползунок" с помощью `SetZoomButtons` метод. По умолчанию горизонтальный ползунок, кнопка слева масштаб отображает знак «минус» и кнопки масштаба справа отображается знак плюс.  
  
 `SetZoomIncrement` Метод определяет шаг, чтобы добавить или вычесть из текущей позиции, при нажатии кнопки масштабирования.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCRibbonSlider` класса для задания свойств ползунка. В примере показано `CMFCRibbonSlider` , отображения кнопок масштаба, задать текущую позицию элемента управления "ползунок" и задайте диапазон значений для элемента управления "ползунок".  
  
 [!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonslider.h  
  
##  <a name="cmfcribbonslider"></a>  CMFCRibbonSlider::CMFCRibbonSlider  
 Создайте ползунок ленты.  
  
```  
CMFCRibbonSlider(
    UINT nID,  
    int nWidth=100);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор ползунок.  
  
 [in]. `nWidth`  
 Ползунок ширина в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Создает ползунок ленты, `nWidth` пикселей в ширину в категории панели, куда добавляется ползунок. По умолчанию ползунка горизонтальной.  
  
##  <a name="getpos"></a>  CMFCRibbonSlider::GetPos  
 Возвращает текущую позицию элемента управления "ползунок".  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее положение ползунка и положение относительно начала ползунка.  
  
##  <a name="getrangemax"></a>  CMFCRibbonSlider::GetRangeMax  
 Получает максимальное увеличение ползунка входящей ползунок в элементе управления "ползунок".  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное увеличение ползунка входящей ползунок в элементе управления "ползунок".  
  
##  <a name="getrangemin"></a>  CMFCRibbonSlider::GetRangeMin  
 Возвращает минимальный шаг приращения, проходят ползунок в элементе управления "ползунок".  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальный шаг приращения, проходят ползунок в элементе управления "ползунок".  
  
##  <a name="getregularsize"></a>  CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getzoomincrement"></a>  CMFCRibbonSlider::GetZoomIncrement  
 Получите шаг масштабирования для элемента управления "ползунок".  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Шаг масштабирования для элемента управления "ползунок".  
  
##  <a name="haszoombuttons"></a>  CMFCRibbonSlider::HasZoomButtons  
 Указывает, имеет ли ползунком кнопок масштаба.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если ползунок имеются кнопки масштаба; `FALSE` в противном случае.  
  
##  <a name="ondraw"></a>  CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpos"></a>  CMFCRibbonSlider::SetPos  
 Задайте текущее положение ползунка.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPos`  
 Задает положение должно быть задано для ползунка. Позиция является относительно начала ползунка.  
  
 [in] `bRedraw`  
 Если `TRUE`, перерисовывается ползунок.  
  
##  <a name="setrange"></a>  CMFCRibbonSlider::SetRange  
 Задайте диапазон значений для элемента управления "ползунок".  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMin`  
 Указывает минимальное значение элемента управления "ползунок".  
  
 [in] `nMax`  
 Указывает максимальное значение элемента управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Указывает диапазон значений для элемента управления "ползунок", задав минимальное и максимальное значения.  
  
##  <a name="setzoombuttons"></a>  CMFCRibbonSlider::SetZoomButtons  
 Отображение или скрытие кнопки масштабирования.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in]. `bSet`  
 `TRUE` для отображения кнопок масштаба; `FALSE` Чтобы скрыть их.  
  
##  <a name="setzoomincrement"></a>  CMFCRibbonSlider::SetZoomIncrement  
 Установите шаг масштабирования для элемента управления "ползунок".  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nZoomIncrement`  
 Задает шаг масштабирования элемента управления "ползунок".  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)
