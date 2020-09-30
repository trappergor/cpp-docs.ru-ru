---
title: Класс Крект
ms.date: 11/06/2018
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
ms.openlocfilehash: f45090971e8dbb89ae281b408cc3a14e102ffe17
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502885"
---
# <a name="crect-class"></a>Класс Крект

Аналогично структуре [прямоугольника](/windows/win32/api/windef/ns-windef-rect) Windows.

## <a name="syntax"></a>Синтаксис

```
class CRect : public tagRECT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Крект:: Крект](#crect)|Формирует объект `CRect`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Крект:: Боттомригхт](#bottomright)|Возвращает правую нижнюю точку `CRect` .|
|[Крект:: Центерпоинт](#centerpoint)|Возвращает центерпоинт объекта `CRect` .|
|[Крект:: Копирект](#copyrect)|Копирует размеры исходного прямоугольника в `CRect` .|
|[Крект::D Ефлатерект](#deflaterect)|Уменьшает ширину и высоту `CRect` .|
|[Крект:: Екуалрект](#equalrect)|Определяет `CRect` , равен ли значение данному прямоугольнику.|
|[Крект:: Height](#height)|Вычисляет высоту `CRect` .|
|[Крект:: Инфлатерект](#inflaterect)|Увеличивает ширину и высоту `CRect` .|
|[Крект:: Интерсектрект](#intersectrect)|Задает значение `CRect` , равное пересечению двух прямоугольников.|
|[Крект:: Исректемпти](#isrectempty)|Определяет `CRect` , является ли пустой. `CRect` пуст, если ширина и (или) Высота равны 0.|
|[Крект:: Исректнулл](#isrectnull)|Определяет, равны ли значения `top` `bottom` `left` переменных члена,, и `right` 0.|
|[Крект:: Моветокс](#movetox)|Переходит `CRect` к указанной координате x.|
|[Крект:: Моветокси](#movetoxy)|Переходит `CRect` к указанным координатам x и y.|
|[Крект:: Моветой](#movetoy)|Переходит `CRect` к указанной координате y.|
|[Крект:: Нормализерект](#normalizerect)|Стандартизация высоты и ширины `CRect` .|
|[Крект:: Оффсетрект](#offsetrect)|Перемещается `CRect` по указанным смещениям.|
|[Крект::P Тинрект](#ptinrect)|Определяет, находится ли указанная точка в `CRect` .|
|[Крект:: SetRect](#setrect)|Задает размеры `CRect` .|
|[Крект:: Сетректемпти](#setrectempty)|Задает `CRect` пустой прямоугольник (все координаты равны 0).|
|[Крект:: size](#size)|Вычисляет размер `CRect` .|
|[Крект:: Субтрактрект](#subtractrect)|Вычитает один прямоугольник из другого.|
|[Крект:: Топлефт](#topleft)|Возвращает левую верхнюю точку `CRect` .|
|[Крект:: Унионрект](#unionrect)|Задает значение `CRect` , равное объединению двух прямоугольников.|
|[Крект:: Width](#width)|Вычисляет ширину `CRect` .|

### <a name="public-operators"></a>Открытые операторы

|Название|Описание|
|----------|-----------------|
|[Крект:: operator —](#operator_-)|Вычитает заданные смещения из `CRect` или Deflate `CRect` и возвращает результирующий объект `CRect` .|
|[Крект:: operator ЛПКРЕКТ](#operator_lpcrect)|Преобразует `CRect` в `LPCRECT`.|
|[Крект:: operator ЛПРЕКТ](#operator_lprect)|Преобразует `CRect` в `LPRECT`.|
|[Крект:: operator! =](#operator_neq)|Определяет `CRect` , не равен ли прямоугольнику.|
|[Крект:: operator &amp;](#operator_amp)|Создает пересечение `CRect` и прямоугольник и возвращает результирующий объект `CRect` .|
|[Крект:: operator &amp;=](#operator_amp_eq)|Задает значение, `CRect` равное пересечению `CRect` и прямоугольнику.|
|[Крект:: operator &#124;](#operator_or)|Создает объединение `CRect` и прямоугольник и возвращает результирующий объект `CRect` .|
|[Крект:: operator &#124;=](#operator_or_eq)|Задает значение, `CRect` равное объединению `CRect` и прямоугольнику.|
|[Крект:: operator +](#operator_add)|Добавляет заданное смещение в `CRect` или Deflate `CRect` и возвращает результирующий объект `CRect` .|
|[Крект:: operator + =](#operator_add_eq)|Добавляет указанные смещения в `CRect` или Deflate `CRect` .|
|[Крект:: operator =](#operator_eq)|Копирует размеры прямоугольника в `CRect` .|
|[Крект:: operator-=](#operator_-_eq)|Вычитает заданные смещения из `CRect` или Deflate `CRect` .|
|[Крект:: operator = =](#operator_eq_eq)|Определяет `CRect` , равен ли прямоугольник.|

## <a name="remarks"></a>Remarks

`CRect` также включает функции элементов для работы с `CRect` объектами и `RECT` структурами Windows.

`CRect`Объект может передаваться как параметр функции везде, где `RECT` `LPCRECT` `LPRECT` может быть передана структура, или.

> [!NOTE]
> Этот класс является производным от `tagRECT` структуры. (Имя `tagRECT` для структуры является редко используемым именем `RECT` .) Это означает, что элементы данных ( `left` , `top` , `right` и `bottom` ) `RECT` структуры являются доступными элементами данных `CRect` .

`CRect`Содержит переменные-члены, определяющие точки прямоугольника, расположенные в верхней левой и нижней правой части.

При указании `CRect` необходимо внимательно создать его, чтобы он был нормализован, иными словами, что значение левой координаты меньше правого, а верх меньше нижней. Например, верхняя левая часть (10, 10) и Нижняя справа от (20, 20) определяют нормализованный прямоугольник, а верхний левый (20, 20) и нижний правый (10, 10) определяет Ненормализованный прямоугольник. Если прямоугольник не нормализован, многие `CRect` функции-члены могут возвращать неверные результаты. (Список этих функций см. в разделе [крект:: нормализерект](#normalizerect) .) Перед вызовом функции, требующей нормализованных прямоугольников, можно нормализовать ненормализованные прямоугольники, вызвав `NormalizeRect` функцию.

Будьте внимательны при управлении `CRect` с помощью функций-членов [cdc::D Птолп](../../mfc/reference/cdc-class.md#dptolp) и [CDC:: лптодп](../../mfc/reference/cdc-class.md#lptodp) . Если в качестве режима сопоставления контекст отображения имеет отрицательное значение, то, как в `MM_LOENGLISH` , `CDC::DPtoLP` преобразуется, `CRect` чтобы его верх больше нижней. Функции, такие как `Height` и, `Size` затем возвращают отрицательные значения для высоты преобразованной области `CRect` , а прямоугольник — без нормализации.

При использовании перегруженных `CRect` операторов первый операнд должен быть a `CRect` ; второй может быть либо структурой [Rect](/windows/win32/api/windef/ns-windef-rect) , либо `CRect` объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagRECT`

