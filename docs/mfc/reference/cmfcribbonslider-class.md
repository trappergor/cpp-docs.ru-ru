---
title: Класс CMFCRibbonSlider | Документация Майкрософт
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
ms.openlocfilehash: 165dbf85e22a6f30089bbf1523068057b972b7e8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709336"
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
|[CMFCRibbonSlider::GetPos](#getpos)|Возвращает текущее положение элемента управления "ползунок".|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Возвращает максимальное значение ползунка.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Возвращает минимальное значение ползунка.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Возвращает размер шаг изменения масштаба для элемента управления "ползунок".|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Указывает, имеет ли ползунок кнопки масштаба.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|Задает текущую позицию элемента управления "ползунок".|  
|[CMFCRibbonSlider::SetRange](#setrange)|Указывает диапазон элемента управления "ползунок", задав минимальное и максимальное значения.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Показывает или скрывает кнопки масштабирования.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Задает размер шаг изменения масштаба для элемента управления "ползунок".|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `SetRange` метод для настройки диапазона увеличивает масштаб для ползунка. Можно задать текущее положение ползунка с помощью `SetPos` метод.  
  
 Можно отобразить кнопки масштаба циклическая слева и справа от элемента управления slider с помощью `SetZoomButtons` метод. По умолчанию ползунок горизонтальной, кнопка слева масштаб отображает знак «минус» и кнопка справа масштаб отображает значок «плюс».  
  
 `SetZoomIncrement` Метод определяет шаг для добавления или вычитания из текущей позиции, при нажатии кнопки масштабирования.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCRibbonSlider` класса для задания свойств ползунка. В примере показано `CMFCRibbonSlider` , отображения кнопки масштаба, установить текущее положение элемента управления "ползунок" и установить диапазон значений для элемента управления "ползунок".  
  
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
*nID*<br/>
[in] Идентификатор "ползунок".  
  
 [in]. *nWidth*  
 Ползунок ширина в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Создает ленты "ползунок", который является *nWidth* пикселей в ширину в категории панели, где будет добавлен ползунок. По умолчанию ползунок горизонтальной.  
  
##  <a name="getpos"></a>  CMFCRibbonSlider::GetPos  
 Возвращает текущее положение элемента управления "ползунок".  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее положение элемента управления "ползунок", который является позицией относительно начала ползунка.  
  
##  <a name="getrangemax"></a>  CMFCRibbonSlider::GetRangeMax  
 Получает максимальное шаг ползунок, который может проходить ползунок в элементе управления "ползунок".  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное увеличение ползунка, может проходить ползунок в элементе управления "ползунок".  
  
##  <a name="getrangemin"></a>  CMFCRibbonSlider::GetRangeMin  
 Возвращает минимальное число, ползунок могут перемещаться в элементе управления "ползунок".  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное число, ползунок могут перемещаться в элементе управления "ползунок".  
  
##  <a name="getregularsize"></a>  CMFCRibbonSlider::GetRegularSize  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getzoomincrement"></a>  CMFCRibbonSlider::GetZoomIncrement  
 Получите шаг изменения масштаба для элемента управления "ползунок".  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Шаг изменения масштаба для элемента управления "ползунок".  
  
##  <a name="haszoombuttons"></a>  CMFCRibbonSlider::HasZoomButtons  
 Указывает, имеет ли ползунок кнопки масштаба.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ползунок имеет кнопки масштаба; Значение FALSE в противном случае.  
  
##  <a name="ondraw"></a>  CMFCRibbonSlider::OnDraw  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpos"></a>  CMFCRibbonSlider::SetPos  
 Установите текущее положение элемента управления "ползунок".  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*nPos*<br/>
[in] Задает положение, чтобы задать для ползунка. Позиция задается относительно начала ползунка.  
  
*bRedraw*<br/>
[in] Значение TRUE, если ползунок перерисовку.  
  
##  <a name="setrange"></a>  CMFCRibbonSlider::SetRange  
 Задайте диапазон значений для элемента управления "ползунок".  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
*Nмин.*<br/>
[in] Указывает минимальное значение элемента управления "ползунок".  
  
*Nмакс.*<br/>
[in] Указывает максимальное значение элемента управления "ползунок".  
  
### <a name="remarks"></a>Примечания  
 Указывает диапазон значений для элемента управления "ползунок", задав минимальное и максимальное значения.  
  
##  <a name="setzoombuttons"></a>  CMFCRibbonSlider::SetZoomButtons  
 Отображение или скрытие кнопки масштаба.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in]. *bSet*  
 Значение TRUE для отображения кнопки масштаба; Значение FALSE, чтобы скрыть их.  
  
##  <a name="setzoomincrement"></a>  CMFCRibbonSlider::SetZoomIncrement  
 Установите шаг изменения масштаба для элемента управления "ползунок".  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>Параметры  
*nZoomIncrement*<br/>
[in] Задает шаг изменения масштаба элемента управления "ползунок".  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)
