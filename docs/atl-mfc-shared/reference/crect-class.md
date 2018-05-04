---
title: Класс CRect | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a819cfc95588dc9225570a82b8a359d90a8f6b9f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="crect-class"></a>CRect-класс
Аналогично Windows [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRect::CRect](#crect)|Создает объект `CRect`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRect::BottomRight](#bottomright)|Возвращает точку в правой нижней `CRect`.|  
|[CRect::CenterPoint](#centerpoint)|Возвращает centerpoint из `CRect`.|  
|[CRect::CopyRect](#copyrect)|Копирует размеры исходного прямоугольника в `CRect`.|  
|[CRect::DeflateRect](#deflaterect)|Уменьшение ширины и высоты `CRect`.|  
|[CRect::EqualRect](#equalrect)|Определяет, является ли `CRect` равен заданного прямоугольника.|  
|[CRect::Height](#height)|Вычисляет высоту `CRect`.|  
|[CRect::InflateRect](#inflaterect)|Увеличение ширины и высоты `CRect`.|  
|[CRect::IntersectRect](#intersectrect)|Наборы `CRect` равно пересечение двух прямоугольников.|  
|[CRect::IsRectEmpty](#isrectempty)|Определяет, является ли `CRect` пуст. `CRect` пусто, если ширина или высота равна 0.|  
|[CRect::IsRectNull](#isrectnull)|Определяет ли **верхней**, **нижней**, **левой**, и **правой** переменных-членов, все равно 0.|  
|[CRect::MoveToX](#movetox)|Перемещает `CRect` на указанной оси x.|  
|[CRect::MoveToXY](#movetoxy)|Перемещает `CRect` для указанной координаты x и y-.|  
|[CRect::MoveToY](#movetoy)|Перемещает `CRect` для указанного координату по оси y.|  
|[CRect::NormalizeRect](#normalizerect)|Стандартизирует высоту и ширину `CRect`.|  
|[CRect::OffsetRect](#offsetrect)|Перемещает `CRect` с заданными смещениями.|  
|[CRect::PtInRect](#ptinrect)|Определяет, находится ли заданная точка в пределах `CRect`.|  
|[CRect::SetRect](#setrect)|Задает размеры `CRect`.|  
|[CRect::SetRectEmpty](#setrectempty)|Наборы `CRect` для пустой прямоугольник (все координаты, равные 0).|  
|[CRect::Size](#size)|Вычисляет размер `CRect`.|  
|[CRect::SubtractRect](#subtractrect)|Вычитает один прямоугольник из другого.|  
|[CRect::TopLeft](#topleft)|Возвращает точку в левом верхнем `CRect`.|  
|[CRect::UnionRect](#unionrect)|Наборы `CRect` равно объединением двух прямоугольников.|  
|[CRect::Width](#width)|Вычисляет ширину `CRect`.|  
  
### <a name="public-operators"></a>Открытые операторы    
|Имя|Описание|  
|----------|-----------------|  
|[CRect::operator-](#operator_-)|Вычитает заданного смещения из `CRect` или уменьшение объема `CRect` и возвращает итоговое `CRect`.|  
|[LPCRECT CRect::operator](#operator_lpcrect)|Преобразует `CRect` для **LPCRECT**.|  
|[CRect::operator LPRECT](#operator_lprect)|Преобразует `CRect` в `LPRECT`.|  
|[CRect::operator! =](#operator_neq)|Определяет, является ли `CRect` не равно прямоугольник.|  
|[CRect::operator &amp;](#operator_amp)|Создает пересечение `CRect` и прямоугольник и возвращает итоговое `CRect`.|  
|[CRect::operator &amp;=](#operator_amp_eq)|Наборы `CRect` равно пересечение `CRect` и прямоугольник.|  
|[CRect::operator |](#operator_or)|Создает объединение `CRect` и прямоугольник и возвращает итоговое `CRect`.|  
|[CRect::operator |=](#operator_or_eq)|Наборы `CRect` равно объединение `CRect` и прямоугольник.|  
|[CRect::operator +](#operator_add)|Добавление заданного смещения к `CRect` или увеличивает `CRect` и возвращает итоговое `CRect`.|  
|[CRect::operator +=](#operator_add_eq)|Добавляет указанного смещения до `CRect` или увеличивает `CRect`.|  
|[CRect::operator =](#operator_eq)|Копирует размеры прямоугольника для `CRect`.|  
|[CRect::operator-=](#operator_-_eq)|Вычитает из указанного смещения `CRect` или уменьшение объема `CRect`.|  
|[CRect::operator ==](#operator_eq_eq)|Определяет, является ли `CRect` равен прямоугольник.|  
  
## <a name="remarks"></a>Примечания  
 `CRect` также включает функции-члены для управления `CRect` объектов и Windows `RECT` структуры.  
  
 Объект `CRect` можно передавать в качестве параметра функции везде, где `RECT` структуры **LPCRECT**, или `LPRECT` могут быть переданы.  
  
> [!NOTE]
>  Этот класс является производным от **tagRECT** структуры. (Имя **tagRECT** — это имя менее часто используемых для `RECT` структуры.) Это означает, что данные-члены (**левой**, **верхней**, **правой**, и **нижней**) из `RECT` структуры, доступные данные члены `CRect`.  
  
 Объект `CRect` содержит переменные-члены, определяющих точки верхним левым и нижним правым прямоугольника.  
  
 При указании `CRect`, будьте внимательны, чтобы создать его, чтобы он нормализован — другими словами, таким образом, что значение левой координаты меньше, чем вправо и верхней меньше нижней. Например верхнего левого угла (10,10) и нижней правой части (20,20) определяет нормализованным прямоугольником, но верхнего левого угла (20,20) и нижней правой части (10,10) определяет ненормализованной прямоугольник. Если прямоугольник не нормализовано, многие `CRect` функции-члены могут возвращать неверные результаты. (См. [CRect::NormalizeRect](#normalizerect) список этих функций.) Перед вызовом функции, требующей нормализованный прямоугольники, вы можете нормализовать ненормализованной прямоугольники, вызвав `NormalizeRect` функции.  
  
 Соблюдайте осторожность при обработке `CRect` с [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) и [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) функции-члены. Если режим сопоставления контекста отображения является таким образом, что в степени y является отрицательным, как и в `MM_LOENGLISH`, затем `CDC::DPtoLP` приведет к преобразованию `CRect` таким образом, чтобы его верхней больше нижней. Функции, такие как **высота** и **размер** будет возвращать отрицательные значения для данной высоты преобразованного `CRect`, и прямоугольника будет ненормализованной.  

  
 Когда с помощью перегруженных `CRect` операторы, первый операнд должен быть `CRect`; второй может быть либо [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` объекта.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltypes.h  
  
##  <a name="bottomright"></a>  CRect::BottomRight  
 Координаты возвращаются как ссылка на [CPoint](cpoint-class.md) объект, который содержится в `CRect`.  
  
```  
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Координаты нижнего правого угла прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно использовать, чтобы получить или задать нижнего правого угла прямоугольника. Задайте угол с помощью этой функции с левой стороны оператора присваивания.  
  
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
  
##  <a name="centerpoint"></a>  CRect::CenterPoint 
 Вычисляет centerpoint из `CRect` добавив значения влево и вправо и деления на 2 и значения верхней и нижней и деления на два.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CPoint` объект, являющийся centerpoint из `CRect`.  
  
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
  
##  <a name="copyrect"></a>  CRect::CopyRect  
 Копирует `lpSrcRect` прямоугольника в `CRect`.  
  
```  
void CopyRect(LPCRECT lpSrcRect) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `lpSrcRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` объект, который требуется скопировать.  
  
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

  
##  <a name="crect"></a>  CRect::CRect  
 Создает объект `CRect`.  
  
```  
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *l*  
 Указывает положение слева для `CRect`.  
  
 *t*  
 Указывает вверху `CRect`.  
  
 *r*  
 Указывает правой позиции `CRect`.  
  
 *b*  
 Указывает, в нижней части `CRect`.  
  
 *srcRect*  
 Ссылается на [RECT](../../mfc/reference/rect-structure1.md) структуру с координатами для `CRect`.  
  
 `lpSrcRect`  
 Указывает на `RECT` структуру с координатами для `CRect`.  
  
 `point`  
 Задает исходную точку для прямоугольника создаваться. Соответствует верхнего левого угла.  
  
 `size`  
 Указывает смещение от верхнего левого угла в нижний правый угол прямоугольника создаваться.  
  
 *TopLeft*  
 Задает позицию верхнего левого края `CRect`.  
  
 *bottomRight*  
 Задает положение нижней `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Если аргументы не указаны, **левой**, **верхней**, **правой**, и **нижней** члены не инициализированы.  
  
 `CRect`(**Const RECT &**) и `CRect`(**LPCRECT**) конструкторы выполняют [CopyRect](#copyrect). Другие конструкторы непосредственно инициализации переменных-членов объекта.  
  
### <a name="example"></a>Пример  
```cpp  
 // default constructor doesn't initialize!
 CRect rectUnknown;

 // four-integers are left, top, right, and bottom
 CRect rect(0, 0, 100, 50);
 ASSERT(rect.Width() == 100);
 ASSERT(rect.Height() == 50);

 // Initialize from RECT stucture
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
  
##  <a name="deflaterect"></a>  CRect::DeflateRect  
 `DeflateRect` Уменьшение объема `CRect` , перемещая его стороны к ее центру.  
  
```  
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Указывает число единиц deflate слева и справа от `CRect`.  
  
 *y*  
 Указывает число единиц deflate верхней и нижней части `CRect`.  
  
 `size`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) или [CSize](csize-class.md) , указывающее количество единиц, deflate `CRect`. `cx` Значение указывает число единиц deflate левую и правую части и `cy` значение указывает число единиц deflate сверху и снизу.  
  
 `lpRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` , указывающее количество единиц для каждой стороны deflate.  
  
 *l*  
 Указывает число единиц deflate в левой части `CRect`.  
  
 *t*  
 Указывает число единиц deflate вверху `CRect`.  
  
 *r*  
 Указывает число единиц deflate в правой части `CRect`.  
  
 *b*  
 Указывает число единиц deflate в нижней части `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы сделать это, `DeflateRect` добавляет единицы left и top и вычитает устройств из справа и снизу. Параметры `DeflateRect` подписываются значений; deflate положительные значения `CRect` и отрицательные значения увеличению его.  
  
 Первые две перегрузки deflate нескольких пар разные стороны `CRect` , чтобы его общая ширина уменьшается в два раза *x* (или `cx`) и его Общая высота уменьшается в два раза *y* () или `cy`). Другие перегрузки deflate каждой стороне `CRect` независимо от других.  
  
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
  
##  <a name="equalrect"></a>  CRect::EqualRect  
 Определяет, является ли `CRect` равен заданного прямоугольника.  
  
```  
BOOL EqualRect(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` объект, содержащий координаты левого верхнего и нижнего правого угла прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если у двух прямоугольников же верхней, левую, нижнюю и правильные значения; в противном случае — 0.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
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

##  <a name="height"></a>  CRect::Height  
 Вычисляет высоту `CRect` путем вычитания верхнее значение из минимальное значение.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Полученное значение может быть отрицательным.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольника перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(20, 30, 80, 70);
 int nHt = rect.Height();

```cpp  
   CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

   // nHt is now 40
   ASSERT(nHt == 40);   
```

  
##  <a name="inflaterect"></a>  CRect::InflateRect  
 `InflateRect` увеличивает `CRect` , перемещая его стороны от ее центра.  
  
```  
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Указывает число единиц, на которую требуется увеличить слева и справа от `CRect`.  
  
 *y*  
 Указывает число единиц, на которую требуется увеличить верхней и нижней части `CRect`.  
  
 `size`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) или [CSize](csize-class.md) , указывающее количество единиц, на которую требуется увеличить `CRect`. `cx` Значение указывает число единиц, на которую требуется увеличить левую и правую части и `cy` значение указывает число единиц, на которую требуется увеличить сверху и снизу.  
  
 `lpRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` , указывающее количество единиц, на которую требуется увеличить каждой стороны.  
  
 *l*  
 Указывает число единиц, на которую требуется увеличить в левой части `CRect`.  
  
 *t*  
 Указывает число единиц, на которую требуется увеличить вверху `CRect`.  
  
 *r*  
 Указывает число единиц, на которую требуется увеличить в правой части `CRect`.  
  
 *b*  
 Указывает число единиц, на которую требуется увеличить в нижней части `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы сделать это, `InflateRect` вычитает устройств из левой и в верхней и добавляет единицы справа и снизу. Параметры `InflateRect` подписываются значений; положительные значения, которую требуется увеличить `CRect` и отрицательные значения deflate его.  
  
 Первые две перегруженные версии, которую требуется увеличить нескольких пар разные стороны `CRect` , чтобы его общая ширина увеличивается в два раза *x* (или `cx`) и его Общая высота увеличивается в два раза *y* () или `cy`). Две перегрузки, которую требуется увеличить каждой стороне `CRect` независимо от других.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(0, 0, 300, 300);
 rect.InflateRect(50, 200);

 // rect is now (-50, -200, 350, 500)
 ASSERT(rect == CRect(-50, -200, 350, 500));  
```
  
##  <a name="intersectrect"></a>  CRect::IntersectRect  
 Делает `CRect` равно пересечение двух прямоугольников существующий.  
  
```  
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect1`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` объект, содержащий исходного прямоугольника.  
  
 `lpRect2`  
 Указывает на `RECT` структуры или `CRect` объект, содержащий исходного прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пересечение не пуста; 0, если пересечение является пустым.  
  
### <a name="remarks"></a>Примечания  
 Пересечение является самый большой прямоугольник, содержащихся в обоих существующих прямоугольников.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rectOne(125, 0, 150, 200);
 CRect rectTwo(0, 75, 350,  95);
 CRect rectInter;

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
  
##  <a name="isrectempty"></a>  CRect::IsRectEmpty  
 Определяет, является ли `CRect` пуст.  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CRect` пуст; 0 Если `CRect` не является пустым.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник является пустым, если ширина или высота равны 0 или отрицательным. Отличается от `IsRectNull`, который определяет, являются ли все координаты прямоугольника ноль.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольника перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());   
```

  
##  <a name="isrectnull"></a>  CRect::IsRectNull  
 Определяет, является ли слева, сверху вниз и правой значения `CRect` , все равно 0.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CRect`вниз в верхнем, левом и правом значения все равно нулю; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Отличается от `IsRectEmpty`, которое определяет, пуст ли прямоугольник.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
 // note that null means _all_ zeros

 CRect rectNotNull(0, 0, 35, 50);
 ASSERT(!rectNotNull.IsRectNull());  
```
  
##  <a name="movetox"></a>  CRect::MoveToX  
 Вызывайте эту функцию, чтобы переместить прямоугольник в абсолютные координаты x, заданные *x*.  
  
```  
void MoveToX(int x) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Абсолютные координаты x верхнего левого угла прямоугольника.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToX(10);

```cpp  
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));   
```
  
##  <a name="movetoxy"></a>  CRect::MoveToXY  
 Вызывайте эту функцию, чтобы переместить прямоугольник в абсолютные координаты x и y-указан.  
  
```  
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Абсолютные координаты x верхнего левого угла прямоугольника.  
  
 *y*  
 Абсолютный Координата y верхнего левого угла прямоугольника.  
  
 `point`  
 Объект **ТОЧКИ** структуры, указав абсолютный верхнего левого угла прямоугольника.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToXY(10, 10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));   
```

  
##  <a name="movetoy"></a>  CRect::MoveToY  
 Вызывайте эту функцию, чтобы переместить прямоугольник абсолютный координату по оси y, заданные *y*.  
  
```  
void MoveToY(int y) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *y*  
 Абсолютный Координата y верхнего левого угла прямоугольника.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToY(10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));   
```

  
##  <a name="normalizerect"></a>  CRect::NormalizeRect  
 Нормализует `CRect` таким образом, высоту и ширину положительным.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник нормализуется для позиционирования четвертый квадрант, которой обычно используется Windows для координат. `NormalizeRect` Сравнивает значения верхней и нижней и меняет местами, если верхней больше нижней. Аналогичным образом меняет значения влево и вправо, если слева больше, чем вправо. Эта функция используется при работе с режимами другого сопоставления и инвертированный прямоугольники.  
  
> [!NOTE]
>  Следующие `CRect` функции-члены требуют нормализованный прямоугольники для правильной работы: [высота](#height), [ширина](#width), [размер](#size), [ IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [ SubtractRect](#subtractrect), [оператор ==](#operator_eq_eq), [оператор! =](#operator_neq), [оператор &#124; ](#operator_or), [оператор &#124;=](#operator_or_eq), [оператор &](#operator_amp), и [оператор & =](#operator_amp_eq).  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect1(110, 100, 250, 310);
 CRect rect2(250, 310, 110, 100);

```cpp  
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
   rect2.NormalizeRect();
 ASSERT(rect1 == rect2);  
```
  
##  <a name="offsetrect"></a>  CRect::OffsetRect  
 Перемещает `CRect` с заданными смещениями.  
  
```  
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Задает для перемещения влево или вправо. Оно должно быть отрицательным для перемещения влево.  
  
 *y*  
 Задает для перемещения вверх или вниз. Оно должно быть отрицательным для перемещения вверх.  
  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](cpoint-class.md) объект, указывающий как измерения, которое необходимо переместить.  
  
 `size`  
 Содержит [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](csize-class.md) объект, указывающий как измерения, которое необходимо переместить.  
  
### <a name="remarks"></a>Примечания  
 Перемещает `CRect` *x* единиц вдоль оси x и *y* единицы по оси y. *x* и *y* параметры являются значения со знаком, поэтому `CRect` могут перемещаться влево или вправо и вверх или вниз.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(0, 0, 35, 35);
 rect.OffsetRect(230, 230);

```cpp  
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));   
```

  
##  <a name="operator_lpcrect"></a>  Преобразует LPCRECT CRect::operator `CRect` для [LPCRECT](../../mfc/reference/data-types-mfc.md).  

  
```  
operator LPCRECT() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 При использовании этой функции не требуется взятия адреса (**&**) оператор. Этот оператор будет автоматически использоваться при передаче `CRect` в функцию, ожидающую **LPCRECT**.  
  

##  <a name="operator_lprect"></a>  CRect::operator LPRECT  
 Преобразует `CRect` для [LPRECT](../../mfc/reference/data-types-mfc.md).  

  
```
operator LPRECT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 При использовании этой функции не требуется взятия адреса (**&**) оператор. Этот оператор будет автоматически использоваться при передаче `CRect` в функцию, ожидающую `LPRECT`.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CRect::operator LPCRECT](#operator_lpcrect).  
  
##  <a name="operator_eq"></a>  CRect::operator =  
 Назначает *srcRect* для `CRect`.  
  
```  
void operator=(const RECT& srcRect) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *srcRect*  
 Ссылается на исходного прямоугольника. Может быть [RECT](../../mfc/reference/rect-structure1.md) или `CRect`.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(0, 0, 127, 168);
 CRect rect2;

```cpp  
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));   
```

  
##  <a name="operator_eq_eq"></a>  CRect::operator ==  
 Определяет, является ли `rect` равен `CRect` , сравнивая координаты их левого верхнего и нижнего правого угла.  
  
```  
BOOL operator==(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылается на исходного прямоугольника. Может быть [RECT](../../mfc/reference/rect-structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объекты равны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

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

  
##  <a name="operator_neq"></a>  CRect::operator! =  
 Определяет, является ли `rect` не равен `CRect` , сравнивая координаты их левого верхнего и нижнего правого угла.  
  
```  
BOOL operator!=(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылается на исходного прямоугольника. Может быть [RECT](../../mfc/reference/rect-structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объекты не равны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 != rect3);
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect3 != test);  
```
  
##  <a name="operator_add_eq"></a>  CRect::operator +=  
 Первые две перегрузки переместить `CRect` с заданными смещениями.  
  
```  
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Объект [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](cpoint-class.md) объекта, указывающее количество единиц для перемещения прямоугольника.  
  
 `size`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](csize-class.md) , указывающий количество единиц, чтобы переместить прямоугольник.  
  
 `lpRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` , содержащий число единиц, на которую требуется увеличить каждой стороне `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) значения добавляются к `CRect`.  
  
 Увеличивает третьей перегрузке `CRect` на число единиц, заданных в каждый член параметра.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 CRect rect2(135, 300, 235, 400);

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);   
```
  
##  <a name="operator_-_eq"></a>  CRect::operator-=  
 Первые две перегрузки переместить `CRect` с заданными смещениями.  
  
```  
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Объект [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](cpoint-class.md) объекта, указывающее количество единиц для перемещения прямоугольника.  
  
 `size`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](csize-class.md) , указывающий количество единиц, чтобы переместить прямоугольник.  
  
 `lpRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` , содержащий число единиц для каждой стороны deflate `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) вычитается из значения `CRect`.  
  
 Уменьшение объема третьей перегрузке `CRect` на число единиц, заданных в каждый член параметра. Обратите внимание, что эта перегрузка функции например [DeflateRect](#deflaterect).  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 rect1 -= pt;

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);   
```
  
##  <a name="operator_amp_eq"></a>  CRect::operator &amp;=  
 Наборы `CRect` равно пересечение `CRect` и `rect`.  
  
```  
void operator&=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Содержит [RECT](../../mfc/reference/rect-structure1.md) или `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Пересечение является самый большой прямоугольник, содержащаяся в оба прямоугольника.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CRect::IntersectRect](#intersectrect).  
  
##  <a name="operator_or_eq"></a>  CRect::operator &#124;=  
 Наборы `CRect` равно объединение `CRect` и `rect`.  
  
```  
void operator|=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Содержит `CRect` или [RECT](../../mfc/reference/rect-structure1.md).  
  
### <a name="remarks"></a>Примечания  
 Объединение является наименьший прямоугольник, содержащий оба исходного прямоугольника.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 rect1 |= rect2;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);   
```

  
##  <a name="operator_add"></a>  CRect::operator +  
 Первые две перегрузки возвращают `CRect` объекта, равное `CRect` смещаются с заданными смещениями.  
  
```  
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Объект [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](cpoint-class.md) объекта, указывающее количество единиц для перемещения возвращаемое значение.  
  
 `size`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](csize-class.md) объекта, указывающее количество единиц для перемещения возвращаемое значение.  
  
 `lpRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` объект, содержащий число единиц, на которую требуется увеличить каждой стороны возвращаемого значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CRect` Возникающие в результате перемещения или дало бы ошибку `CRect` число единиц, указанный в параметре.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) параметры добавляются `CRect`по позиции.  
  
 Возвращает новый третьей перегрузке `CRect` , равное `CRect` увеличивается за счет число единиц, заданных в каждый член параметра.  
  
### <a name="example"></a>Пример  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);   
```

  
##  <a name="operator_-"></a>  CRect::operator-  
 Первые две перегрузки возвращают `CRect` объекта, равное `CRect` смещаются с заданными смещениями.  
  
```  
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Объект [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или `CPoint` объекта, указывающее количество единиц для перемещения возвращаемое значение.  
  
 `size`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или `CSize` объекта, указывающее количество единиц для перемещения возвращаемое значение.  
  
 `lpRect`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` объект, содержащий число единиц deflate каждой стороны возвращаемого значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CRect` Возникающие в результате перемещения или сократятся `CRect` число единиц, указанный в параметре.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) параметры вычитаются из `CRect`по позиции.  
  
 Возвращает новый третьей перегрузке `CRect` , равное `CRect` уменьшения на число единиц, заданных в каждый член параметра. Обратите внимание, что эта перегрузка функции например [DeflateRect](#deflaterect), а не [SubtractRect](#subtractrect).  
  
### <a name="example"></a>Пример  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);   
```

  
##  <a name="operator_amp"></a>  CRect::operator &amp;  
 Возвращает `CRect` , пересечение `CRect` и *rect2*.  
  
```  
CRect operator&(const RECT& rect2) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *rect2*  
 Содержит [RECT](../../mfc/reference/rect-structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , пересечение `CRect` и *rect2*.  
  
### <a name="remarks"></a>Примечания  
 Пересечение является самый большой прямоугольник, содержащаяся в оба прямоугольника.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="operator_or"></a>  CRect::operator&#124;  
 Возвращает `CRect` , представляющее собой объединение `CRect` и *rect2*.  
  
```   
CRect operator|(const RECT& 
rect2) const throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 *rect2*  
 Содержит [RECT](../../mfc/reference/rect-structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , представляющее собой объединение `CRect` и *rect2*.  
  
### <a name="remarks"></a>Примечания  
 Объединение является наименьший прямоугольник, содержащий оба прямоугольника.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 CRect rect3;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="ptinrect"></a>  CRect::PtInRect  
 Определяет, находится ли заданная точка в пределах `CRect`.  
  
```   
BOOL PtInRect(POINT point) const throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](cpoint-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эта точка находится в пределах `CRect`; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Точка находится в пределах `CRect` если он находится на левой или верхней стороны или находится в пределах всех четырех сторон. Точка на стороне правому или нижнему находится вне `CRect`.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольника перед вызовом этой функции.  
  
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
  
##  <a name="setrect"></a>  CRect::SetRect  
 Задает размеры `CRect` в указанные координаты.  
  
```   
void SetRect(int x1, int y1, int x2, int y2) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `x1`  
 Указывает Координата по оси x верхнего левого угла.  
  
 `y1`  
 Задает координату y верхнего левого угла.  
  
 `x2`  
 Указывает Координата по оси x нижнего правого угла.  
  
 `y2`  
 Указывает Координата по оси y нижнего правого угла.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect;
 rect.SetRect(256, 256, 512, 512);

```cpp  
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));   
```

  
##  <a name="setrectempty"></a>  CRect::SetRectEmpty  
 Делает `CRect` прямоугольник, установив все координаты нулевое значение null.  
  
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
  
##  <a name="size"></a>  CRect::SIZE 
 `cx` И `cy` содержат члены возвращаемого значения высоты и ширины `CRect`.  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](csize-class.md) , содержащий размер `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Высота или ширина может быть отрицательным.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольника перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
 CRect rect(10, 10, 50, 50);
 CSize sz = rect.Size();
 ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="subtractrect"></a>  CRect::SubtractRect  
 Делает размеры **CRect** равно вычитании смещения `lpRectSrc2` из `lpRectSrc1`.  
  
```  
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpRectSrc1`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) структуры или `CRect` объект, из которого вычитается прямоугольник.  
  
 `lpRectSrc2`  
 Указывает на `RECT` структуры или `CRect` объект, удаляемый из прямоугольника, на который указывает `lpRectSrc1` параметра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вычитания имеет наименьший прямоугольник, содержащий все точки в `lpRectScr1` , не входящих в пересечении `lpRectScr1` и *lpRectScr2*.  
  
 Прямоугольник, задаваемый параметром `lpRectSrc1` останутся без изменений, если прямоугольник, задаваемый параметром `lpRectSrc2` не полностью перекрывать прямоугольник, задаваемый параметром *lpRectSrc1* по крайней мере одним из x или y направлениях.  
  
 Например если `lpRectSrc1` были (10,10, 100,100) и `lpRectSrc2` были (50,50, 150,150) прямоугольника, на который указывает `lpRectSrc1` бы без изменений при возврате функции. Если `lpRectSrc1` были (10,10, 100,100) и `lpRectSrc2` были (50,10, 150,150), однако прямоугольника, на который указывает `lpRectSrc1` будет содержать координаты (10,10, 50,100) при возврате функции.  
  
 `SubtractRect` не является таким же, как [оператор -](#operator_-) , ни [оператор-=](#operator_-_eq). Ни один из этих операторов никогда не вызывает `SubtractRect`.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
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
  
##  <a name="topleft"></a>  CRect::TopLeft  
 Координаты возвращаются как ссылка на [CPoint](cpoint-class.md) объект, который содержится в `CRect`.  
  
```  
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Координаты левого верхнего угла прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно использовать, чтобы получить или задать верхнего левого угла прямоугольника. Задайте угол с помощью этой функции с левой стороны оператора присваивания.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CRect::CenterPoint](#centerpoint).  
  
##  <a name="unionrect"></a>  CRect::UnionRect  
 Делает размеры `CRect` равно объединение двух исходных прямоугольники.  
  
```  
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect1`  
 Указывает на [RECT](../../mfc/reference/rect-structure1.md) или `CRect` , содержащий исходного прямоугольника.  
  
 `lpRect2`  
 Указывает на `RECT` или `CRect` , содержащий исходного прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объединение не пуста; 0, если объединение является пустым.  
  
### <a name="remarks"></a>Примечания  
 Объединение является наименьший прямоугольник, содержащий оба исходного прямоугольника.  
  
 Windows будет игнорировать размеры пустой прямоугольник; то есть, прямоугольник, который содержит не высота или ширина не.  
  
> [!NOTE]
>  Оба прямоугольника должны быть нормализованы или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольники перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```
 
##  <a name="width"></a>  CRect::Width  
 Вычисляет ширину `CRect` путем вычитания значение слева от правильного значения.  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Ширина может быть отрицательным.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#normalizerect) нормализовать прямоугольника перед вызовом этой функции.  
  
### <a name="example"></a>Пример  

```cpp  
   CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);   
```
## <a name="see-also"></a>См. также  
 [Класс CPoint](cpoint-class.md)   
 [Класс CSize](csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)


