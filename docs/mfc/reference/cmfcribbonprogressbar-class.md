---
title: Класс CMFCRibbonProgressBar | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24981d2544c2b3e2c8be6a3307829f8a1e1c29ad
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040224"
---
# <a name="cmfcribbonprogressbar-class"></a>Класс CMFCRibbonProgressBar
Реализует элемент управления, который визуально показывает ход выполнения длительных операций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Создает и инициализирует объект `CMFCRibbonProgressBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|Возвращает текущее состояние.|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Возвращает максимальное значение текущего диапазона.|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Возвращает минимальное значение текущего диапазона.|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|Указывает, работает ли индикатор выполнения в режиме бесконечного.|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Задает для работы в режиме бесконечного индикатор выполнения.|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|Задает текущий ход выполнения.|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|Задает минимальное и максимальное значения.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CMFCRibbonProgressBar` может работать в двух режимах: обычные и бесконечной. В обычном режиме индикатор заполняется слева направо и останавливается при достижении максимального значения. В режиме бесконечного индикатор многократно заполняется с минимального значения до максимального значения. Можно использовать неограниченное режим для указания, что операция является текущей, но неизвестно, время выполнения.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCRibbonProgressBar` класса. В примере как задать индикатор для работы в бесконечный режиме (где неизвестно время завершения операции), установите минимальное и максимальное значения для индикатора и установить текущее положение индикатора выполнения. Этот фрагмент кода является частью [MS Office 2007 демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>  CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 Создает и инициализирует [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) объекта.  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nID*  
 Указывает идентификатор команды для индикатора ленты.  
  
 [in] *nWidth*  
 Ширина в пикселях индикатора ленты.  
  
 [in] *nHeight*  
 Высота в пикселях индикатора ленты.  
  
##  <a name="getpos"></a>  CMFCRibbonProgressBar::GetPos  
 Возвращает текущую позицию индикатора хода выполнения.  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее текущее положение индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Задаваемая диапазон должен быть в диапазоне, определяемом [CMFCRibbonProgressBar::SetRange](#setrange) метод.  
  
##  <a name="getrangemax"></a>  CMFCRibbonProgressBar::GetRangeMax  
 Возвращает индикатор текущее максимальное значение.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное значение текущего диапазона.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrangemin"></a>  CMFCRibbonProgressBar::GetRangeMin  
 Возвращает текущий индикатор минимальное значение диапазона.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное значение текущего диапазона.  
  
##  <a name="getregularsize"></a>  CMFCRibbonProgressBar::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isinfinitemode"></a>  CMFCRibbonProgressBar::IsInfiniteMode  
 Указывает, работает ли индикатор выполнения в режиме бесконечного.  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если индикатор выполнения в режиме бесконечного. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В режиме бесконечного индикатор заполняет несколько раз с минимального значения до максимального значения. Можно использовать неограниченное режим для указания, что операция является текущей, но неизвестно, время выполнения.  
  
##  <a name="ondraw"></a>  CMFCRibbonProgressBar::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setinfinitemode"></a>  CMFCRibbonProgressBar::SetInfiniteMode  
 Задает для работы в режиме бесконечного индикатор выполнения.  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bSet*  
 `TRUE` Чтобы указать, что индикатор выполнения в режиме бесконечного. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Обычно если индикатор выполнения в режиме бесконечного, он означает, что операция является текущей, но неизвестно, время выполнения. Таким образом индикатор выполнения заполняет несколько раз с минимального значения до максимального значения.  
  
##  <a name="setpos"></a>  CMFCRibbonProgressBar::SetPos  
 Задает текущую позицию индикатора хода выполнения.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nPos*  
 Задает позицию, к которой имеет значение индикатора хода выполнения.  
  
 [in] *bRedraw*  
 Указывает, должны быть перерисованы индикатор выполнения.  
  
### <a name="remarks"></a>Примечания  
 Задаваемая диапазон должен быть в диапазоне, определяемом [CMFCRibbonProgressBar::SetRange](#setrange) метод.  
  
##  <a name="setrange"></a>  CMFCRibbonProgressBar::SetRange  
 Задает минимальное и максимальное значения для индикатора.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nMin*  
 Задает минимальное значение диапазона.  
  
 [in] *nMax*  
 Указывает максимальное значение диапазона.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы определить диапазон индикатора хода выполнения с помощью задания минимального и максимального значения.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
