---
title: Класс CPoint | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2656871f62bf7881eee9c64041f3f1f492a3c948
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064892"
---
# <a name="cpoint-class"></a>Класс CPoint

Как и в структуре `POINT` Windows.

## <a name="syntax"></a>Синтаксис

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPoint::CPoint](#cpoint)|Создает документ `CPoint`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPoint::Offset](#offset)|Добавляет значения в таблицу `x` и `y` членами `CPoint`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CPoint::operator-](#operator_-)|Возвращает разность `CPoint` и размером или отрицание точку или разница размера между двумя точками или смещение с отрицательным размером.|
|[CPoint::operator! =](#operator_neq)|Проверяет неравенство между двумя точками.|
|[CPoint::operator +](#operator_add)|Возвращает сумму `CPoint` и размер или точки, или `CRect` смещается на размер.|
|[CPoint::operator +=](#operator_add_eq)|Смещает `CPoint` путем добавления размера или точки.|
|[CPoint::operator-=](#operator_-_eq)|Смещает `CPoint` путем вычитания размер или точки.|
|[CPoint::operator ==](#operator_eq_eq)|Проверяет равенство между двумя точками.|

## <a name="remarks"></a>Примечания

Он также включает функции-члены для управления `CPoint` и [ТОЧКИ](../../mfc/reference/point-structure.md) структуры.

Объект `CPoint` объект можно использовать везде, где `POINT` используется структура. Операторы этого класса, которые взаимодействуют с «размер» допускает оба [CSize](../../atl-mfc-shared/reference/csize-class.md) объектов или [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры, так как они взаимозаменяемы.

> [!NOTE]
>  Этот класс является производным от `tagPOINT` структуры. (Имя `tagPOINT` представляет собой наименее часто используемым `POINT` структуры.) Это означает, что данные-члены `POINT` структуры, `x` и `y`, являются членами доступные данные `CPoint`.

> [!NOTE]
>  Дополнительные сведения о общие служебные классы (как `CPoint`), см. в разделе [общих классов](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Требования

**Заголовок:** atltypes.h

##  <a name="cpoint"></a>  CPoint::CPoint

Создает объект `CPoint`.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Параметры

*initX*<br/>
Определяет значение члена `x` структуры `CPoint`.

*initY*<br/>
Определяет значение члена `y` структуры `CPoint`.

*initPt*<br/>
[ТОЧКА](../../mfc/reference/point-structure.md) структуры или `CPoint` , определяет значения, используемые для инициализации `CPoint`.

*initSize*<br/>
[РАЗМЕР](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) , определяет значения, используемые для инициализации `CPoint`.

*dwPoint*<br/>
Наборы `x` члена младшее слово из *dwPoint* и `y` член для старшего слова из *dwPoint*.

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

##  <a name="offset"></a>  CPoint::Offset

Добавляет значения в таблицу `x` и `y` членами `CPoint`.

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Параметры

*Смещение*<br/>
Указывает величина смещения `x` членом `CPoint`.

*Смещение*<br/>
Указывает величина смещения `y` членом `CPoint`.

*точка*<br/>
Указывает объем ( [ТОЧКИ](../../mfc/reference/point-structure.md) или `CPoint`) смещения `CPoint`.

*size*<br/>
Указывает объем ( [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) или [CSize](../../atl-mfc-shared/reference/csize-class.md)) смещения `CPoint`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CPoint::operator ==

Проверяет равенство между двумя точками.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*точка*<br/>
Содержит [ТОЧКИ](../../mfc/reference/point-structure.md) структуры или `CPoint` объекта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если точки совпадают; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>  CPoint::operator! =

Проверяет неравенство между двумя точками.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*точка*<br/>
Содержит [ТОЧКИ](../../mfc/reference/point-structure.md) структуры или `CPoint` объекта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если точки не равны; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CPoint::operator +=

Первая перегрузка добавляет размер `CPoint`.

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.

*точка*<br/>
Содержит [ТОЧКИ](../../mfc/reference/point-structure.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.

### <a name="remarks"></a>Примечания

Вторая перегрузка добавляет точку `CPoint`.

В обоих случаях сложения выполняется путем добавления `x` (или `cx`) членом правый операнд для `x` членом `CPoint` и добавление `y` (или `cy`) членом правый операнд `y` членом `CPoint`.

Например, добавление `CPoint(5, -7)` на переменную, которая содержит `CPoint(30, 40)` изменяет переменную `CPoint(35, 33)`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CPoint::operator-=

Первая перегрузка вычитает размер из `CPoint`.

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.

*точка*<br/>
Содержит [ТОЧКИ](../../mfc/reference/point-structure.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.

### <a name="remarks"></a>Примечания

Вторая перегрузка вычитает точку с помощью `CPoint`.

В обоих случаях вычитания выполняется путем вычитания `x` (или `cx`) член правого операнда из `x` членом `CPoint` и вычитания `y` (или `cy`) членом справа операнд из `y` членом `CPoint`.

Например, при вычитании `CPoint(5, -7)` из переменной, которая содержит `CPoint(30, 40)` изменяет переменную `CPoint(25, 47)`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>  CPoint::operator +

Этот оператор используется для смещения `CPoint` по `CPoint` или `CSize` объекта, или смещения `CRect` по `CPoint`.

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*size*<br/>
Содержит [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.

*точка*<br/>
Содержит [ТОЧКИ](../../mfc/reference/point-structure.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.

*lpRect*<br/>
Содержит указатель на [RECT](../../mfc/reference/rect-structure.md) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Объект `CPoint` , являющийся смещением по размеру, `CPoint` , являющийся смещением точкой, или `CRect` смещается на точку.

### <a name="remarks"></a>Примечания

Например, с помощью одного из первых двух перегрузок смещения `CPoint(25, -19)` точкой `CPoint(15, 5)` или размер `CSize(15, 5)` возвращает значение `CPoint(40, -14)`.

Добавление прямоугольника на момент Возвращает прямоугольник после компенсируется `x` и `y` значениями, указанными в точку. Например, используя последнюю перегрузку смещения прямоугольника `CRect(125, 219, 325, 419)` точкой `CPoint(25, -19)` возвращает `CRect(150, 200, 350, 400)`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>  CPoint::operator-

Используйте один из первых двух перегрузок для вычитания `CPoint` или `CSize` объекта из `CPoint`.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Параметры

*точка*<br/>
Объект [ТОЧКИ](../../mfc/reference/point-structure.md) структуры или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объекта.

*size*<br/>
Объект [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.

*lpRect*<br/>
Указатель на [RECT](../../mfc/reference/rect-structure.md) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Объект `CSize` является различие между двумя точками `CPoint` , являющийся смещением путем размера `CRect` , являющийся смещением по отрицание является точкой, или `CPoint` то есть отрицание точки.

### <a name="remarks"></a>Примечания

Третья перегрузка смещения `CRect` с отрицанием `CPoint`. Наконец, использовать унарный оператор для отрицания `CPoint`.

Например, с помощью первая перегрузка найти разницу между двумя точками `CPoint(25, -19)` и `CPoint(15, 5)` возвращает `CSize(10, -24)`.

Вычитание `CSize` из `CPoint` выполняет те же самые вычисления, как описано выше, но возвращает `CPoint` объекта, не `CSize` объекта. Например, с помощью вторая перегрузка для нахождение разности между точкой `CPoint(25, -19)` и размер `CSize(15, 5)` возвращает `CPoint(10, -24)`.

Вычитания прямоугольник из точки Возвращает смещение прямоугольника, отрицательные результаты из `x` и `y` значениями, указанными в точку. Например, используя последнюю перегрузку смещения прямоугольника `CRect(125, 200, 325, 400)` точкой `CPoint(25, -19)` возвращает `CRect(100, 219, 300, 419)`.

Используйте унарный оператор для отрицания точку. Например, с помощью унарный оператор с точкой `CPoint(25, -19)` возвращает `CPoint(-25, 19)`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура POINT](../../mfc/reference/point-structure.md)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Класс CSize](../../atl-mfc-shared/reference/csize-class.md)

