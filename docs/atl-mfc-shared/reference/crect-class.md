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
ms.openlocfilehash: 13f86c411cca98f5817d1b3b2d9162ae8af8b734
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866536"
---
# <a name="crect-class"></a>Класс Крект

Аналогично структуре [прямоугольника](/windows/win32/api/windef/ns-windef-rect) Windows.

## <a name="syntax"></a>Синтаксис

```
class CRect : public tagRECT
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Крект:: Крект](#crect)|Формирует объект `CRect`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Крект:: Боттомригхт](#bottomright)|Возвращает правую нижнюю точку `CRect`.|
|[Крект:: Центерпоинт](#centerpoint)|Возвращает центерпоинт `CRect`.|
|[Крект:: Копирект](#copyrect)|Копирует измерения исходного прямоугольника в `CRect`.|
|[Крект::D Ефлатерект](#deflaterect)|Уменьшает ширину и высоту `CRect`.|
|[Крект:: Екуалрект](#equalrect)|Определяет, равен ли `CRect` данному прямоугольнику.|
|[Крект:: Height](#height)|Вычисляет высоту `CRect`.|
|[Крект:: Инфлатерект](#inflaterect)|Увеличивает ширину и высоту `CRect`.|
|[Крект:: Интерсектрект](#intersectrect)|Задает `CRect` равно пересечению двух прямоугольников.|
|[Крект:: Исректемпти](#isrectempty)|Определяет, является ли `CRect` пустым. `CRect` пуст, если ширина и (или) Высота равны 0.|
|[Крект:: Исректнулл](#isrectnull)|Определяет, равны ли переменные членов `top`, `bottom`, `left`и `right` 0.|
|[Крект:: Моветокс](#movetox)|Перемещает `CRect` на указанную координату x.|
|[Крект:: Моветокси](#movetoxy)|Перемещает `CRect` к указанным координатам x и y.|
|[Крект:: Моветой](#movetoy)|Перемещает `CRect` в указанную координату по оси y.|
|[Крект:: Нормализерект](#normalizerect)|Стандартизация высоты и ширины `CRect`.|
|[Крект:: Оффсетрект](#offsetrect)|Перемещает `CRect` по указанным смещениям.|
|[Крект::P Тинрект](#ptinrect)|Определяет, находится ли указанная точка в пределах `CRect`.|
|[Крект:: SetRect](#setrect)|Задает размеры `CRect`.|
|[Крект:: Сетректемпти](#setrectempty)|Задает `CRect` пустому прямоугольнику (все координаты равны 0).|
|[Крект:: size](#size)|Вычисляет размер `CRect`.|
|[Крект:: Субтрактрект](#subtractrect)|Вычитает один прямоугольник из другого.|
|[Крект:: Топлефт](#topleft)|Возвращает левую верхнюю точку `CRect`.|
|[Крект:: Унионрект](#unionrect)|Задает `CRect` равное объединению двух прямоугольников.|
|[Крект:: Width](#width)|Вычисляет ширину `CRect`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Крект:: operator —](#operator_-)|Вычитает заданные смещения из `CRect` или Deflate `CRect` и возвращает результирующую `CRect`.|
|[Крект:: operator ЛПКРЕКТ](#operator_lpcrect)|Преобразует `CRect` в `LPCRECT`.|
|[Крект:: operator ЛПРЕКТ](#operator_lprect)|Преобразует `CRect` в `LPRECT`.|
|[Крект:: operator! =](#operator_neq)|Определяет, не равен ли `CRect` прямоугольнику.|
|[Крект:: operator &amp;](#operator_amp)|Создает пересечение `CRect` и прямоугольника и возвращает результирующую `CRect`.|
|[Крект:: operator &amp;=](#operator_amp_eq)|Задает `CRect` равно пересечению `CRect` и прямоугольника.|
|[Крект:: operator&#124;](#operator_or)|Создает объединение `CRect` и прямоугольника и возвращает результирующую `CRect`.|
|[Крект:: operator &#124;=](#operator_or_eq)|Задает `CRect` равное объединению `CRect` и прямоугольника.|
|[Крект:: operator +](#operator_add)|Добавляет заданное смещение в `CRect` или Deflate `CRect` и возвращает полученный `CRect`.|
|[Крект:: operator + =](#operator_add_eq)|Добавляет указанные смещения в `CRect` или Deflate `CRect`.|
|[Крект:: operator =](#operator_eq)|Копирует размеры прямоугольника в `CRect`.|
|[Крект:: operator-=](#operator_-_eq)|Вычитает указанные смещения из `CRect` или Deflate `CRect`.|
|[Крект:: operator = =](#operator_eq_eq)|Определяет, равен ли `CRect` прямоугольнику.|

## <a name="remarks"></a>Remarks

`CRect` также включает функции элементов для работы с `CRect`ными объектами и структурами Windows `RECT`.

Объект `CRect` может передаваться как параметр функции везде, где можно передавать `RECT` структуру, `LPCRECT`или `LPRECT`.

> [!NOTE]
> Этот класс является производным от структуры `tagRECT`. (Имя `tagRECT` является редко используемым именем для структуры `RECT`.) Это означает, что элементы данных (`left`, `top`, `right`и `bottom`) структуры `RECT` являются доступными элементами данных `CRect`.

`CRect` содержит переменные-члены, определяющие верхнюю левую и правую точки прямоугольника.

При указании `CRect`необходимо внимательно создать его, чтобы он был нормализован, иными словами, что значение левой координаты меньше правого, а верх меньше нижней. Например, верхняя левая часть (10, 10) и Нижняя справа от (20, 20) определяют нормализованный прямоугольник, а верхний левый (20, 20) и нижний правый (10, 10) определяет Ненормализованный прямоугольник. Если прямоугольник не нормализован, многие функции-члены `CRect` могут возвращать неверные результаты. (Список этих функций см. в разделе [крект:: нормализерект](#normalizerect) .) Перед вызовом функции, требующей нормализованных прямоугольников, можно нормализовать ненормализованные прямоугольники, вызвав функцию `NormalizeRect`.

Будьте внимательны при управлении `CRect` с помощью функций-членов [CDC::D птолп](../../mfc/reference/cdc-class.md#dptolp) и [CDC:: лптодп](../../mfc/reference/cdc-class.md#lptodp) . Если в качестве режима сопоставления контекст отображения имеет отрицательное значение, как в `MM_LOENGLISH`, `CDC::DPtoLP` преобразует `CRect`, чтобы его верхнюю часть превышала нижнюю. Такие функции, как `Height` и `Size`, будут возвращать отрицательные значения высоты преобразованных `CRect`, а прямоугольник не будет нормализован.

При использовании перегруженных операторов `CRect` первый операнд должен быть `CRect`; второй может быть либо структурой [Rect](/windows/win32/api/windef/ns-windef-rect) , либо объектом `CRect`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagRECT`