`CRect`

## <a name="requirements"></a>Требования

**Заголовок:** атлтипес. h

## <a name="crectbottomright"></a><a name="bottomright"></a> Крект:: Боттомригхт

Координаты возвращаются в виде ссылки на объект [CPoint](cpoint-class.md) , содержащийся в `CRect` .

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Координаты правого нижнего угла прямоугольника.

### <a name="remarks"></a>Remarks

Эту функцию можно использовать для получения или установки правого нижнего угла прямоугольника. Задайте угол, используя эту функцию в левой части оператора присваивания.

### <a name="example"></a>Пример

```cpp
// use BottomRight() to retrieve the bottom
// right POINT
CRect rect(210, 150, 350, 900);
CPoint ptDown;

ptDown = rect.BottomRight();

// ptDown is now set to (350, 900)
ASSERT(ptDown == CPoint(350, 900));

// or, use BottomRight() to set the bottom
// right POINT
CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);

CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

// rect2 is now (10, 10, 180, 180)
ASSERT(rect2 == CRect(10, 10, 180, 180));
```

## <a name="crectcenterpoint"></a><a name="centerpoint"></a> Крект:: Центерпоинт

Вычисляет центерпоинт, `CRect` добавляя левые и правые значения и разделив их на два, а также добавляя верхние и нижние значения и разделив их на два.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

`CPoint`Объект, центерпоинт `CRect` .

### <a name="example"></a>Пример

```cpp
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog.
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);

    // device context for painting

    // get the size and position of the client area of
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT
    // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```

## <a name="crectcopyrect"></a><a name="copyrect"></a> Крект:: Копирект

