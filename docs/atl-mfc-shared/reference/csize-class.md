---
title: Класс CSize
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
ms.openlocfilehash: 36da88a49e7d0e648d44b0798e108a60abb935d9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415153"
---
# <a name="csize-class"></a>Класс CSize

Аналог структуры [SIZE](/windows/desktop/api/windef/ns-windef-tagsize) в ОС Windows, реализующий относительные координаты или положение.

## <a name="syntax"></a>Синтаксис

```
class CSize : public tagSIZE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CSize::CSize](#csize)|Создает объект `CSize`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSize::operator-](#operator_-)|Вычитает два размера.|
|[CSize::operator! =](#operator_neq)|Проверяет неравенство между `CSize` и размер.|
|[CSize::operator +](#operator_add)|Добавляет два размера.|
|[CSize::operator +=](#operator_add_eq)|Добавляет размер `CSize`.|
|[CSize::operator-=](#operator_-_eq)|Вычитает размер из `CSize`.|
|[CSize::operator ==](#operator_eq_eq)|Проверяет равенство между `CSize` и размер.|

## <a name="remarks"></a>Примечания

Этот класс является производным от `SIZE` структуры. Это означает, что вы можете передать `CSize` в параметр, который требует `SIZE` и что члены данных `SIZE` структуры являются членами доступные данные `CSize`.

`cx` И `cy` членами `SIZE` (и `CSize`) являются открытыми. Кроме того `CSize` реализует функции-члены для управления `SIZE` структуры.

> [!NOTE]
> Дополнительные сведения о общие служебные классы (как `CSize`), см. в разделе [общих классов](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagSIZE`

`CSize`

## <a name="requirements"></a>Требования

**Заголовок:** atltypes.h

##  <a name="csize"></a>  CSize::CSize

Создает объект `CSize`.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Параметры

*initCX*<br/>
Наборы `cx` член для `CSize`.

*initCY*<br/>
Наборы `cy` член для `CSize`.

*initSize*<br/>
[РАЗМЕР](/windows/desktop/api/windef/ns-windef-tagsize) структуры или `CSize` объект, используемый для инициализации `CSize`.

*initPt*<br/>
[ТОЧКА](/windows/desktop/api/windef/ns-windef-tagpoint) структуры или `CPoint` объект, используемый для инициализации `CSize`.

*dwSize*<br/>
DWORD используется для инициализации `CSize`. Младшее слово — `cx` член и старшее слово является `cy` член.

### <a name="remarks"></a>Примечания

Если аргументы не указаны, `cx` и `cy` инициализируются нулевым значением.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CSize::operator ==

Проверяет равенство двух размеров.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает ненулевое значение, если размеры равны, otherwize 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

##  <a name="operator_neq"></a>  CSize::operator! =

Проверяет неравенство двух размеров.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Примечания

Возвращает ненулевое значение, если размеры не равны; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CSize::operator +=

Добавляет это размер `CSize`.

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CSize::operator-=

Вычитает размер из этого `CSize`.

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

##  <a name="operator_add"></a>  CSize::operator +

Добавьте эти операторы `CSize` задаваемое значение параметра.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Примечания

См. в следующих описаниях отдельных операторов:

- **оператор + (** *размер* **)**

  Эта операция добавляет два `CSize` значения.

- **оператор + (** *точки* **)**

  Эта операция смещений (перемещается) [ТОЧКИ](/previous-versions/dd162805\(v=vs.85\)) (или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) значение в данном `CSize` значение. `cx` И `cy` элементов этой `CSize` значение добавляются к `x` и `y` данные-члены `POINT` значение. Он аналогичен версии [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , принимающий [размер](/windows/desktop/api/windef/ns-windef-tagsize) параметра.

- **оператор + (** *lpRect* **)**

   Эта операция смещений (перемещается) [RECT](/previous-versions/dd162897\(v=vs.85\)) (или [CRect](../../atl-mfc-shared/reference/crect-class.md)) значение в данном `CSize` значение. `cx` И `cy` элементов этой `CSize` значение добавляются к `left`, `top`, `right`, и `bottom` данные-члены `RECT` значение. Он аналогичен версии [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , принимающий [размер](/windows/desktop/api/windef/ns-windef-tagsize) параметра.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

##  <a name="operator_-"></a>  CSize::operator-

Первые три из этих операторов вычесть это `CSize` задаваемое значение параметра.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Примечания

Четвертый оператор "унарный минус", изменяет знак `CSize` значение. См. в следующих описаниях отдельных операторов:

- **оператор-(** *размер* **)**

  Эта операция Находит разность двух `CSize` значения.

- **оператор-(** *точки* **)**

  Эта операция смещений (перемещается) [ТОЧКИ](/previous-versions/dd162805\(v=vs.85\)) или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) значение аддитивную инверсию `CSize` значение. `cx` И `cy` этого `CSize` значение вычитается из `x` и `y` данные-члены `POINT` значение. Он аналогичен версии [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , принимающий [размер](/windows/desktop/api/windef/ns-windef-tagsize) параметра.

- **оператор-(** *lpRect* **)**

  Эта операция смещений (перемещается) [RECT](/previous-versions/dd162897\(v=vs.85\)) или [CRect](../../atl-mfc-shared/reference/crect-class.md) значение аддитивную инверсию `CSize` значение. `cx` И `cy` элементов этой `CSize` значение вычитается из `left`, `top`, `right`, и `bottom` данные-члены `RECT` значение. Он аналогичен версии [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) , принимающий [размер](/windows/desktop/api/windef/ns-windef-tagsize) параметра.

- **оператор-)**

  Эта операция Возвращает аддитивную инверсию `CSize` значение.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Класс CPoint](../../atl-mfc-shared/reference/cpoint-class.md)

