---
title: Класс CSize | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71a96e54c3182db3fa57798f962ae5565aeca812
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752269"
---
# <a name="csize-class"></a>Класс CSize

Аналогичную Windows [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры, реализующий относительные координаты или положение.

## <a name="syntax"></a>Синтаксис

```
class CSize : public tagSIZE 
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
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
>  Дополнительные сведения о общие служебные классы (как `CSize`), см. в разделе [общих классов](../../atl-mfc-shared/atl-mfc-shared-classes.md).

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

*initCX*  
Наборы `cx` член для `CSize`.

*initCY*  
Наборы `cy` член для `CSize`.

*initSize*  
[РАЗМЕР](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или `CSize` объект, используемый для инициализации `CSize`.

*initPt*  
[ТОЧКА](../../mfc/reference/point-structure1.md) структуры или `CPoint` объект, используемый для инициализации `CSize`.

*dwSize*  
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

- **оператор + (** `size` **)** эта операция добавляет два `CSize` значения.

- **оператор + (** `point` **)** эта операция смещений (перемещается) [ТОЧКИ](https://msdn.microsoft.com/library/windows/desktop/dd162805) (или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) значение в данном `CSize` значение. **Cx** и **cy** элементов этой `CSize` значение добавляются к **x** и **y** данные-члены **ТОЧКИ**  значение. Он аналогичен версии [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , принимающий [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) параметра.

- **оператор + (** `lpRect` **)** эта операция смещений (перемещается) [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) (или [CRect](../../atl-mfc-shared/reference/crect-class.md)) значение в данном `CSize` значение. **Cx** и **cy** элементов этой `CSize` значение добавляются к **левой**, **верхней**, **справа**, и **нижней** данные-члены `RECT` значение. Он аналогичен версии [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , принимающий [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) параметра.

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

- **оператор-(** `size` **)** эта операция Находит разность двух `CSize` значения.

- **оператор-(** `point` **)** эта операция смещений (перемещается) [ТОЧКИ](https://msdn.microsoft.com/library/windows/desktop/dd162805) или [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) значение аддитивную инверсию `CSize` значение. **Cx** и **cy** этого `CSize` значение вычитается из **x** и **y** данные-члены **ТОЧКИ**  значение. Он аналогичен версии [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , принимающий [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) параметра.

- **оператор-(** `lpRect` **)** эта операция смещений (перемещается) [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) или [CRect](../../atl-mfc-shared/reference/crect-class.md) значение аддитивную инверсию `CSize` значение. **Cx** и **cy** элементов этой `CSize` значение вычитается из **левой**, **верхней**, **справа**, и **нижней** данные-члены `RECT` значение. Он аналогичен версии [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) , принимающий [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) параметра.

- **оператор-()** эта операция Возвращает аддитивную инверсию `CSize` значение.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../visual-cpp-samples.md)   
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)   
[Класс CPoint](../../atl-mfc-shared/reference/cpoint-class.md)