Копирует `lpSrcRect` прямоугольник в `CRect` .

```cpp
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Параметры

*лпсркрект*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект Rect `CRect` , который необходимо скопировать.

### <a name="example"></a>Пример

```cpp
CRect rectSource(35, 10, 125, 10);
CRect rectDest;

rectDest.CopyRect(&rectSource);

// rectDest is now set to (35, 10, 125, 10)

RECT rectSource2;
rectSource2.left = 0;
rectSource2.top = 0;
rectSource2.bottom = 480;
rectSource2.right = 640;

rectDest.CopyRect(&rectSource2);

// works against RECT structures, too!
// rectDest is now set to (0, 0, 640, 480)
```

## <a name="crectcrect"></a><a name="crect"></a> Крект:: Крект

Формирует объект `CRect`.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>Параметры

*l*<br/>
Задает левую точку `CRect` .

*t*<br/>
Указывает верхнюю часть `CRect` .

*r*<br/>
Указывает правую точку `CRect` .

*b*<br/>
Указывает нижнюю часть `CRect` .

*srcRect*<br/>
Ссылается на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) с координатами для `CRect` .

*лпсркрект*<br/>
Указывает на `RECT` структуру с координатами для `CRect` .

*точки*<br/>
Задает точку отсчета для создаваемого прямоугольника. Соответствует левому верхнему углу.

*size*<br/>
Задает смещение от верхнего левого угла до правого нижнего угла создаваемого прямоугольника.

*topLeft*<br/>
Задает верхнюю левую точку `CRect` .

*bottomRight*<br/>
Задает нижний правый индекс `CRect` .

### <a name="remarks"></a>Remarks

Если аргументы не заданы, `left` члены,, `top` `right` и `bottom` имеют значение 0.

`CRect` `const RECT&` Конструкторы () и `CRect` ( `LPCRECT` ) выполняют [копирект](#copyrect). Другие конструкторы напрямую инициализируют переменные членов объекта.

### <a name="example"></a>Пример

```cpp
// default constructor is equivalent to CRect(0, 0, 0, 0)
CRect emptyRect;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT structure
RECT sdkRect;
sdkRect.left = 0;
sdkRect.top = 0;
sdkRect.right = 100;
sdkRect.bottom = 50;

CRect rect2(sdkRect);
// by reference
CRect rect3(&sdkRect);

// by address
ASSERT(rect2 == rect);
ASSERT(rect3 == rect);

// from a point and a size
CPoint pt(0, 0);
CSize sz(100, 50);
CRect rect4(pt, sz);
ASSERT(rect4 == rect2);

// from two points
CPoint ptBottomRight(100, 50);
CRect rect5(pt, ptBottomRight);
ASSERT(rect5 == rect4);
```

## <a name="crectdeflaterect"></a><a name="deflaterect"></a> Крект::D Ефлатерект

`DeflateRect` Вогнутая линза `CRect` путем перемещения сторон в сторону его центра.

```cpp
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Задает число единиц, которые должны быть сведены к левой и правой сторонам `CRect` .

*y*<br/>
Указывает число единиц, которые должны быть сведены к верхнему и нижнему краям `CRect` .

*size*<br/>
[Размер](/windows/win32/api/windef/ns-windef-size) или [ксизе](csize-class.md) , указывающий количество единиц, которые нужно деувеличить `CRect` . `cx`Значение указывает количество единиц, которые должны быть сведены к левой и правой сторонам, а `cy` значение указывает количество единиц, которое будет разворотировать сверху и снизу.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` , в которой указывается количество единиц, которые должны быть сведены для каждой стороны.

*l*<br/>
Задает число единиц, которые должны быть сведены к левой стороне `CRect` .

*t*<br/>
Указывает число единиц, которое будет превышено в верхнюю часть `CRect` .

*r*<br/>
Задает число единиц, которые должны быть сведены к правой части `CRect` .

*b*<br/>
Указывает число единиц, которое будет сведено к концу `CRect` .

### <a name="remarks"></a>Remarks

Для этого `DeflateRect` добавляет единицы измерения слева и сверху и вычитает единицы из правой и нижней части. Параметры — это `DeflateRect` значения со знаком; положительные значения преобразуются в неструктурированные `CRect` и отрицательные.

Первые две перегрузки разменяют обе пары противоположных сторон `CRect` так, что ее общая ширина уменьшается на два раза *x* (или `cx` ), а ее общая высота уменьшается на два раза по *оси y* (или `cy` ). Две другие перегрузки размещаются на каждой стороне `CRect` независимо от других.

### <a name="example"></a>Пример

```cpp
CRect rect(10, 10, 50, 50);
rect.DeflateRect(1, 2);
ASSERT(rect.left == 11 && rect.right == 49);
ASSERT(rect.top == 12 && rect.bottom == 48);

