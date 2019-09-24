---
title: Класс CPoint
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: b7c13ef8b9656c5c2fa6a90fefca0d9babbe1c84
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491230"
---
# <a name="cpoint-class"></a>Класс CPoint

Как и в структуре `POINT` Windows.

## <a name="syntax"></a>Синтаксис

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPoint:: CPoint](#cpoint)|Создает документ `CPoint`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPoint:: offset](#offset)|Добавляет значения `x` в элементы и `y` объекта. `CPoint`|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CPoint:: operator —](#operator_-)|Возвращает разность `CPoint` между и размером, или отрицанием точки, либо разность размера между двумя точками или смещение на отрицательный размер.|
|[CPoint:: operator! =](#operator_neq)|Проверяет на неравенство между двумя точками.|
|[CPoint:: operator +](#operator_add)|Возвращает сумму `CPoint` , а также размер или точку `CRect` или смещение на размер.|
|[CPoint:: operator + =](#operator_add_eq)|`CPoint` Смещение путем добавления размера или точки.|
|[CPoint:: operator-=](#operator_-_eq)|`CPoint` Смещение путем вычитания размера или точки.|
|[CPoint:: operator = =](#operator_eq_eq)|Проверяет равенство между двумя точками.|

## <a name="remarks"></a>Примечания

Он также включает функции элементов для управления `CPoint` структурами и [точек](/windows/win32/api/windef/ns-windef-point) .

Объект можно использовать везде, `POINT` где используется структура. `CPoint` Операторы этого класса, взаимодействующие с "size", принимают либо объекты [ксизе](../../atl-mfc-shared/reference/csize-class.md) , либо структуры [размера](/windows/win32/api/windef/ns-windef-size) , так как эти два являются взаимозаменяемыми.

> [!NOTE]
>  Этот класс является производным от `tagPOINT` структуры. (Имя `tagPOINT` `POINT` для структуры является менее часто используемым именем.) Это означает, что `POINT` элементы данных `x` структуры и `y`являются доступными элементами `CPoint`данных.

> [!NOTE]
>  Дополнительные сведения о общих классах служебной программы `CPoint`(например,) см. в разделе [Общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Требования

**Заголовок:** атлтипес. h

##  <a name="cpoint"></a>CPoint:: CPoint

Создает объект `CPoint`.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Параметры

*иниткс*<br/>
Определяет значение члена `x` структуры `CPoint`.

*Инициализация*<br/>
Определяет значение члена `y` структуры `CPoint`.

*инитпт*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или `CPoint` , указывающая значения, используемые для `CPoint`инициализации.

*initSize*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или [ксизе](../../atl-mfc-shared/reference/csize-class.md) , указывающая значения, используемые для `CPoint`инициализации.

*двпоинт*<br/>
Задает элементу `y` неупорядоченное слово *двпоинт* , а элемент — в слове двпоинт с высоким приоритетом. `x`

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

##  <a name="offset"></a>CPoint:: offset

Добавляет значения `x` в элементы и `y` объекта. `CPoint`

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Параметры

*ксоффсет*<br/>
Задает величину смещения `x` элемента `CPoint`.

*йоффсет*<br/>
Задает величину смещения `y` элемента `CPoint`.

*point*<br/>
Задает величину ( [POINT](/windows/win32/api/windef/ns-windef-point) или `CPoint`)смещения для`CPoint`.

*size*<br/>
Задает величину ( [size](/windows/win32/api/windef/ns-windef-size) или [ксизе](../../atl-mfc-shared/reference/csize-class.md)) смещения `CPoint`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>CPoint:: operator = =

Проверяет равенство между двумя точками.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или `CPoint` объект.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если точки равны; в противном случае — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>CPoint:: operator! =

Проверяет на неравенство между двумя точками.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или `CPoint` объект.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если точки не равны; в противном случае — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>CPoint:: operator + =

Первая перегрузка добавляет размер в `CPoint`.

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит структуру [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) .

*point*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

### <a name="remarks"></a>Примечания

Вторая перегрузка добавляет точку в `CPoint`.

В обоих случаях сложение выполняется `x` путем добавления элемента (или `cx`) правого операнда `CPoint` к `x` элементу и добавления `y` элемента (или `cy`) правого операнда в элемент `y` член .`CPoint`

Например, добавление `CPoint(5, -7)` в переменную, которая содержит `CPoint(30, 40)` , изменяет переменную `CPoint(35, 33)`на.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>CPoint:: operator-=

Первая перегрузка вычитает размер из `CPoint`.

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит структуру [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) .

*point*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

### <a name="remarks"></a>Примечания

Вторая перегрузка вычитает точку из `CPoint`.

В обоих случаях вычитание выполняется путем вычитания `x` элемента (или `cx`) правого операнда `CPoint` из `x` элемента и вычитания `y` элемента (или `cy`) правой стороны операнд из `y` элемента `CPoint`.

Например, вычитание `CPoint(5, -7)` из переменной, которая содержит `CPoint(30, 40)` , изменяет переменную на `CPoint(25, 47)`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>CPoint:: operator +

Этот оператор используется для смещения `CPoint` `CPoint` `CSize` объектаили`CRect` , а также для смещения a на. `CPoint`

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит структуру [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) .

*point*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

*лпрект*<br/>
Содержит указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или объект [крект](../../atl-mfc-shared/reference/crect-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Объект `CPoint` , который смещается по размеру `CPoint` , смещению по точке или `CRect` смещению на точку.

### <a name="remarks"></a>Примечания

Например, использование одной из первых двух перегрузок `CPoint(25, -19)` для смещения точки на точку `CPoint(15, 5)` или размер `CSize(15, 5)` возвращает значение `CPoint(40, -14)`.

Добавление прямоугольника в точку возвращает прямоугольник после смещения `x` значениями и `y` , заданными в точке. Например, использование последней перегрузки для смещения прямоугольника `CRect(125, 219, 325, 419)` на точку `CPoint(25, -19)` возвращает `CRect(150, 200, 350, 400)`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>CPoint:: operator —

Используйте одну из первых двух перегрузок для вычитания `CPoint` объекта или `CSize` из. `CPoint`

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Структура [Point](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) .

*лпрект*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или объект [крект](../../atl-mfc-shared/reference/crect-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Объект `CSize` , который представляет собой разность между двумя точками `CPoint` , которая смещается от отрицания размера, `CRect` , который смещается на `CPoint` отрицание точки, или, который является отрицанием точки.

### <a name="remarks"></a>Примечания

Третья перегрузка смещает a на `CRect` противоположность. `CPoint` Наконец, используйте унарный оператор для отрицания `CPoint`.

Например, с помощью первой перегрузки можно найти разницу между двумя точками `CPoint(25, -19)` и `CPoint(15, 5)` возвратами `CSize(10, -24)`.

Вычитание `CPoint` `CPoint` из выполняет то же вычисление, что и выше, но возвращает объект, `CSize` а не объект. `CSize` Например, используйте вторую перегрузку для определения разницы между точкой `CPoint(25, -19)` и `CPoint(10, -24)`размером `CSize(15, 5)` .

Вычитание прямоугольника из точки возвращает смещение прямоугольника по отрицательным `x` значениям и `y` , указанным в точке. Например, использование последней перегрузки для смещения прямоугольника `CRect(125, 200, 325, 400)` на точка `CPoint(25, -19)` возвращает `CRect(100, 219, 300, 419)`.

Используйте унарный оператор для отрицания точки. Например, использование унарного оператора с точкой `CPoint(25, -19)` возвращает. `CPoint(-25, 19)`

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>См. также

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура точки](/windows/win32/api/windef/ns-windef-point)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Класс CSize](../../atl-mfc-shared/reference/csize-class.md)
