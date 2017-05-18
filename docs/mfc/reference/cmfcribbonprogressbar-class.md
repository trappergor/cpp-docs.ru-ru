---
title: "Класс CMFCRibbonProgressBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCRibbonProgressBar class
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 51efd8c4ac84dffe1384b7d664197b4bdebad110
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonprogressbar-class"></a>Класс CMFCRibbonProgressBar
Реализует элемент управления, который визуально показывает ход выполнения длительных операций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Создает и инициализирует объект `CMFCRibbonProgressBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|Возвращает текущий ход выполнения.|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Возвращает максимальное значение текущего диапазона.|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Возвращает минимальное значение текущего диапазона.|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|Указывает, работает ли индикатор хода выполнения в режиме бесконечного.|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Задает индикатор для работы в режиме бесконечной.|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|Задает текущий ход выполнения.|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|Задает минимальное и максимальное значения.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CMFCRibbonProgressBar` может работать в двух режимах: обычных и бесконечной. В обычном режиме индикатор хода выполнения заполняется слева направо и останавливается при достижении максимального значения. В режиме бесконечного индикатор многократно заполняется из минимальное значение максимальное значение. Бесконечный режим можно использовать для указания, что операция является постоянной, но неизвестно, время завершения.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCRibbonProgressBar` класса. В примере значение индикатора хода выполнения работы в бесконечный режиме (где время завершения операции неизвестно), как задать минимальное и максимальное значения для индикатора и задать текущее положение индикатора хода выполнения. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&11;](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 Создает и инициализирует [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) объекта.  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Указывает идентификатор команды для индикатора ленты.  
  
 [in] `nWidth`  
 Ширина в пикселях индикатор ленты.  
  
 [in] `nHeight`  
 Высота в пикселях индикатор ленты.  
  
##  <a name="getpos"></a>CMFCRibbonProgressBar::GetPos  
 Возвращает текущую позицию индикатора хода выполнения.  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее текущее положение индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Диапазон должен быть в диапазоне, определяемом [CMFCRibbonProgressBar::SetRange](#setrange) метод.  
  
##  <a name="getrangemax"></a>CMFCRibbonProgressBar::GetRangeMax  
 Возвращает текущий индикатор максимальное значение.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное значение текущего диапазона.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrangemin"></a>CMFCRibbonProgressBar::GetRangeMin  
 Возвращает текущий индикатор минимальное значение диапазона.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное значение текущего диапазона.  
  
##  <a name="getregularsize"></a>CMFCRibbonProgressBar::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isinfinitemode"></a>CMFCRibbonProgressBar::IsInfiniteMode  
 Указывает, работает ли индикатор хода выполнения в режиме бесконечного.  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если индикатор выполнения не в режиме бесконечного; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В режиме бесконечного индикатор заполняет несколько раз с минимального значения максимальное значение. Бесконечный режим можно использовать для указания, что операция является постоянной, но неизвестно, время завершения.  
  
##  <a name="ondraw"></a>CMFCRibbonProgressBar::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setinfinitemode"></a>CMFCRibbonProgressBar::SetInfiniteMode  
 Задает индикатор для работы в режиме бесконечной.  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 `TRUE`Чтобы указать индикатора хода выполнения в режиме бесконечного; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Обычно в случае индикатор хода выполнения в режиме бесконечного его означает, что операция является постоянной, но неизвестно, время завершения. Таким образом индикатор заполняет несколько раз с минимального значения до максимального значения.  
  
##  <a name="setpos"></a>CMFCRibbonProgressBar::SetPos  
 Задает текущую позицию индикатора хода выполнения.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPos`  
 Задает положение, задаваемое для индикатора хода выполнения.  
  
 [in] `bRedraw`  
 Указывает, должны быть перерисованы индикатора хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Диапазон должен быть в диапазоне, определяемом [CMFCRibbonProgressBar::SetRange](#setrange) метод.  
  
##  <a name="setrange"></a>CMFCRibbonProgressBar::SetRange  
 Задает минимальное и максимальное значения для индикатора.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMin`  
 Задает минимальное значение диапазона.  
  
 [in] `nMax`  
 Задает максимальное значение диапазона.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы определить диапазон индикатора хода выполнения, задав минимальное и максимальное значения.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