CRect rect2(10, 10, 50, 50);
CRect rectDeflate(1, 2, 3, 4);
rect2.DeflateRect(&rectDeflate);
ASSERT(rect2.left == 11 && rect2.right == 47);
ASSERT(rect2.top == 12 && rect2.bottom == 46);
```

## <a name="crectequalrect"></a><a name="equalrect"></a> Крект:: Екуалрект

Определяет `CRect` , равен ли значение данному прямоугольнику.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*лпрект*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект Rect `CRect` , который содержит координаты прямоугольника в верхнем левом и нижнем правом углу.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если два прямоугольника имеют одинаковые значения сверху, слева, снизу и справа; в противном случае — 0.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
ASSERT(!rect1.EqualRect(rect3));
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1.EqualRect(&test));
```

## <a name="crectheight"></a><a name="height"></a> Крект:: Height

Вычисляет высоту `CRect` , вычитая верхнее значение из нижнего значения.

```
int Height() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Высота `CRect` .

### <a name="remarks"></a>Remarks

Результирующее значение может быть отрицательным.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

## <a name="crectinflaterect"></a><a name="inflaterect"></a> Крект:: Инфлатерект

`InflateRect` выпуклая линза `CRect` путем перемещения сторон в сторону от его центра.

```cpp
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Указывает число единиц, которое будет разворотировать левую и правую части `CRect` .

*y*<br/>
Указывает число единиц, которое будет вычислено сверху и снизу от `CRect` .

*size*<br/>
[Размер](/windows/win32/api/windef/ns-windef-size) или [ксизе](csize-class.md) , указывающий количество единиц, которое необходимо увеличить `CRect` . `cx`Значение указывает количество единиц, которое будет разворотировать левую и правую части, а `cy` значение указывает количество единиц, которое будет вычислено сверху и снизу.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или на `CRect` число единиц, которые нужно увеличить на каждой стороне.

*l*<br/>
Задает число единиц, которое необходимо увеличить с левой стороны `CRect` .

*t*<br/>
Указывает число единиц, которое будет вычислено в верхней части `CRect` .

*r*<br/>
Задает число единиц, которое нужно увеличить с правой стороны `CRect` .

*b*<br/>
Задает число единиц, которое будет изменяться снизу `CRect` .

### <a name="remarks"></a>Remarks

Для этого `InflateRect` вычитает единицы слева и сверху и добавляет единицы вправо и вниз. Параметры `InflateRect` имеют значения со знаком; положительные значения преобразуются в неровные `CRect` , а отрицательные — в неизменном виде.

Первые две перегрузки разменяют обе пары противоположных сторон `CRect` так, что ее общая ширина увеличивается на два раза *x* (или), `cx` а ее общая высота увеличивается на два раза *y* (или `cy` ). Две другие перегрузки размещаются на каждой стороне `CRect` независимо от других.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

## <a name="crectintersectrect"></a><a name="intersectrect"></a> Крект:: Интерсектрект

Устанавливает значение, `CRect` равное пересечению двух существующих прямоугольников.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Параметры

*lpRect1*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект Rect `CRect` , который содержит исходный прямоугольник.

*lpRect2*<br/>
Указывает на `RECT` структуру или `CRect` объект, который содержит исходный прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пересечение не пусто; 0, если пересечение пусто.

### <a name="remarks"></a>Remarks

Пересечением является самый крупный прямоугольник, содержащийся в обоих существующих прямоугольниках.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rectOne(125,  0, 150, 200);
CRect rectTwo(0, 75, 350, 95);
CRect rectInter;

rectInter.IntersectRect(rectOne, rectTwo);
ASSERT(rectInter == CRect(125, 75, 150, 95));
// operator &= can do the same task:

