---
title: Класс Ксизе
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: 26bb43355f4dff3f77a905068bea83dd1ceaf79c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491657"
---
# <a name="csize-class"></a>Класс Ксизе

Аналог структуры [SIZE](/windows/win32/api/windef/ns-windef-size) в ОС Windows, реализующий относительные координаты или положение.

## <a name="syntax"></a>Синтаксис

```
class CSize : public tagSIZE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ксизе:: Ксизе](#csize)|Создает объект `CSize`.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ксизе:: operator —](#operator_-)|Вычитает два размера.|
|[Ксизе:: operator! =](#operator_neq)|Проверяет на неравенство между `CSize` и размером.|
|[Ксизе:: operator +](#operator_add)|Складывает два размера.|
|[Ксизе:: operator + =](#operator_add_eq)|Добавляет размер в `CSize`.|
|[Ксизе:: operator-=](#operator_-_eq)|Вычитает размер из `CSize`.|
|[Ксизе:: operator = =](#operator_eq_eq)|Проверяет равенство между `CSize` и размером.|

## <a name="remarks"></a>Примечания

Этот класс является производным от `SIZE` структуры. Это означает, что можно передать `CSize` в параметр, который вызывает метод `SIZE` для и что элементы `SIZE` данных структуры являются доступными элементами `CSize`данных.

Члены `cx` и`cy` ( и`CSize`) являются открытыми. `SIZE` Кроме того `CSize` `SIZE` , реализует функции элементов для управления структурой.

> [!NOTE]
> Дополнительные сведения о общих классах служебной программы `CSize`(например,) см. в разделе [Общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagSIZE`

`CSize`

## <a name="requirements"></a>Требования

**Заголовок:** атлтипес. h

##  <a name="csize"></a>Ксизе:: Ксизе

Создает объект `CSize`.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Параметры

*инитккс*<br/>
`cx` Задает элемент`CSize`для.

*инитци*<br/>
`cy` Задает элемент`CSize`для.

*initSize*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или `CSize` объект, используемый для `CSize`инициализации.

*инитпт*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или `CPoint` объект, используемый для `CSize`инициализации.

*двсизе*<br/>
DWORD, используемый для `CSize`инициализации. Слово с низким приоритетом является `cx` элементом, а старшим словом `cy` является элемент.

### <a name="remarks"></a>Примечания

Значение, `cx` если аргументы не заданы `cy` и инициализируются нулем.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

##  <a name="operator_eq_eq"></a>Ксизе:: operator = =

Проверяет равенство двух размеров.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает ненулевое значение, если размеры равны, осервизе 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

##  <a name="operator_neq"></a>Ксизе:: operator! =

Проверяет на неравенство между двумя размерами.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает ненулевое значение, если размеры не равны; в противном случае — значение 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

##  <a name="operator_add_eq"></a>Ксизе:: operator + =

Добавляет размер к этому `CSize`.

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

##  <a name="operator_-_eq"></a>Ксизе:: operator-=

Вычитает размер из этого `CSize`.

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

##  <a name="operator_add"></a>Ксизе:: operator +

Эти операторы добавляют `CSize` это значение к значению параметра.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Примечания

См. следующие описания отдельных операторов.

- **оператор + (** *size* **)**

  Эта операция добавляет два `CSize` значения.

- **оператор + (** *Point* **)**

  Эта операция смещает (перемещает) значение [точки](/previous-versions/dd162805\(v=vs.85\)) (или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) на это `CSize` значение. `x` `y` Члены `cx` и `cy` этого значения`CSize` добавляютсякэлементам`POINT` данных и значения. Он аналогичен версии [CPoint:: operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , принимающей параметр [size](/windows/win32/api/windef/ns-windef-size) .

- **operator + (** *лпрект* **)**

   Эта операция смещает (перемещает) значение [Rect](/previous-versions/dd162897\(v=vs.85\)) (или [крект](../../atl-mfc-shared/reference/crect-class.md)) на это `CSize` значение. `left` `top`Элементы `cx` и `cy` этого значения`CSize` добавляются в элементы данных,`right`, и`bottom` значения .`RECT` Он аналогичен версии [крект:: operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , принимающей параметр [size](/windows/win32/api/windef/ns-windef-size) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

##  <a name="operator_-"></a>Ксизе:: operator —

Первые три из этих операторов вычитают это `CSize` значение в качестве значения параметра.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Примечания

Четвертый оператор, унарный минус, изменяет знак `CSize` значения. См. следующие описания отдельных операторов.

- **operator — (** *size* **)**

  Эта операция вычитает два `CSize` значения.

- **оператор-(** *Point* **)**

  Эта операция смещает (перемещает) значение [точки](/previous-versions/dd162805\(v=vs.85\)) или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) на обратный инверсия этого `CSize` значения. `y` `x` Значение `cx` и `cy` для этого `CSize` значения вычитаются из элементов `POINT` данных и в значении. Он аналогичен версии [CPoint:: operator-](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , принимающей параметр [size](/windows/win32/api/windef/ns-windef-size) .

- **operator — (** *лпрект* **)**

  Эта операция смещает (перемещает) значение [Rect](/previous-versions/dd162897\(v=vs.85\)) или [крект](../../atl-mfc-shared/reference/crect-class.md) на обратный инверсия этого `CSize` значения. `top` `bottom` Элементы `cx` и `cy` этого `left` значениявычитаются`RECT` из элементов данных, ,изначения.`right` `CSize` Он аналогичен версии [крект:: operator-](../../atl-mfc-shared/reference/crect-class.md#operator_-) , принимающей параметр [size](/windows/win32/api/windef/ns-windef-size) .

- **operator-()**

  Эта операция возвращает добавочное обратное значение этого `CSize` значения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>См. также

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Класс CPoint](../../atl-mfc-shared/reference/cpoint-class.md)