`CRect`

## <a name="requirements"></a>Требования

**Заголовок:** атлтипес. h

##  <a name="bottomright"></a>Крект:: Боттомригхт

Координаты возвращаются в виде ссылки на объект [CPoint](cpoint-class.md) , содержащийся в `CRect`.

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

##  <a name="centerpoint"></a>Крект:: Центерпоинт

Вычисляет центерпоинт `CRect`, добавляя левые и правые значения и разделив их на два, а также добавляя верхние и нижние значения и деление на два.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CPoint`, центерпоинт `CRect`.

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

##  <a name="copyrect"></a>Крект:: Копирект

Копирует прямоугольник `lpSrcRect` в `CRect`.

```
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Параметры

*лпсркрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, который необходимо скопировать.

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

##  <a name="crect"></a>Крект:: Крект

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
Задает левую точку `CRect`.

*t*<br/>
Указывает верхнюю часть `CRect`.

*r*<br/>
Указывает правую точку `CRect`.

*b*<br/>
Указывает нижнюю часть `CRect`.

*srcRect*<br/>
Ссылается на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) с координатами для `CRect`.

*лпсркрект*<br/>
Указывает на структуру `RECT` с координатами для `CRect`.

*point*<br/>
Задает точку отсчета для создаваемого прямоугольника. Соответствует левому верхнему углу.

