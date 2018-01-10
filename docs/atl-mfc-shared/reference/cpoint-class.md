---
title: "Класс CPoint | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs: C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7140e2db55db8a28c1af63f89517708f4dc0d835
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cpoint-class"></a>Класс CPoint
Как и в структуре `POINT` Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPoint : public tagPOINT 
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPoint::CPoint](#cpoint)|Создает документ `CPoint`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPoint::Offset](#offset)|Значения добавляются к **x** и **y** члены `CPoint`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPoint::operator-](#operator_-)|Возвращает разность `CPoint` и размер, или отрицательными значениями точку или разница размера между двумя точками или смещение с отрицательным размером.|  
|[CPoint::operator! =](#operator_neq)|Проверяет неравенство двух точек.|  
|[CPoint::operator +](#operator_add)|Возвращает сумму `CPoint` и размер или точку, или `CRect` смещение по размеру.|  
|[CPoint::operator +=](#operator_add_eq)|Смещает `CPoint` путем добавления размера или точки.|  
|[CPoint::operator-=](#operator_-_eq)|Смещает `CPoint` путем вычитания размер или точки.|  
|[CPoint::operator ==](#operator_eq_eq)|Проверяет равенство между двумя точками.|  
  
## <a name="remarks"></a>Примечания  
 Он также включает функции-члены для управления `CPoint` и [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры.  
  
 Объект `CPoint` объект можно использовать везде, где `POINT` использовать структуру. Операторы этого класса, которые взаимодействуют с «размер» примите либо [CSize](../../atl-mfc-shared/reference/csize-class.md) объектов или [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры, так как они взаимозаменяемы.  
  
> [!NOTE]
>  Этот класс является производным от `tagPOINT` структуры. (Имя `tagPOINT` является наименее часто используемым именем `POINT` структуры.) Это означает, что данные-члены `POINT` структуры `x` и `y`, являются членами данных `CPoint`.  
  
> [!NOTE]
>  Дополнительные сведения об общих служебных классов (как `CPoint`), в разделе [совместно используемые классы](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagPOINT`  
  
 `CPoint`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltypes.h  
  
##  <a name="cpoint"></a>CPoint::CPoint
 Создает объект `CPoint`.  
  
```  
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `initX`  
 Определяет значение члена `x` структуры `CPoint`.  
  
 `initY`  
 Определяет значение члена `y` структуры `CPoint`.  
  
 `initPt`  
 [ТОЧКА](../../mfc/reference/point-structure1.md) структуры или `CPoint` , задающий значения, используемые для инициализации `CPoint`.  
  
 `initSize`  
 [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) , задающий значения, используемые для инициализации `CPoint`.  
  
 `dwPoint`  
 Задает член `x` для младшего слова `dwPoint` и член `y` для старшего слова `dwPoint`.  
  
### <a name="remarks"></a>Примечания  
 Если аргументы не указаны, для членов `x` и `y` задается значение 0.  
  
### <a name="example"></a>Пример  
  
```cpp   
CPoint   ptTopLeft(0, 0); 
// works from a POINT, too  
 
POINT   ptHere;  
ptHere.x = 35;  
ptHere.y = 95;  
 
CPoint   ptMFCHere(ptHere);
 
// works from a SIZE 
SIZE   sHowBig;  
sHowBig.cx = 300;  
sHowBig.cy = 10;  
 
CPoint ptMFCBig(sHowBig); 
// or from a DWORD  
 
DWORD   dwSize;  
dwSize = MAKELONG(35, 95);
 
CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```  
  
##  <a name="offset"></a>CPoint::Offset  
 Значения добавляются к **x** и **y** члены `CPoint`.  
  
```  
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *Смещение*  
 Указывает число для смещения **x** членом `CPoint`.  
  
 *Смещение*  
 Указывает число для смещения **y** членом `CPoint`.  
  
 `point`  
 Указывает объем ( [ТОЧКИ](../../mfc/reference/point-structure1.md) или `CPoint`) по смещению `CPoint`.  
  
 `size`  
 Указывает объем ( [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) или [CSize](../../atl-mfc-shared/reference/csize-class.md)) по смещению `CPoint`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CPoint::operator ==  
 Проверяет равенство между двумя точками.  
  
```  
BOOL operator==(POINT point) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или `CPoint` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если точки совпадают; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CPoint::operator! =  
 Проверяет неравенство двух точек.  
  
```  
BOOL operator!=(POINT point) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или `CPoint` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если точки не равны. в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CPoint::operator +=  
 Первая перегрузка добавляет размер для `CPoint`.  
  
```  
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Содержит [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.  
  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Вторая перегрузка добавляет точку `CPoint`.  
  
 В обоих случаях добавление выполняется путем добавления **x** (или **cx**) члена для правого операнда **x** членом `CPoint` и добавление **y**  (или **cy**) члена для правого операнда **y** членом `CPoint`.  
  
 Например, при добавлении `CPoint(5, -7)` на переменную, которая содержит `CPoint(30, 40)` изменяет переменную `CPoint(35, 33)`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>CPoint::operator-=  
 Первая перегрузка вычитает размер из `CPoint`.  
  
```  
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Содержит [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.  
  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Вторая перегрузка вычитает точку с `CPoint`.  
  
 В обоих случаях вычитания выполняется путем вычитания **x** (или **cx**) член правого операнда из **x** членом `CPoint` и вычитания **y** (или **cy**) член правого операнда из **y** членом `CPoint`.  
  
 Например, при вычитании `CPoint(5, -7)` из переменной, которая содержит `CPoint(30, 40)` изменяет переменную `CPoint(25, 47)`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]  
  
##  <a name="operator_add"></a>CPoint::operator +  
 Этот оператор используется для смещения `CPoint` по `CPoint` или `CSize` объекта, или по смещению `CRect` по `CPoint`.  
  
```  
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Содержит [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.  
  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.  
  
 `lpRect`  
 Содержит указатель на [RECT](../../mfc/reference/rect-structure1.md) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CPoint` , смещение по размеру, **CPoint** , смещением точку, или **CRect** смещением на точку.  
  
### <a name="remarks"></a>Примечания  
 Например, одним из первых двух перегрузок смещения `CPoint(25, -19)` точкой `CPoint(15, 5)` или размер `CSize(15, 5)` возвращает значение `CPoint(40, -14)`.  
  
 Добавление прямоугольника на момент возвращает прямоугольника после выполняется компенсируется **x** и **y** значениями, указанными в точке. Например, с помощью последнего перегрузки смещения прямоугольника `CRect(125, 219, 325, 419)` точкой `CPoint(25, -19)` возвращает `CRect(150, 200, 350, 400)`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]  
  
##  <a name="operator_-"></a>CPoint::operator-  
 Используйте один из первых двух перегрузок Вычитаемый `CPoint` или `CSize` объекта из `CPoint`.  
  
```  
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Объект [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.  
  
 `size`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.  
  
 `lpRect`  
 Указатель на [RECT](../../mfc/reference/rect-structure1.md) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` , представляющий собой разницу между двумя точками `CPoint` , смещением отрицания размера `CRect` , смещением отрицания точки, или `CPoint` именно отрицания точки.  
  
### <a name="remarks"></a>Примечания  
 Третий перегрузки смещения `CRect` с отрицательными значениями `CPoint`. Наконец, используйте унарный оператор для отрицания `CPoint`.  
  
 Например, с помощью первая перегрузка, чтобы определить разницу между двумя точками `CPoint(25, -19)` и `CPoint(15, 5)` возвращает `CSize(10, -24)`.  
  
 Вычитание `CSize` из `CPoint` содержит такой же расчет, как описано выше, но возвращает `CPoint` объекта, не `CSize` объекта. Например, с помощью вторую перегрузку, чтобы определить разницу между точкой `CPoint(25, -19)` и размер `CSize(15, 5)` возвращает `CPoint(10, -24)`.  
  
 Вычитания прямоугольник из точки Возвращает смещение прямоугольник с отрицательных из **x** и **y** значениями, указанными в точке. Например, с помощью последнего перегрузки смещения прямоугольника `CRect(125, 200, 325, 400)` точкой `CPoint(25, -19)` возвращает `CRect(100, 219, 300, 419)`.  
  
 Используйте унарный оператор для отрицания точку. Например, использование унарного оператора с точкой `CPoint(25, -19)` возвращает `CPoint(-25, 19)`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Структура POINT](../../mfc/reference/point-structure1.md)   
 [CRect-класс](../../atl-mfc-shared/reference/crect-class.md)   
 [Класс CSize](../../atl-mfc-shared/reference/csize-class.md)



