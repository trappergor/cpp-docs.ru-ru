---
title: "Класс CSize | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
dev_langs:
- C++
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
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
ms.openlocfilehash: 96905d916dfde8f8a7bf8131a280ae7ccfe511d8
ms.lasthandoff: 02/24/2017

---
# <a name="csize-class"></a>Класс CSize
Аналог структуры [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) в ОС Windows, реализующий относительные координаты или положение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSize::CSize](#csize)|Создает объект `CSize`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|Вычитает два размера.|  
|[CSize::operator! =](#operator_neq)|Проверяет неравенство `CSize` и размер.|  
|[CSize::operator +](#operator_add)|Добавление двух размеров.|  
|[CSize::operator +=](#operator_add_eq)|Добавляет размер `CSize`.|  
|[CSize::operator-=](#operator_-_eq)|Вычитает размер из `CSize`.|  
|[CSize::operator ==](#operator_eq_eq)|Проверяет на равенство между `CSize` и размер.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является производным от **размер** структуры. Это означает, что можно передать `CSize` в параметр, который требует **размер** и что данные-члены **размер** структуры являются членами данных `CSize`.  
  
 **Cx** и **cy** члены **размер** (и `CSize`), являются общедоступными. Кроме того `CSize` реализует функции-члены для управления **размер** структуры.  
  
> [!NOTE]
>  Дополнительные сведения о общие служебные классы (как `CSize`), в разделе [совместно используемые классы](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltypes.h  
  
##  <a name="csize"></a>CSize::CSize  
 Создает объект `CSize`.  
  
```  
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 *initCX*  
 Наборы **cx** элемент для `CSize`.  
  
 *initCY*  
 Наборы **cy** элемент для `CSize`.  
  
 `initSize`  
 [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или `CSize` объект, используемый для инициализации `CSize`.  
  
 `initPt`  
 [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или `CPoint` объект, используемый для инициализации `CSize`.  
  
 `dwSize`  
 `DWORD`используется для инициализации `CSize`. Младшее слово **cx** член и старшее слово является **cy** член.  
  
### <a name="remarks"></a>Примечания  
 Если аргументы не указаны, **cx** и **cy** инициализируются нулевым значением.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#97;](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CSize::operator ==  
 Проверяет равенство двух размеров.  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает ненулевое значение, если размеры равны, otherwize 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#98;](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CSize::operator! =  
 Проверяет неравенство двух размеров.  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает ненулевое значение, если размеры не равны; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#99;](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CSize::operator +=  
 Это добавляет размером `CSize`.  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#100;](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>CSize::operator-=  
 Вычитает из этого размера `CSize`.  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#101;](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="operator_add"></a>CSize::operator +  
 Добавьте эти операторы `CSize` в значение параметра.  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>Примечания  
 Следующие описания отдельных операторов см.:  
  
- **оператор + (** `size` **)**эта операция добавляет два `CSize` значения.  
  
- **оператор + (** `point` **)**этой операции смещений (перемещается) [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) (или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) значение в этом `CSize` значение. **Cx** и **cy** членов этой `CSize` значения добавляются в **x** и **y** данные-члены **ТОЧКИ** значение. Он аналогичен версии [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , которая принимает [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) параметр.  
  
- **оператор + (** `lpRect` **)**этой операции смещений (перемещается) [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (или [CRect](../../atl-mfc-shared/reference/crect-class.md)) значение в этом `CSize` значение. **Cx** и **cy** членов этой `CSize` значения добавляются в **левой**, **начало**, **правом**, и **нижней** данные-члены `RECT` значение. Он аналогичен версии [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , которая принимает [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) параметр.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#102;](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="operator_-"></a>CSize::operator-  
 Первые три из этих операторов вычесть это `CSize` в значение параметра.  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>Примечания  
 Четвертый оператор унарного минуса, изменяет знак `CSize` значение. Следующие описания отдельных операторов см.:  
  
- **оператор-(** `size` **)**этой операции вычитает два `CSize` значения.  
  
- **оператор-(** `point` **)**этой операции смещений (перемещается) [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) значение аддитивную инверсию `CSize` значение. **Cx** и **cy** этого `CSize` значение вычитается из **x** и **y** данные-члены **ТОЧКИ** значение. Он аналогичен версии [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , которая принимает [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) параметр.  
  
- **оператор-(** `lpRect` **)**этой операции смещений (перемещается) [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) или [CRect](../../atl-mfc-shared/reference/crect-class.md) значение аддитивную инверсию `CSize` значение. **Cx** и **cy** членов этой `CSize` значение вычитается из **левой**, **начало**, **правом**, и **нижней** данные-члены `RECT` значение. Он аналогичен версии [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) , которая принимает [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) параметр.  
  
- **оператор-()**эта операция Возвращает аддитивную инверсию `CSize` значение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#103;](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRect](../../atl-mfc-shared/reference/crect-class.md)   
 [Класс CPoint](../../atl-mfc-shared/reference/cpoint-class.md)