*size*<br/>
Задает смещение от верхнего левого угла до правого нижнего угла создаваемого прямоугольника.

*топлефт*<br/>
Задает верхнюю левую точку `CRect`.

*боттомригхт*<br/>
Задает расположение `CRect`в нижнем правом углу.

### <a name="remarks"></a>Remarks

Если аргументы не заданы, элементы `left`, `top`, `right`и `bottom` не инициализируются.

Конструкторы `CRect`(`const RECT&`) и `CRect`(`LPCRECT`) выполняют [копирект](#copyrect). Другие конструкторы напрямую инициализируют переменные членов объекта.

### <a name="example"></a>Пример

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

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

##  <a name="deflaterect"></a>Крект::D Ефлатерект

`DeflateRect` Deflate `CRect`, перемещая свои стороны в центр.

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Указывает число единиц, которые должны быть сведены к левой и правой сторонам `CRect`.

*y*<br/>
Указывает число единиц, которое будет сведено к началу и низу `CRect`.

*size*<br/>
[Размер](/windows/win32/api/windef/ns-windef-size) или [ксизе](csize-class.md) , указывающий количество единиц для `CRect`. Значение `cx` указывает количество единиц, которые должны быть сведены к левому и правому краю, а значение `cy` указывает число единиц, которое будет сведено сверху и снизу.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`, в которой указывается количество единиц, которые должны быть сведены каждую сторону.

*l*<br/>
Указывает число единиц, которые должны быть сведены к левой стороне `CRect`.

*t*<br/>
Указывает число единиц, которое будет сведено к началу `CRect`.

*r*<br/>
Указывает число единиц, которые должны быть сведены к правой части `CRect`.

*b*<br/>
Указывает число единиц, которое будет сведено к концу `CRect`.

### <a name="remarks"></a>Remarks

Для этого `DeflateRect` добавляет единицы к левому и верхнему краю и вычитает единицы из правой и нижней части. Параметры `DeflateRect` являются значениями со знаком. положительные значения `CRect` и отрицательные значения преувеличиваются в неизменном виде.

Первые две перегрузки разменяют обе пары противоположных сторон `CRect` таким образом, что ее общая ширина уменьшается на два раза *x* (или `cx`), а ее общая высота уменьшается на два раза по *оси y* (или `cy`). Две другие перегрузки размещаются в каждой стороне `CRect` независимо от других.

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

##  <a name="equalrect"></a>Крект:: Екуалрект

Определяет, равен ли `CRect` данному прямоугольнику.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, содержащий координаты прямоугольника в верхнем левом и нижнем правом углу.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если два прямоугольника имеют одинаковые значения сверху, слева, снизу и справа; в противном случае — 0.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

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

##  <a name="height"></a>Крект:: Height

Вычисляет высоту `CRect`, вычитая верхнее значение из нижнего значения.

```
int Height() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Высота `CRect`.

### <a name="remarks"></a>Remarks

Результирующее значение может быть отрицательным.

> [!NOTE]
>  Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

##  <a name="inflaterect"></a>Крект:: Инфлатерект

`InflateRect` расширяет `CRect`, перемещая свои стороны за пределы центра.

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Задает число единиц, которое необходимо увеличить до левой и правой частей `CRect`.

*y*<br/>
Указывает число единиц, которое будет вычислено сверху и снизу от `CRect`.

*size*<br/>
[Размер](/windows/win32/api/windef/ns-windef-size) или [ксизе](csize-class.md) , указывающий количество единиц, которое необходимо увеличить `CRect`. Значение `cx` указывает количество единиц, которое будет разворотировать левую и правую части, а значение `cy` указывает количество единиц, которое нужно увеличить сверху и снизу.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`, указывающую количество единиц, которые нужно увеличить на каждой стороне.

*l*<br/>
Указывает число единиц, которое необходимо увеличить слева от `CRect`.

*t*<br/>
Указывает число единиц, которое будет превышено в верхней части `CRect`.

*r*<br/>
Указывает число единиц, которое необходимо увеличить с правой стороны `CRect`.

*b*<br/>
Указывает число единиц, которое будет сведено к концу `CRect`.

### <a name="remarks"></a>Remarks

Для этого `InflateRect` вычитает единицы слева и сверху и добавляет единицы вправо и вниз. Параметры `InflateRect` являются значениями со знаком. положительные значения пре`CRect`ся, а отрицательные — в неизменном виде.

Первые две перегрузки разменяют обе пары противоположных сторон `CRect` таким образом, что ее общая ширина увеличивается на два раза *x* (или `cx`), а ее общая высота увеличивается на два раза по *оси y* (или `cy`). Две другие перегрузки премещаются в каждую сторону `CRect` независимо от других.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

##  <a name="intersectrect"></a>Крект:: Интерсектрект

Делает `CRect` равным пересечению двух существующих прямоугольников.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Параметры

*lpRect1*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, содержащий исходный прямоугольник.

*lpRect2*<br/>
Указывает на `RECT` структуру или `CRect` объект, содержащий исходный прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пересечение не пусто; 0, если пересечение пусто.

### <a name="remarks"></a>Remarks

Пересечением является самый крупный прямоугольник, содержащийся в обоих существующих прямоугольниках.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

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

##  <a name="isrectempty"></a>Крект:: Исректемпти

Определяет, является ли `CRect` пустым.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если `CRect` пусто; 0, если `CRect` не пуста.

### <a name="remarks"></a>Remarks

Прямоугольник пуст, если ширина и (или) Высота равны 0 или минус. Отличается от `IsRectNull`, которая определяет, равны ли все координаты прямоугольника нулю.

> [!NOTE]
>  Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

##  <a name="isrectnull"></a>Крект:: Исректнулл

Определяет, равны ли значения верхнего, левого, нижнего и правого `CRect` значений 0.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если значения верхнего, левого, нижнего и правого `CRect`равны 0; в противном случае — 0.

### <a name="remarks"></a>Remarks

Отличается от `IsRectEmpty`, которая определяет, пуст ли прямоугольник.

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

##  <a name="movetox"></a>Крект:: Моветокс

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютную координату x, заданную параметром *x*.

```
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

##  <a name="movetoxy"></a>Крект:: Моветокси

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютные заданные координаты x и y.

```
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Абсолютная координата по оси x для левого верхнего угла прямоугольника.

*y*<br/>
Абсолютная координата по оси y для верхнего левого угла прямоугольника.

*point*<br/>
Структура `POINT`, указывающая абсолютный левый верхний угол прямоугольника.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

##  <a name="movetoy"></a>Крект:: Моветой

Вызовите эту функцию, чтобы переместить прямоугольник в абсолютную координату y, заданную параметром *y*.

```
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

##  <a name="normalizerect"></a>Крект:: Нормализерект

Нормализует `CRect` таким образом, чтобы высота и ширина были положительными.

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>Remarks

Прямоугольник нормализован для позиционирования четвертого квадранта, который Windows обычно использует для координат. `NormalizeRect` сравнивает верхнее и нижнее значения и меняет местами, если верхняя часть больше нижней. Аналогичным образом он меняет местами левые и правые значения, если левое значение больше правого. Эта функция полезна при работе с различными режимами сопоставления и инвертированными прямоугольниками.

> [!NOTE]
> Для правильной работы следующих `CRect` функций элементов требуются нормализованные прямоугольники: [Высота](#height), [Ширина](#width), [Размер](#size), [исректемпти](#isrectempty), [PtInRect](#ptinrect), [екуалрект](#equalrect), [унионрект](#unionrect), [интерсектрект](#intersectrect), [субтрактрект](#subtractrect), [operator = =](#operator_eq_eq), оператор [! =](#operator_neq), [оператор &#124; ](#operator_or), [оператор &#124;=](#operator_or_eq), [оператор &](#operator_amp)и [оператор & =](#operator_amp_eq).

### <a name="example"></a>Пример

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

##  <a name="offsetrect"></a>Крект:: Оффсетрект

Перемещает `CRect` по указанным смещениям.

```
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Указывает величину для перемещения влево или вправо. Оно должно быть отрицательным для перемещения влево.

*y*<br/>
Задает величину перемещения вверх или вниз. Оно должно быть отрицательным для перемещения вверх.

*point*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий оба измерения для перемещения.

*size*<br/>
Содержит структуру [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий оба измерения для перемещения.

### <a name="remarks"></a>Remarks

Перемещает `CRect`*x* единиц вдоль осей x и *y* вдоль оси y. Параметры *x* и *y* — это значения со знаком, поэтому `CRect` можно перемещать влево или вправо, а также вверх или вниз.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

##  <a name="operator_lpcrect"></a>Крект:: operator ЛПКРЕКТ преобразует `CRect` в [лпкрект](../../mfc/reference/data-types-mfc.md).

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Remarks

При использовании этой функции не требуется оператор адреса ( **&** ). Этот оператор будет автоматически использоваться при передаче `CRect` объекта в функцию, ожидающую `LPCRECT`.

##  <a name="operator_lprect"></a>Крект:: operator ЛПРЕКТ

Преобразует `CRect` в [лпрект](../../mfc/reference/data-types-mfc.md).

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Remarks

При использовании этой функции не требуется оператор адреса ( **&** ). Этот оператор будет автоматически использоваться при передаче `CRect` объекта в функцию, ожидающую `LPRECT`.

### <a name="example"></a>Пример

См. пример для [крект:: operator лпкрект](#operator_lpcrect).

##  <a name="operator_eq"></a>Крект:: operator =

Назначает *srcRect* для `CRect`.

```
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Параметры

*srcRect*<br/>
Ссылается на исходный прямоугольник. Может быть [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="example"></a>Пример

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

##  <a name="operator_eq_eq"></a>Крект:: operator = =

Определяет, равно ли `rect` `CRect`, сравнивая координаты их верхнего левого угла.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Ссылается на исходный прямоугольник. Может быть [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если равно; в противном случае — 0.

### <a name="remarks"></a>Remarks

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

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

##  <a name="operator_neq"></a>Крект:: operator! =

Определяет, является ли значение *Rect* неравным `CRect` путем сравнения координат их верхнего левого и нижнего правого угла.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Ссылается на исходный прямоугольник. Может быть [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если не равно; в противном случае — 0.

### <a name="remarks"></a>Remarks

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

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

##  <a name="operator_add_eq"></a>Крект:: operator + =

Первые две перегрузки переходят `CRect` по указанным смещениям.

```
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий количество единиц для перемещения прямоугольника.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий количество единиц перемещения прямоугольника.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, который содержит число единиц, которые нужно увеличить на каждой стороне `CRect`.

### <a name="remarks"></a>Remarks

Значения *x* и *y* (или `cx` и `cy`) параметра добавляются в `CRect`.

Третья перегрузка `CRect`ся по количеству единиц, указанных в каждом элементе параметра.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

##  <a name="operator_-_eq"></a>Крект:: operator-=

Первые две перегрузки переходят `CRect` по указанным смещениям.

```
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий количество единиц для перемещения прямоугольника.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий количество единиц перемещения прямоугольника.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, который содержит число единиц, которые должны быть сведены каждый из сторон `CRect`.

### <a name="remarks"></a>Remarks

Значения *x* и *y* (или `cx` и `cy`) вычитаются из `CRect`.

Третья перегрузка уменьшает `CRect` на число единиц, указанное в каждом элементе параметра. Обратите внимание, что эта перегрузка функция, например [дефлатерект](#deflaterect).

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

##  <a name="operator_amp_eq"></a>Крект:: operator &amp;=

Задает `CRect` равно пересечению `CRect` и `rect`.

```
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Содержит [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="remarks"></a>Remarks

Пересечением является самый крупный прямоугольник, содержащийся в обоих прямоугольниках.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

См. пример для [крект:: интерсектрект](#intersectrect).

##  <a name="operator_or_eq"></a>Крект:: operator &#124;=

Задает `CRect` равное объединению `CRect` и `rect`.

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Содержит `CRect` или [Rect](/windows/win32/api/windef/ns-windef-rect).

### <a name="remarks"></a>Remarks

Объединение — это самый маленький прямоугольник, содержащий оба исходных прямоугольника.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

##  <a name="operator_add"></a>Крект:: operator +

Первые две перегрузки возвращают объект `CRect`, который равен `CRect`, заданному указанными смещениями.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) , указывающий количество единиц для перемещения возвращаемого значения.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или объект [ксизе](csize-class.md) , указывающий количество единиц для перемещения возвращаемого значения.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, который содержит число единиц, которые нужно увеличить с каждой стороны возвращаемого значения.

### <a name="return-value"></a>Возвращаемое значение

`CRect`, полученный в результате перемещения или переноса `CRect` на число единиц, указанное в параметре.

### <a name="remarks"></a>Remarks

Параметры *x* и *y* (или `cx` и `cy`) добавляются к положению `CRect`.

Третья перегрузка возвращает новую `CRect`, которая равна `CRect`, с последующим числом единиц, указанным в каждом элементе параметра.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

##  <a name="operator_-"></a>Крект:: operator —

Первые две перегрузки возвращают объект `CRect`, который равен `CRect`, заданному указанными смещениями.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Структура [точки](/windows/win32/api/windef/ns-windef-point) или `CPoint` объект, указывающий количество единиц для перемещения возвращаемого значения.

*size*<br/>
Структура [размера](/windows/win32/api/windef/ns-windef-size) или `CSize` объект, указывающий количество единиц для перемещения возвращаемого значения.

*лпрект*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, который содержит число единиц, которые должны быть сведены по каждой стороне возвращаемого значения.

### <a name="return-value"></a>Возвращаемое значение

`CRect`, полученный в результате перемещения или деспрямления `CRect` на число единиц, указанное в параметре.

### <a name="remarks"></a>Remarks

Параметры *x* и *y* (или `cx` и `cy`) вычитаются из расположения `CRect`.

Третья перегрузка возвращает новый `CRect`, который равен `CRect` с последующим числом единиц, указанным в каждом элементе параметра. Обратите внимание, что эта перегрузка функции, например [дефлатерект](#deflaterect), не [субтрактрект](#subtractrect).

### <a name="example"></a>Пример

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

##  <a name="operator_amp"></a>Крект:: operator &amp;

Возвращает `CRect`, представляющий собой пересечение `CRect` и *rect2*.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Параметры

*rect2*<br/>
Содержит [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="return-value"></a>Возвращаемое значение

`CRect`, являющийся пересечением `CRect` и *rect2*.

### <a name="remarks"></a>Remarks

Пересечением является самый крупный прямоугольник, содержащийся в обоих прямоугольниках.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

##  <a name="operator_or"></a>Крект:: operator&#124;

Возвращает `CRect`, который является объединением `CRect` и *rect2*.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Параметры

*rect2*<br/>
Содержит [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`.

### <a name="return-value"></a>Возвращаемое значение

`CRect`, который является объединением `CRect` и *rect2*.

### <a name="remarks"></a>Remarks

Объединение — это наименьший прямоугольник, который содержит оба прямоугольника.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

##  <a name="ptinrect"></a>Крект::P Тинрект

Определяет, находится ли указанная точка в пределах `CRect`.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Параметры

*point*<br/>
Содержит структуру [точек](/windows/win32/api/windef/ns-windef-point) или объект [CPoint](cpoint-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если точка находится в пределах `CRect`; в противном случае — 0.

### <a name="remarks"></a>Remarks

Точка находится в пределах `CRect`, если она находится на левой или верхней стороне или находится внутри всех четырех сторон. Точка с правой или нижней стороны выходит за пределы `CRect`.

> [!NOTE]
>  Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

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

##  <a name="setrect"></a>Крект:: SetRect

Задает размеры `CRect` указанным координатам.

```
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>Параметры

*x1*<br/>
Задает координату по оси x верхнего левого угла.

*y1*<br/>
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

##  <a name="setrectempty"></a>Крект:: Сетректемпти

Делает `CRect` неопределенным прямоугольником, устанавливая все координаты равными нулю.

```
void SetRectEmpty() throw();
```

### <a name="example"></a>Пример

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

##  <a name="size"></a>Крект:: SIZE

Элементы `cx` и `cy` возвращаемого значения содержат высоту и ширину `CRect`.

```
CSize Size() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [ксизе](csize-class.md) , который содержит размер `CRect`.

### <a name="remarks"></a>Remarks

Либо высота, либо ширина могут быть отрицательными.

> [!NOTE]
>  Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

##  <a name="subtractrect"></a>Крект:: Субтрактрект

Делает измерения `CRect` равными вычитанию `lpRectSrc2` из `lpRectSrc1`.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Параметры

*lpRectSrc1*<br/>
Указывает на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect` объект, из которого будет вычитаться прямоугольник.

*lpRectSrc2*<br/>
Указывает на `RECT` структуру или `CRect` объект, вычитаемый из прямоугольника, на который указывает параметр *lpRectSrc1* .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Вычитание является наименьшим прямоугольником, содержащим все точки в *lpRectScr1* , которые не находятся в пересечении *lpRectScr1* и *lpRectScr2*.

Прямоугольник, заданный параметром *lpRectSrc1* , будет неизменным, если прямоугольник, заданный параметром *lpRectSrc2* , не полностью пересекается с прямоугольником, заданным параметром *lpRectSrc1* , по крайней мере в одном из направлений x или y.

Например, если *lpRectSrc1* были (10, 10, 100 100) и *lpRectSrc2* (50, 50, 150 150), то прямоугольник, на который указывает *lpRectSrc1* , будет неизменным при возвращении функции. Если *lpRectSrc1* были (10, 10, 100 100) и *lpRectSrc2* (50, 10, 150 150), то прямоугольник, на который указывает *lpRectSrc1* , будет содержать координаты (10, 10, 50 100) при возвращении функции.

`SubtractRect` не совпадает с [оператором operator-](#operator_-) and [-=](#operator_-_eq). Ни один из этих операторов не вызывает `SubtractRect`.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

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

##  <a name="topleft"></a>Крект:: Топлефт

Координаты возвращаются в виде ссылки на объект [CPoint](cpoint-class.md) , содержащийся в `CRect`.

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

##  <a name="unionrect"></a>Крект:: Унионрект

Делает измерения `CRect` равными объединению двух исходных прямоугольников.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Параметры

*lpRect1*<br/>
Указывает на [Rect](/windows/win32/api/windef/ns-windef-rect) или `CRect`, содержащий исходный прямоугольник.

*lpRect2*<br/>
Указывает на `RECT` или `CRect`, содержащий исходный прямоугольник.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объединение не пусто; 0, если объединение пусто.

### <a name="remarks"></a>Remarks

Объединение — это самый маленький прямоугольник, содержащий оба исходных прямоугольника.

Windows игнорирует размеры пустого прямоугольника; то есть прямоугольник, который не имеет высоты или не имеет ширины.

> [!NOTE]
>  Оба прямоугольника должны быть нормализованы, или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольников перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

##  <a name="width"></a>Крект:: Width

Вычисляет ширину `CRect` путем вычитания левого значения из правого значения.

```
int Width() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ширина `CRect`.

### <a name="remarks"></a>Remarks

Ширина может быть отрицательной.

> [!NOTE]
>  Прямоугольник должен быть нормализован или эта функция может завершиться ошибкой. Можно вызвать [нормализерект](#normalizerect) для нормализации прямоугольника перед вызовом этой функции.

### <a name="example"></a>Пример

```cpp
CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
// nWid is now 60
ASSERT(nWid == 60);
```

## <a name="see-also"></a>См. также раздел

[Класс CPoint](cpoint-class.md)<br/>
[Класс CSize](csize-class.md)<br/>
[ПЕРЕТАСКИВАЕМЫЕ](/windows/win32/api/windef/ns-windef-rect)