CRect rectInter2 = rectOne;
rectInter2 &= rectTwo;
ASSERT(rectInter2 == CRect(125, 75, 150, 95));
```

## <a name="crectisrectempty"></a><a name="isrectempty"></a> Крект:: Исректемпти

Определяет `CRect` , является ли пустой.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое `CRect` значение, если пусто; 0 `CRect` , если не пусто.

### <a name="remarks"></a>Remarks

Прямоугольник пуст, если ширина и (или) Высота равны 0 или минус. Отличается от `IsRectNull` , который определяет, равны ли все координаты прямоугольника нулю.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

## <a name="crectisrectnull"></a><a name="isrectnull"></a> Крект:: Исректнулл

Определяет, равны ли значения "Top", "Left", "Bottom" и "Right" `CRect` равными 0.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если `CRect` значения верхнего, левого, нижнего и правого равны 0; в противном случае — 0.

### <a name="remarks"></a>Remarks

Отличается от `IsRectEmpty` , который определяет, является ли прямоугольник пустым.

### <a name="example"></a>Пример

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

## <a name="crectmovetox"></a><a name="movetox"></a> Крект:: Моветокс

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютную координату x, заданную параметром *x*.

```cpp
void MoveToX(int x) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Абсолютная координата по оси x для левого верхнего угла прямоугольника.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

## <a name="crectmovetoxy"></a><a name="movetoxy"></a> Крект:: Моветокси

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютные заданные координаты x и y.

```cpp
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Абсолютная координата по оси x для левого верхнего угла прямоугольника.

*y*<br/>
Абсолютная координата по оси y для верхнего левого угла прямоугольника.

*точки*<br/>
`POINT`Структура, указывающая абсолютный левый верхний угол прямоугольника.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

## <a name="crectmovetoy"></a><a name="movetoy"></a> Крект:: Моветой

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютную координату y, заданную параметром *y*.

```cpp
void MoveToY(int y) throw();
```

### <a name="parameters"></a>Параметры

*y*<br/>
Абсолютная координата по оси y для верхнего левого угла прямоугольника.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

## <a name="crectnormalizerect"></a><a name="normalizerect"></a> Крект:: Нормализерект

Нормализует `CRect` таким образом, чтобы высота и ширина были положительными.

```cpp
void NormalizeRect() throw();
```

### <a name="remarks"></a>Remarks

Прямоугольник нормализован для позиционирования четвертого квадранта, который Windows обычно использует для координат. `NormalizeRect` Сравнивает верхнее и нижнее значения и меняет местами, если верхняя часть больше нижней. Аналогичным образом он меняет местами левые и правые значения, если левое значение больше правого. Эта функция полезна при работе с различными режимами сопоставления и инвертированными прямоугольниками.

> [!NOTE]
> `CRect`Для правильной работы следующих функций элементов требуются нормализованные прямоугольники: [Высота](#height), [Ширина](#width), [Размер](#size), [исректемпти](#isrectempty), [PtInRect](#ptinrect), [екуалрект](#equalrect), [унионрект](#unionrect), [интерсектрект](#intersectrect), [субтрактрект](#subtractrect), [operator = =](#operator_eq_eq), [оператор! =](#operator_neq), [оператор &#124;](#operator_or), [оператор &#124;=](#operator_or_eq), [оператор &](#operator_amp)и [оператор &=](#operator_amp_eq).

### <a name="example"></a>Пример

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

## <a name="crectoffsetrect"></a><a name="offsetrect"></a> Крект:: Оффсетрект

Перемещается `CRect` по указанным смещениям.

```cpp
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Указывает величину для перемещения влево или вправо. Оно должно быть отрицательным для перемещения влево.

*y*<br/>
Задает величину перемещения вверх или вниз. Оно должно быть отрицательным для перемещения вверх.

*точки*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий оба измерения для перемещения.

*size*<br/>
Содержит структуру [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий оба измерения для перемещения.

### <a name="remarks"></a>Remarks

Перемещает `CRect` *x* единиц вдоль осей x и *y* вдоль оси y. Параметры *x* и *y* — это значения со знаком, поэтому их `CRect` можно перемещать влево или вправо, а также вверх или вниз.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

## <a name="crectoperator-lpcrect-converts-a-crect-to-an-lpcrect"></a><a name="operator_lpcrect"></a> Крект:: operator ЛПКРЕКТ преобразует `CRect` в [лпкрект](../../mfc/reference/data-types-mfc.md).

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Remarks

При использовании этой функции не требуется оператор address-of ( **&** ). Этот оператор будет автоматически использоваться при передаче `CRect` объекта в функцию, ожидающую `LPCRECT` .

## <a name="crectoperator-lprect"></a><a name="operator_lprect"></a> Крект:: operator ЛПРЕКТ

Преобразует `CRect` в [лпрект](../../mfc/reference/data-types-mfc.md).

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Remarks

При использовании этой функции не требуется оператор address-of ( **&** ). Этот оператор будет автоматически использоваться при передаче `CRect` объекта в функцию, ожидающую `LPRECT` .

### <a name="example"></a>Пример

См. пример для [крект:: operator лпкрект](#operator_lpcrect).

## <a name="crectoperator-"></a><a name="operator_eq"></a> Крект:: operator =

Присваивает *srcRect* `CRect` .

```cpp
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Параметры

*srcRect*<br/>
Ссылается на исходный прямоугольник. Может быть [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` .

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

## <a name="crectoperator-"></a><a name="operator_eq_eq"></a> Крект:: operator = =

Определяет, `rect` равно ли равенство `CRect` , путем сравнения координат верхнего левого и нижнего правого угла.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Ссылается на исходный прямоугольник. Может быть [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если равно; в противном случае — 0.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1 == test);
```

## <a name="crectoperator-"></a><a name="operator_neq"></a> Крект:: operator! =

Определяет, является ли значение *Rect* неравным `CRect` , сравнивая координаты их верхнего левого угла.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Ссылается на исходный прямоугольник. Может быть [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если не равно; в противном случае — 0.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);
```

## <a name="crectoperator-"></a><a name="operator_add_eq"></a> Крект:: operator + =

Первые две перегрузки перемещаются `CRect` по указанным смещениям.

```cpp
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Параметры

*точки*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий количество единиц для перемещения прямоугольника.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий количество единиц перемещения прямоугольника.

*лпрект*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект Rect `CRect` , который содержит число единиц, которые нужно увеличить с каждой стороны `CRect` .

### <a name="remarks"></a>Remarks

Значения *x* и *y* (или `cx` и `cy` ) для параметра добавляются в `CRect` .

Третья перегрузка уменьшается на `CRect` число единиц, указанное в каждом элементе параметра.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-_eq"></a> Крект:: operator-=

Первые две перегрузки перемещаются `CRect` по указанным смещениям.

```cpp
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Параметры

*точки*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий количество единиц для перемещения прямоугольника.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий количество единиц перемещения прямоугольника.

*лпрект*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект Rect `CRect` , который содержит число единиц, которые должны быть сведены каждый из сторон `CRect` .

### <a name="remarks"></a>Remarks

Значения *x* и *y* (или и) для параметра `cx` `cy` вычитаются из `CRect` .

Третья перегрузка уменьшается на `CRect` число единиц, указанное в каждом элементе параметра. Обратите внимание, что эта перегрузка функция, например [дефлатерект](#deflaterect).

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp_eq"></a> Крект:: operator &amp;=

Задает значение, `CRect` равное пересечению `CRect` и `rect` .

```cpp
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Содержит [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` .

### <a name="remarks"></a>Remarks

Пересечением является самый крупный прямоугольник, содержащийся в обоих прямоугольниках.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

См. пример для [крект:: интерсектрект](#intersectrect).

## <a name="crectoperator-124"></a><a name="operator_or_eq"></a> Крект:: operator &#124;=

Задает `CRect` значение, равное объединению `CRect` и `rect` .

```cpp
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Содержит `CRect` [прямоугольник](/windows/win32/api/windef/ns-windef-rect)или.

### <a name="remarks"></a>Remarks

Объединение — это самый маленький прямоугольник, содержащий оба исходных прямоугольника.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

## <a name="crectoperator-"></a><a name="operator_add"></a> Крект:: operator +

Первые две перегрузки возвращают `CRect` объект, который равен `CRect` заданным смещениям.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>Параметры

*точки*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий количество единиц для перемещения возвращаемого значения.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий количество единиц для перемещения возвращаемого значения.

*лпрект*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект Rect `CRect` , который содержит число единиц, которые нужно увеличить с каждой стороны возвращаемого значения.

### <a name="return-value"></a>Возвращаемое значение

`CRect`Результат, полученный при перемещении или переходе `CRect` к количеству единиц, указанных в параметре.

### <a name="remarks"></a>Remarks

Значения параметров *x* и *y* (или `cx` и `cy` ) добавляются в `CRect` расположение.

Третья перегрузка возвращает новый `CRect` , который равен `CRect` количеству единиц, заданному в каждом элементе параметра.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-"></a> Крект:: operator —

Первые две перегрузки возвращают `CRect` объект, который равен `CRect` заданным смещениям.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*точки*<br/>
Структура [точек](/windows/win32/api/windef/ns-windef-point) или `CPoint` объект, указывающий количество единиц для перемещения возвращаемого значения.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или `CSize` объект, указывающий количество единиц для перемещения возвращаемого значения.

*лпрект*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект Rect `CRect` , который содержит число единиц, которые должны быть сведены по каждой стороне возвращаемого значения.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CRect` полученный в результате перемещения или деспрямления `CRect` по количеству единиц, указанных в параметре.

### <a name="remarks"></a>Remarks

Значения параметров *x* и *y* (или `cx` и `cy` ) вычитаются из `CRect` расположения.

Третья перегрузка возвращает новый `CRect` , который равен `CRect` количеству единиц, указанных в каждом элементе параметра. Обратите внимание, что эта перегрузка функции, например [дефлатерект](#deflaterect), не [субтрактрект](#subtractrect).

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp"></a> Крект:: operator &amp;

Возвращает объект `CRect` , который является пересечением `CRect` и *rect2*.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Параметры

*rect2*<br/>
Содержит [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` .

### <a name="return-value"></a>Возвращаемое значение

Объект `CRect` , представляющий собой пересечение `CRect` и *rect2*.

### <a name="remarks"></a>Remarks

Пересечением является самый крупный прямоугольник, содержащийся в обоих прямоугольниках.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

## <a name="crectoperator-124"></a><a name="operator_or"></a> Крект:: operator &#124;

Возвращает объект `CRect` , который является объединением `CRect` и *rect2*.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Параметры

*rect2*<br/>
Содержит [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` .

### <a name="return-value"></a>Возвращаемое значение

Объект `CRect` , который является объединением `CRect` и *rect2*.

### <a name="remarks"></a>Remarks

Объединение — это наименьший прямоугольник, который содержит оба прямоугольника.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectptinrect"></a><a name="ptinrect"></a> Крект::P Тинрект

Определяет, находится ли указанная точка в `CRect` .

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*точки*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если точка находится внутри `CRect` ; в противном случае — 0.

### <a name="remarks"></a>Remarks

Точка находится в пределах, `CRect` если она находится на левой или верхней стороне или находится внутри всех четырех сторон. Точка с правой или нижней стороны находится вне `CRect` .

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect(5, 5, 100, 100);
CPoint pt1(35, 50);
CPoint pt2(125, 298);

// this is true, because pt1 is inside the rectangle
ASSERT(rect.PtInRect(pt1));

// this is NOT true, because pt2 is outside the rectangle
ASSERT(!rect.PtInRect(pt2));

// note that the right and the bottom aren't inside
ASSERT(!rect.PtInRect(CPoint(35, 100)));
ASSERT(!rect.PtInRect(CPoint(100, 98)));

// but the top and the left are inside
ASSERT(rect.PtInRect(CPoint(5, 65)));
ASSERT(rect.PtInRect(CPoint(88, 5)));

// and that PtInRect() works against a POINT, too
POINT pt;
pt.x = 35;
pt.y = 50;
ASSERT(rect.PtInRect(pt));
```

## <a name="crectsetrect"></a><a name="setrect"></a> Крект:: SetRect

Задает размеры, `CRect` равные указанным координатам.

```cpp
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>Параметры

*x1*<br/>
Задает координату по оси x верхнего левого угла.

*Y1*<br/>
Задает координату по оси y верхнего левого угла.

*штук*<br/>
Задает координату по оси x правого нижнего угла.

*Y2*<br/>
Задает координату по оси y правого нижнего угла.

### <a name="example"></a>Пример

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

## <a name="crectsetrectempty"></a><a name="setrectempty"></a> Крект:: Сетректемпти

Создает `CRect` прямоугольник со значением NULL, устанавливая все координаты равными нулю.

```cpp
void SetRectEmpty() throw();
```

### <a name="example"></a>Пример

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

## <a name="crectsize"></a><a name="size"></a> Крект:: SIZE

`cx`Элементы и `cy` возвращаемого значения содержат высоту и ширину `CRect` .

```
CSize Size() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [ксизе](csize-class.md) , который содержит размер `CRect` .

### <a name="remarks"></a>Remarks

Либо высота, либо ширина могут быть отрицательными.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

## <a name="crectsubtractrect"></a><a name="subtractrect"></a> Крект:: Субтрактрект

Делает измерения `CRect` равными для вычитания `lpRectSrc2` из `lpRectSrc1` .

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Параметры

*lpRectSrc1*<br/>
Указывает на структуру или объект [Rect](/windows/win32/api/windef/ns-windef-rect) , `CRect` из которого будет вычитаться прямоугольник.

*lpRectSrc2*<br/>
Указывает на `RECT` структуру или `CRect` объект, вычитаемый из прямоугольника, на который указывает параметр *lpRectSrc1* .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Вычитание является наименьшим прямоугольником, содержащим все точки в *lpRectScr1* , которые не находятся в пересечении *lpRectScr1* и *lpRectScr2*.

Прямоугольник, заданный параметром *lpRectSrc1* , будет неизменным, если прямоугольник, заданный параметром *lpRectSrc2* , не полностью пересекается с прямоугольником, заданным параметром *lpRectSrc1* , по крайней мере в одном из направлений x или y.

Например, если *lpRectSrc1* были (10, 10, 100 100) и *lpRectSrc2* (50, 50, 150 150), то прямоугольник, на который указывает *lpRectSrc1* , будет неизменным при возвращении функции. Если *lpRectSrc1* были (10, 10, 100 100) и *lpRectSrc2* (50, 10, 150 150), то прямоугольник, на который указывает *lpRectSrc1* , будет содержать координаты (10, 10, 50 100) при возвращении функции.

`SubtractRect` не совпадает с [оператором operator-](#operator_-) and [-=](#operator_-_eq). Ни один из этих операторов никогда не вызывается `SubtractRect` .

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
RECT   rectOne;
RECT   rectTwo;

rectOne.left = 10;
rectOne.top = 10;
rectOne.bottom = 100;
rectOne.right = 100;

rectTwo.left = 50;
rectTwo.top = 10;
rectTwo.bottom = 150;
rectTwo.right = 150;

CRect   rectDiff;

rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

ASSERT(rectDiff == rectResult);

// works for CRect, too, since there is
// implicit CRect -> LPCRECT conversion

CRect rect1(10, 10, 100, 100);
CRect rect2(50, 10, 150, 150);
CRect rectOut;

rectOut.SubtractRect(rect1, rect2);
ASSERT(rectResult == rectOut);
```

## <a name="crecttopleft"></a><a name="topleft"></a> Крект:: Топлефт

Координаты возвращаются в виде ссылки на объект [CPoint](cpoint-class.md) , содержащийся в `CRect` .

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Координаты верхнего левого угла прямоугольника.

### <a name="remarks"></a>Remarks

С помощью этой функции можно получить или задать левый верхний угол прямоугольника. Задайте угол, используя эту функцию в левой части оператора присваивания.

### <a name="example"></a>Пример

См. пример для [крект:: центерпоинт](#centerpoint).

## <a name="crectunionrect"></a><a name="unionrect"></a> Крект:: Унионрект

Устанавливает размеры, `CRect` равные объединению двух исходных прямоугольников.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Параметры

*lpRect1*<br/>
Указывает на [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` , который содержит исходный прямоугольник.

*lpRect2*<br/>
Указывает на `RECT` или `CRect` , который содержит исходный прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объединение не пусто; 0, если объединение пусто.

### <a name="remarks"></a>Remarks

Объединение — это самый маленький прямоугольник, содержащий оба исходных прямоугольника.

Windows игнорирует размеры пустого прямоугольника; то есть прямоугольник, который не имеет высоты или не имеет ширины.

> [!NOTE]
> Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectwidth"></a><a name="width"></a> Крект:: Width

Вычисляет ширину `CRect` , вычитая левое значение из правого.

```
int Width() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ширина `CRect` .

### <a name="remarks"></a>Remarks

Ширина может быть отрицательной.

> [!NOTE]
> Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
// nWid is now 60
ASSERT(nWid == 60);
```

## <a name="see-also"></a>См. также раздел

[Класс CPoint](cpoint-class.md)<br/>
[Класс Ксизе](csize-class.md)<br/>
[ПЕРЕТАСКИВАЕМЫЕ](/windows/win32/api/windef/ns-windef-rect)
