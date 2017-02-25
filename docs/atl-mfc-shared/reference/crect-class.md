---
title: "Класс CRect | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRect"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPCRECT - тип данных"
  - "Класс CRect"
  - "LPRECT-оператор"
  - "RECT - структура"
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# Класс CRect
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Аналогично Windows [RECT](RECT%20Structure1.md) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRect::CRect](#crect__crect)|Создает объект `CRect`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRect::BottomRight](#crect__bottomright)|Возвращает точку справа внизу `CRect`.|  
|[CRect::CenterPoint](#crect__centerpoint)|Возвращает centerpoint из `CRect`.|  
|[CRect::CopyRect](#crect__copyrect)|Копирует размеры исходного прямоугольника в `CRect`.|  
|[CRect::DeflateRect](#crect__deflaterect)|Уменьшение ширины и высоты `CRect`.|  
|[CRect::EqualRect](#crect__equalrect)|Определяет, является ли `CRect` равен данного прямоугольника.|  
|[CRect::Height](#crect__height)|Вычисляет высоту `CRect`.|  
|[CRect::InflateRect](#crect__inflaterect)|Увеличение ширины и высоты `CRect`.|  
|[CRect::IntersectRect](#crect__intersectrect)|Наборы `CRect` равно пересечение двух прямоугольников.|  
|[CRect::IsRectEmpty](#crect__isrectempty)|Определяет, является ли `CRect` пуст. `CRect` пусто, если ширина или высота равна 0.|  
|[CRect::IsRectNull](#crect__isrectnull)|Определяет ли **Начало**, **нижней**, **левой**, и **правом** переменных-членов, все равно 0.|  
|[CRect::MoveToX](#crect__movetox)|Перемещает `CRect` к указанным координатам x.|  
|[CRect::MoveToXY](#crect__movetoxy)|Перемещает `CRect` для указанного x и y координаты.|  
|[CRect::MoveToY](#crect__movetoy)|Перемещает `CRect` для указанного координату по оси y.|  
|[CRect::NormalizeRect](#crect__normalizerect)|Стандартизирует высоту и ширину `CRect`.|  
|[CRect::OffsetRect](#crect__offsetrect)|Перемещает `CRect` с заданными смещениями.|  
|[CRect::PtInRect](#crect__ptinrect)|Определяет, находится ли указанная точка в пределах `CRect`.|  
|[CRect::SetRect](#crect__setrect)|Задает размеры `CRect`.|  
|[CRect::SetRectEmpty](#crect__setrectempty)|Наборы `CRect` для пустой прямоугольник (все координаты равны 0).|  
|[CRect::Size](#crect__size)|Вычисляет размер `CRect`.|  
|[CRect::SubtractRect](#crect__subtractrect)|Вычитает один прямоугольник из другого.|  
|[CRect::TopLeft](#crect__topleft)|Возвращает точку верхнего левого `CRect`.|  
|[CRect::UnionRect](#crect__unionrect)|Наборы `CRect` равно объединением двух прямоугольников.|  
|[CRect::Width](#crect__width)|Вычисляет ширину `CRect`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRect::operator-](#crect__operator_-)|Вычитание заданного смещения из `CRect` или сжимает `CRect` и возвращает полученный в результате `CRect`.|  
|[CRect::operator LPCRECT](#crect__operator_lpcrect)|Преобразует `CRect` для **LPCRECT**.|  
|[CRect::operator LPRECT](#crect__operator_lprect)|Преобразует `CRect` для `LPRECT`.|  
|[CRect::operator! =](#crect__operator__neq)|Определяет, является ли `CRect` не равен прямоугольника.|  
|[CRect::operator &amp;](#crect__operator__amp_)|Создает пересечение `CRect` и прямоугольник и возвращает полученный в результате `CRect`.|  
|[CRect::operator &amp;=](#crect__operator__amp__eq)|Наборы `CRect` равно пересечение `CRect` и прямоугольник.|  
|[CRect::operator |](#crect__operator__or)|Создает объединение `CRect` и прямоугольник и возвращает полученный в результате `CRect`.|  
|[CRect::operator |=](#crect__operator__or_eq)|Наборы `CRect` равно объединение `CRect` и прямоугольник.|  
|[CRect::operator +](#crect__operator__add)|Добавление заданного смещения в `CRect` или увеличивает `CRect` и возвращает полученный в результате `CRect`.|  
|[CRect::operator +=](#crect__operator__add_eq)|Добавляет указанного смещения до `CRect` или увеличивает `CRect`.|  
|[CRect::operator =](#crect__operator__eq)|Копирует с размерами прямоугольника в `CRect`.|  
|[CRect::operator-=](#crect__operator_-_eq)|Вычитание заданного смещения из `CRect` или сжимает `CRect`.|  
|[CRect::operator ==](#crect__operator__eq_eq)|Определяет, является ли `CRect` равен прямоугольника.|  
  
## <a name="remarks"></a>Примечания  
 `CRect` также включает функции-члены для управления `CRect` объекты и Windows `RECT` структуры.  
  
 Объект `CRect` объект может передаваться как параметр функции везде, где `RECT` структуры, **LPCRECT**, или `LPRECT` могут передаваться.  
  
> [!NOTE]
>  Этот класс является производным от **tagRECT** структуры. (Имя **tagRECT** — это имя менее часто используемых для `RECT` структуры.) Это означает, что данные-члены ( **левой**, **Начало**, **справа**, и **нижней**) из `RECT` структуры являются членами доступные данные `CRect`.  
  
 Объект `CRect` содержит переменные, определяющих левый верхний и нижний правый точки прямоугольника.  
  
 При указании `CRect`, будьте внимательны, чтобы создать его, чтобы он нормализован — другими словами, таким образом, что значение левая координата меньше, чем правой и верхней меньше нижней. Например верхнем левом углу (10,10) и нижней правой части (20,20) определяет нормализованным прямоугольником, но верхнем левом углу (20,20) и нижней правой части (10,10) определяет ненормализованной прямоугольник. Если прямоугольник не нормализовано, многие `CRect` функции-члены могут возвращать неверные результаты. (См. [CRect::NormalizeRect](#crect__normalizerect) список этих функций.) Перед вызовом функции, требующей нормализованных прямоугольники, вы можете нормализовать ненормализованной прямоугольники путем вызова `NormalizeRect` функции.  
  
 Будьте осторожны при обработке `CRect` с [CDC::DPtoLP] (.. /Topic/CDC%20Class.md#cdc__dptolp и [CDC::LPtoDP] (.. Функции-члены /topic/CDC%20Class.md#cdc__lptodp. Если режим сопоставления контекста отображения — таким образом, что область y является отрицательным, как в `MM_LOENGLISH`, затем `CDC::DPtoLP` приведет к преобразованию `CRect` таким образом, чтобы его свойство top больше нижней. Функции, такие как **Высота** и **размер** будет возвращать отрицательные значения высоты преобразованного `CRect`, а прямоугольник будет ненормализованной.  
  
 Если с помощью перегруженных `CRect` операторы, первый операнд должен иметь `CRect`; второй может быть либо [RECT](RECT%20Structure1.md) структуры или `CRect` объекта.  
  
> [!NOTE]
>  Дополнительные сведения об общих служебные классы (как `CRect`), в разделе [совместно используемые классы](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltypes.h  
  
##  <a name="a-namecrectbottomrighta-crectbottomright"></a><a name="crect__bottomright"></a>  CRect::BottomRight  
 Координаты возвращаются как ссылка на [CPoint](../Topic/CPoint%20Class.md) объект, содержащийся в `CRect`.  
  
```  
 
CPoint& BottomRight() throw();

const CPoint& BottomRight() const throw();

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Координаты нижнего правого угла прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно использовать, чтобы получить или задать нижнего правого угла прямоугольника. Задайте угол с помощью этой функции в левой части оператора присваивания.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#35](../../atl-mfc-shared/codesnippet/CPP/crect-class_1.cpp)]  
  
##  <a name="a-namecrectcenterpointa-crectcenterpoint"></a><a name="crect__centerpoint"></a>  CRect::CenterPoint  
 Вычисляет centerpoint из `CRect` путем добавления значений левого и правого и деления двух и добавления максимальные и минимальные значения и деления двух.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CPoint` объект, являющийся centerpoint из `CRect`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#36](../../atl-mfc-shared/codesnippet/CPP/crect-class_2.cpp)]  
  
##  <a name="a-namecrectcopyrecta-crectcopyrect"></a><a name="crect__copyrect"></a>  CRect::CopyRect  
 Копирует `lpSrcRect` прямоугольника в `CRect`.  
  
```  
 
void CopyRect(
LPCRECT   
lpSrcRect) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `lpSrcRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, который требуется скопировать.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#37](../../atl-mfc-shared/codesnippet/CPP/crect-class_3.cpp)]  
  
##  <a name="a-namecrectcrecta-crectcrect"></a><a name="crect__crect"></a>  CRect::CRect  
 Создает объект `CRect`.  
  
```  
 
    CRect() throw();
CRect(
 int    
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();
CRect(
 const RECT& 
    srcRect) throw();
CRect(
 LPCRECT    
    lpSrcRect) throw();
CRect(
 POINT    
    point ,  
    SIZE 
    size) throw();
CRect(
 POINT    
    topLeft ,  
    POINT 
    bottomRight) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *l*  
 Указывает положение слева для `CRect`.  
  
 *t*  
 Указывает вверху `CRect`.  
  
 *r*  
 Определяет положение правой `CRect`.  
  
 *b*  
 Указывает, в нижней части `CRect`.  
  
 *srcRect*  
 Ссылается на [RECT](RECT%20Structure1.md) структуры с помощью координат `CRect`.  
  
 `lpSrcRect`  
 Указывает `RECT` структуры с помощью координат `CRect`.  
  
 `point`  
 Задает исходную точку для прямоугольника для отправки. Соответствует верхнему левому углу.  
  
 `size`  
 Указывает смещение от верхнего левого угла до правого нижнего угла прямоугольника для отправки.  
  
 *topLeft*  
 Задает позицию верхнего левого `CRect`.  
  
 *bottomRight*  
 Определяет положение нижней `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Если аргументы не указаны, **левой**, **Начало**, **правом**, и **нижней** члены не инициализируются.  
  
  `CRect`( **Const RECT &**) и `CRect`( **LPCRECT**) конструкторы выполняют [CopyRect](#crect__copyrect). Другие конструкторы инициализации переменных-членов объекта напрямую.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#38](../../atl-mfc-shared/codesnippet/CPP/crect-class_4.cpp)]  
  
##  <a name="a-namecrectdeflaterecta-crectdeflaterect"></a><a name="crect__deflaterect"></a>  CRect::DeflateRect  
 `DeflateRect` Уменьшение объема `CRect` путем продвижения к центру его сторон.  
  
```  
 
    void DeflateRect(
    int 
    x ,  
    int 
    y) throw();
void DeflateRect(
    SIZE 
    size) throw();
void DeflateRect(
    LPCRECT 
    lpRect) throw();
void DeflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Указывает число единиц deflate слева и справа от `CRect`.  
  
 *y*  
 Указывает число единиц deflate верхней и нижней части `CRect`.  
  
 `size`  
 A [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) или [CSize](../../atl-mfc-shared/reference/csize-class.md) указывающее количество единиц, deflate `CRect`.  `cx` Значение указывает количество единиц, deflate левую и правую части и `cy` значение указывает количество единиц, deflate сверху и снизу.  
  
 `lpRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` указывающее количество единиц, deflate каждой стороны.  
  
 *l*  
 Указывает количество единиц в левой части deflate `CRect`.  
  
 *t*  
 Указывает количество единиц в верхней части deflate `CRect`.  
  
 *r*  
 Указывает число единиц deflate справа от `CRect`.  
  
 *b*  
 Указывает число единиц deflate в нижней части `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы сделать это, `DeflateRect` добавляет единиц left и top и вычитает единиц вправо и вниз. Параметры `DeflateRect` подписываются значений; deflate положительные значения `CRect` и отрицательные значения увеличению его.  
  
 Первые две перегрузки deflate обе пары разные стороны `CRect` таким образом, чтобы его ширина уменьшается в два раза *x* (или `cx`) и его высота всего уменьшается в два раза *y* (или `cy`). Другие перегрузки deflate каждой стороны `CRect` независимо от других.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#39](../../atl-mfc-shared/codesnippet/CPP/crect-class_5.cpp)]  
  
##  <a name="a-namecrectequalrecta-crectequalrect"></a><a name="crect__equalrect"></a>  CRect::EqualRect  
 Определяет, является ли `CRect` равен данного прямоугольника.  
  
```  
 
BOOL EqualRect(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, содержащий координаты левого верхнего и нижнего правого угла прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если у двух прямоугольников же сверху, слева, снизу и правильные значения; в противном случае — 0.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#40](../../atl-mfc-shared/codesnippet/CPP/crect-class_6.cpp)]  
  
##  <a name="a-namecrectheighta-crectheight"></a><a name="crect__height"></a>  CRect::Height  
 Вычисляет высоту `CRect` путем вычитания верхнее значение из минимальное значение.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Полученное значение может быть отрицательным.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольник перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#41](../../atl-mfc-shared/codesnippet/CPP/crect-class_7.cpp)]  
  
##  <a name="a-namecrectinflaterecta-crectinflaterect"></a><a name="crect__inflaterect"></a>  CRect::InflateRect  
 `InflateRect` увеличивает `CRect` перемещая его сторон от ее центра.  
  
```  
 
    void InflateRect(
    int 
    x ,  
    int 
    y) throw();
void InflateRect(
    SIZE 
    size) throw();
void InflateRect(
    LPCRECT 
    lpRect) throw();
void InflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Указывает количество единиц, на которую требуется увеличить слева и справа от `CRect`.  
  
 *y*  
 Указывает количество единиц, на которую требуется увеличить верхней и нижней части `CRect`.  
  
 `size`  
 A [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) или [CSize](../../atl-mfc-shared/reference/csize-class.md) указывающее количество единиц, на которую требуется увеличить `CRect`.  `cx` Значение указывает количество единиц, на которую требуется увеличить левую и правую части и `cy` значение указывает количество единиц, на которую требуется увеличить сверху и снизу.  
  
 `lpRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` указывающее количество единиц, на которую требуется увеличить каждой стороны.  
  
 *l*  
 Указывает количество единиц, на которую увеличится в левой части `CRect`.  
  
 *t*  
 Указывает количество единиц, на которую требуется увеличить вверху `CRect`.  
  
 *r*  
 Указывает количество единиц, на которую увеличится в правой части `CRect`.  
  
 *b*  
 Указывает количество единиц, на которую увеличится в нижней части `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы сделать это, `InflateRect` вычитает устройств из left и top и добавляет единиц вправо и вниз. Параметры `InflateRect` подписываются значения; положительные значения увеличению `CRect` и отрицательные значения deflate его.  
  
 Первые две перегрузки, которую требуется увеличить обе пары разные стороны `CRect` таким образом, чтобы его ширина увеличивается в два раза *x* (или `cx`) и его высота всего увеличивается в два раза *y* (или `cy`). Две перегрузки, которую требуется увеличить каждой стороны `CRect` независимо от других.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#42](../../atl-mfc-shared/codesnippet/CPP/crect-class_8.cpp)]  
  
##  <a name="a-namecrectintersectrecta-crectintersectrect"></a><a name="crect__intersectrect"></a>  CRect::IntersectRect  
 Делает `CRect` равно пересечение двух прямоугольников существующий.  
  
```  
 
    BOOL IntersectRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect1`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, который содержит исходный прямоугольник.  
  
 `lpRect2`  
 Указывает `RECT` структуры или `CRect` объект, который содержит исходный прямоугольник.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пересечение не пуста; 0, если пересечение является пустым.  
  
### <a name="remarks"></a>Примечания  
 Пересечение является большой прямоугольник, содержащихся в обоих существующих прямоугольников.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#43](../../atl-mfc-shared/codesnippet/CPP/crect-class_9.cpp)]  
  
##  <a name="a-namecrectisrectemptya-crectisrectempty"></a><a name="crect__isrectempty"></a>  CRect::IsRectEmpty  
 Определяет, является ли `CRect` пуст.  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CRect` является пустой; 0 Если `CRect` не является пустым.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник является пустым, если ширина или высота равна 0 или отрицательным. Отличается от `IsRectNull`, который определяет, являются ли все координаты прямоугольника ноль.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольник перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#44](../../atl-mfc-shared/codesnippet/CPP/crect-class_10.cpp)]  
  
##  <a name="a-namecrectisrectnulla-crectisrectnull"></a><a name="crect__isrectnull"></a>  CRect::IsRectNull  
 Определяет, является ли слева, сверху вниз и непосредственно значения `CRect` равны 0.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CRect`сверху, слева, снизу и справа значения все равно 0; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Отличается от `IsRectEmpty`, которое определяет, пуст ли прямоугольник.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#45](../../atl-mfc-shared/codesnippet/CPP/crect-class_11.cpp)]  
  
##  <a name="a-namecrectmovetoxa-crectmovetox"></a><a name="crect__movetox"></a>  CRect::MoveToX  
 Эта функция вызывается для переместите прямоугольник в абсолютные координаты x заданные *x*.  
  
```  
 
void MoveToX(
int   
x) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Абсолютные координаты x верхнего левого угла прямоугольника.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#46](../../atl-mfc-shared/codesnippet/CPP/crect-class_12.cpp)]  
  
##  <a name="a-namecrectmovetoxya-crectmovetoxy"></a><a name="crect__movetoxy"></a>  CRect::MoveToXY  
 Эта функция используется для перемещения в абсолютные координаты x и y-указанного прямоугольника.  
  
```  
 
    void MoveToXY(
    int 
    x ,  
    int 
    y) throw();
void MoveToXY(
    POINT 
    point) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Абсолютные координаты x верхнего левого угла прямоугольника.  
  
 *y*  
 Абсолютный Координата y верхнего левого угла прямоугольника.  
  
 `point`  
 A **ТОЧКИ** Структура абсолютный верхнего левого угла прямоугольника.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#47](../../atl-mfc-shared/codesnippet/CPP/crect-class_13.cpp)]  
  
##  <a name="a-namecrectmovetoya-crectmovetoy"></a><a name="crect__movetoy"></a>  CRect::MoveToY  
 Эта функция вызывается для перемещения прямоугольника абсолютный координату по оси y заданные *y*.  
  
```  
 
void MoveToY(
int   
y) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *y*  
 Абсолютный Координата y верхнего левого угла прямоугольника.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#48](../../atl-mfc-shared/codesnippet/CPP/crect-class_14.cpp)]  
  
##  <a name="a-namecrectnormalizerecta-crectnormalizerect"></a><a name="crect__normalizerect"></a>  CRect::NormalizeRect  
 Нормализует `CRect` имеют положительное значение высоты и ширины.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник нормализуется для позиционирования четвертый квадранте, которой обычно используется Windows для координат. `NormalizeRect` Сравнивает значения верхней и нижней и меняет местами, если он больше нижней. Аналогичным образом переключает значения слева и справа, слева больше значения вправо. Эта функция удобна при работе с режимами другого сопоставления и инвертированного прямоугольников.  
  
> [!NOTE]
>  Следующие `CRect` функции-члены требуют нормализованных прямоугольники для правильной работы: [Высота](#crect__height), [Ширина](#crect__width), [размер](#crect__size), [IsRectEmpty](#crect__isrectempty), [PtInRect](#crect__ptinrect), [EqualRect](#crect__equalrect), [UnionRect](#crect__unionrect), [IntersectRect](#crect__intersectrect), [SubtractRect](#crect__subtractrect), [оператор ==](#crect__operator__eq_eq), [оператор! =](#crect__operator__neq), [оператор &#124;](#crect__operator__or), [оператор &#124; =](#crect__operator__or_eq), [оператор &](#crect__operator__amp_), и [оператор & =](#crect__operator__amp__eq).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#49](../../atl-mfc-shared/codesnippet/CPP/crect-class_15.cpp)]  
  
##  <a name="a-namecrectoffsetrecta-crectoffsetrect"></a><a name="crect__offsetrect"></a>  CRect::OffsetRect  
 Перемещает `CRect` с заданными смещениями.  
  
```  
 
    void OffsetRect(
    int 
    x ,  
    int 
    y) throw();
void OffsetRect(
    POINT 
    point) throw();
void OffsetRect(
    SIZE 
    size) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Указывает объем требуется переместиться влево или вправо. Оно должно быть отрицательным требуется переместиться влево.  
  
 *y*  
 Задает для перемещения вверх или вниз. Оно должно быть отрицательным для перемещения вверх.  
  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../Topic/CPoint%20Class.md) указания обоих измерения, которое необходимо переместить объект.  
  
 `size`  
 Содержит [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) указания обоих измерения, которое необходимо переместить объект.  
  
### <a name="remarks"></a>Примечания  
 Перемещает `CRect`*x* единиц вдоль оси x и *y* единицы по оси y.  *x* и *y* параметры являются значения со знаком, так что `CRect` могут перемещаться влево или вправо и вверх или вниз.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#50](../../atl-mfc-shared/codesnippet/CPP/crect-class_16.cpp)]  
  
##  <a name="a-namecrectoperatorlpcrecta-crectoperator-lpcrect"></a><a name="crect__operator_lpcrect"></a>  CRect::operator LPCRECT  
 Преобразует `CRect` для [LPCRECT](../Topic/Data%20Types%20\(MFC\).md).  
  
''' const throw() LPCRECT() оператор;
```  
  
### Remarks  
 When you use this function, you don't need the address-of ( **&**) operator. This operator will be automatically used when you pass a `CRect` object to a function that expects an **LPCRECT**.  
  
### Example  
 [!code-cpp[NVC_ATLMFC_Utilities#58](../../atl-mfc-shared/codesnippet/CPP/crect-class_17.cpp)]  
  
##  <a name="crect__operator_lprect"></a>  CRect::operator LPRECT  
 Converts a `CRect` to an [LPRECT](../Topic/Data%20Types%20\(MFC\).md).  
  
```  operator LPRECT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 При использовании этой функции не требуется взятия адреса ( **&**) оператор. Этот оператор будет автоматически использоваться при передаче `CRect` в функцию, ожидающую `LPRECT`.  
  
### <a name="example"></a>Пример  
 В примере показано [CRect::operator LPCRECT](#crect__operator_lpcrect).  
  
##  <a name="a-namecrectoperatoreqa-crectoperator-"></a><a name="crect__operator__eq"></a>  CRect::operator =  
 Назначает *srcRect* для `CRect`.  
  
```  
 
void operator=(
const RECT& 
srcRect) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *srcRect*  
 Ссылается на исходный прямоугольник. Может быть [RECT](RECT%20Structure1.md) или `CRect`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#59](../../atl-mfc-shared/codesnippet/CPP/crect-class_18.cpp)]  
  
##  <a name="a-namecrectoperatoreqeqa-crectoperator-"></a><a name="crect__operator__eq_eq"></a>  CRect::operator ==  
 Определяет, является ли `rect` равен `CRect` сравнивая координаты их верхний левый и правый нижний углы.  
  
```  
 
BOOL operator==(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылается на исходный прямоугольник. Может быть [RECT](RECT%20Structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объекты равны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#60](../../atl-mfc-shared/codesnippet/CPP/crect-class_19.cpp)]  
  
##  <a name="a-namecrectoperatorneqa-crectoperator-"></a><a name="crect__operator__neq"></a>  CRect::operator! =  
 Определяет, является ли `rect` не равен `CRect` сравнивая координаты их верхний левый и правый нижний углы.  
  
```  
 
BOOL operator!=(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылается на исходный прямоугольник. Может быть [RECT](RECT%20Structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объекты не равны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#61](../../atl-mfc-shared/codesnippet/CPP/crect-class_20.cpp)]  
  
##  <a name="a-namecrectoperatoraddeqa-crectoperator-"></a><a name="crect__operator__add_eq"></a>  CRect::operator +=  
 Первые две перегрузки переместить `CRect` с заданными смещениями.  
  
```  
 
void operator+=(
POINT   
point) throw();

void operator+=(
SIZE   
size) throw();

void operator+=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 A [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../Topic/CPoint%20Class.md) объект, который указывает число единиц, чтобы переместить прямоугольник.  
  
 `size`  
 A [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) указывающий число единиц, чтобы переместить прямоугольник.  
  
 `lpRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, содержащий число единиц, на которую требуется увеличить каждой стороны `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) добавляются значения `CRect`.  
  
 Третья перегрузка увеличивает `CRect` число единиц, заданных в каждый член параметра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#62](../../atl-mfc-shared/codesnippet/CPP/crect-class_21.cpp)]  
  
##  <a name="a-namecrectoperator-eqa-crectoperator--"></a><a name="crect__operator_-_eq"></a>  CRect::operator-=  
 Первые две перегрузки переместить `CRect` с заданными смещениями.  
  
```  
 
void operator-=(
POINT   
point) throw();

void operator-=(
SIZE   
size) throw();

void operator-=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 A [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../Topic/CPoint%20Class.md) объект, который указывает число единиц, чтобы переместить прямоугольник.  
  
 `size`  
 A [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) указывающий число единиц, чтобы переместить прямоугольник.  
  
 `lpRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, содержащий число единиц для каждой стороны deflate `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) вычитается из значения `CRect`.  
  
 Третья перегрузка сжимает `CRect` число единиц, заданных в каждый член параметра. Обратите внимание, что эта перегрузка функции как [DeflateRect](#crect__deflaterect).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#63](../../atl-mfc-shared/codesnippet/CPP/crect-class_22.cpp)]  
  
##  <a name="a-namecrectoperatorampeqa-crectoperator-amp"></a><a name="crect__operator__amp__eq"></a>  CRect::operator &amp;=  
 Наборы `CRect` равно пересечение `CRect` и `rect`.  
  
```  
 
void operator&=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Содержит [RECT](RECT%20Structure1.md) или `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Пересечение является большой прямоугольник, который содержится в обоих прямоугольников.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 В примере показано [CRect::IntersectRect](#crect__intersectrect).  
  
##  <a name="a-namecrectoperatororeqa-crectoperator-124"></a><a name="crect__operator__or_eq"></a>  CRect::operator &#124; =  
 Наборы `CRect` равно объединение `CRect` и `rect`.  
  
```  
 
void operator|=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Содержит `CRect` или [RECT](RECT%20Structure1.md).  
  
### <a name="remarks"></a>Примечания  
 Объединение является наименьший прямоугольник, содержащий оба исходного прямоугольника.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#64](../../atl-mfc-shared/codesnippet/CPP/crect-class_23.cpp)]  
  
##  <a name="a-namecrectoperatoradda-crectoperator-"></a><a name="crect__operator__add"></a>  CRect::operator +  
 Первые две перегрузки возвращают `CRect` объекта, равное `CRect` замещения с заданными смещениями.  
  
```  
 
CRect operator+(
POINT   
point) const throw();

CRect operator+(
LPCRECT   
lpRect) const throw();

CRect operator+(
SIZE   
size) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 A [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../Topic/CPoint%20Class.md) объект, который указывает число единиц для перемещения возвращаемое значение.  
  
 `size`  
 A [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) указывающий число единиц для перемещения возвращаемое значение.  
  
 `lpRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, содержащий число единиц, на которую требуется увеличить каждой стороны возвращаемого значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
  `CRect` Результате перемещение или могло бы ошибочно увеличить `CRect` число единиц, указанных в параметре.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) добавляются параметры `CRect`в позиции.  
  
 Третья перегрузка возвращает новый `CRect` равное `CRect` увеличивается за счет число единиц, заданных в каждый член параметра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#65](../../atl-mfc-shared/codesnippet/CPP/crect-class_24.cpp)]  
  
##  <a name="a-namecrectoperator-a-crectoperator--"></a><a name="crect__operator_-"></a>  CRect::operator-  
 Первые две перегрузки возвращают `CRect` объекта, равное `CRect` замещения с заданными смещениями.  
  
```  
 
CRect operator-(
POINT   
point) const throw();

CRect operator-(
SIZE   
size) const throw();

CRect operator-(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 A [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или `CPoint` объект, который указывает число единиц для перемещения возвращаемое значение.  
  
 `size`  
 A [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры или `CSize` объект, который указывает число единиц для перемещения возвращаемое значение.  
  
 `lpRect`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, содержащий число единиц deflate каждой стороны возвращаемого значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
  `CRect` Результате перемещение или сократятся `CRect` число единиц, указанных в параметре.  
  
### <a name="remarks"></a>Примечания  
 Параметр *x* и *y* (или `cx` и `cy`) параметры вычитаются из `CRect`в позиции.  
  
 Третья перегрузка возвращает новый `CRect` равное `CRect` уменьшения число единиц, заданных в каждый член параметра. Обратите внимание, что эта перегрузка функции как [DeflateRect](#crect__deflaterect), а не [SubtractRect](#crect__subtractrect).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#66](../../atl-mfc-shared/codesnippet/CPP/crect-class_25.cpp)]  
  
##  <a name="a-namecrectoperatorampa-crectoperator-amp"></a><a name="crect__operator__amp_"></a>  CRect::operator &amp;  
 Возвращает `CRect` это пересечение `CRect` и *rect2*.  
  
```  
 
CRect operator&(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *rect2*  
 Содержит [RECT](RECT%20Structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `CRect` это пересечение `CRect` и *rect2*.  
  
### <a name="remarks"></a>Примечания  
 Пересечение является большой прямоугольник, который содержится в обоих прямоугольников.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#67](../../atl-mfc-shared/codesnippet/CPP/crect-class_26.cpp)]  
  
##  <a name="a-namecrectoperatorora-crectoperator-124"></a><a name="crect__operator__or"></a>  CRect::operator &#124;  
 Возвращает `CRect` представляющий собой объединение `CRect` и *rect2*.  
  
```  
 
CRect operator|(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 *rect2*  
 Содержит [RECT](RECT%20Structure1.md) или `CRect`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` представляющий собой объединение `CRect` и *rect2*.  
  
### <a name="remarks"></a>Примечания  
 Объединение является наименьший прямоугольник, содержащий оба прямоугольника.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#68](../../atl-mfc-shared/codesnippet/CPP/crect-class_27.cpp)]  
  
##  <a name="a-namecrectptinrecta-crectptinrect"></a><a name="crect__ptinrect"></a>  CRect::PtInRect  
 Определяет, находится ли указанная точка в пределах `CRect`.  
  
```  
 
BOOL PtInRect(
POINT   
point) const throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Содержит [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры или [CPoint](../Topic/CPoint%20Class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эта точка находится в пределах `CRect`; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Точка находится в пределах `CRect` Если он находится на левой или верхней стороны или находится в пределах всех четырех сторон. Точки на стороне правому или нижнему находится за пределами `CRect`.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольник перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#51](../../atl-mfc-shared/codesnippet/CPP/crect-class_28.cpp)]  
  
##  <a name="a-namecrectsetrecta-crectsetrect"></a><a name="crect__setrect"></a>  CRect::SetRect  
 Задает размеры `CRect` в указанные координаты.  
  
```  
 
    void SetRect(
    int 
    x1 ,  
    int 
    y1 ,  
    int 
    x2 ,  
    int 
    y2) throw();

 
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
 [!code-cpp[NVC_ATLMFC_Utilities#52](../../atl-mfc-shared/codesnippet/CPP/crect-class_29.cpp)]  
  
##  <a name="a-namecrectsetrectemptya-crectsetrectempty"></a><a name="crect__setrectempty"></a>  CRect::SetRectEmpty  
 Делает `CRect` null прямоугольника, установив все координаты до нуля.  
  
```  
void SetRectEmpty() throw();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#53](../../atl-mfc-shared/codesnippet/CPP/crect-class_30.cpp)]  
  
##  <a name="a-namecrectsizea-crectsize"></a><a name="crect__size"></a>  CRect::Size  
  `cx` И `cy` содержат члены возвращаемого значения высоты и ширины `CRect`.  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) содержащий размер `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Высота или ширина может быть отрицательным.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольник перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#54](../../atl-mfc-shared/codesnippet/CPP/crect-class_31.cpp)]  
  
##  <a name="a-namecrectsubtractrecta-crectsubtractrect"></a><a name="crect__subtractrect"></a>  CRect::SubtractRect  
 Делает размеры **CRect** равно вычитания `lpRectSrc2` из `lpRectSrc1`.  
  
```  
 
    BOOL SubtractRect(
    LPCRECT 
    lpRectSrc1 ,  
    LPCRECT 
    lpRectSrc2) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `lpRectSrc1`  
 Указывает [RECT](RECT%20Structure1.md) структуры или `CRect` объект, из которого будет вычтен прямоугольника.  
  
 `lpRectSrc2`  
 Указывает `RECT` структуры или `CRect` объект, удаляемый из прямоугольника, на который указывает `lpRectSrc1` параметр.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Операция вычитания имеет наименьший прямоугольник, содержащий все точки в `lpRectScr1` не являющиеся пересечение `lpRectScr1` и *lpRectScr2*.  
  
 Прямоугольник, задаваемый параметром `lpRectSrc1` останутся без изменений, если прямоугольник, задаваемый параметром `lpRectSrc2` не полностью перекрывать прямоугольник, задаваемый параметром *lpRectSrc1* по крайней мере одним из x или y направлениях.  
  
 Например если `lpRectSrc1` были (10,10, 100,100) и `lpRectSrc2` были (50,50, 150,150) прямоугольника, на который указывает `lpRectSrc1` бы без изменений при возврате функции. Если `lpRectSrc1` были (10,10, 100,100) и `lpRectSrc2` были (50,10, 150,150), однако прямоугольника указывает `lpRectSrc1` будет содержать координаты (10,10, 50,100) при возврате функции.  
  
 `SubtractRect` не является таким же, как [оператор -](#crect__operator_-) ни [оператор-=](#crect__operator_-_eq). Ни один из этих операторов никогда не вызывает `SubtractRect`.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#55](../../atl-mfc-shared/codesnippet/CPP/crect-class_32.cpp)]  
  
##  <a name="a-namecrecttoplefta-crecttopleft"></a><a name="crect__topleft"></a>  CRect::TopLeft  
 Координаты возвращаются как ссылка на [CPoint](../Topic/CPoint%20Class.md) объект, содержащийся в `CRect`.  
  
```  
 
CPoint& TopLeft() throw();

const CPoint& TopLeft() const throw();

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Координаты верхнего левого угла прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно использовать, чтобы получить или задать верхнего левого угла прямоугольника. Задайте угол с помощью этой функции в левой части оператора присваивания.  
  
### <a name="example"></a>Пример  
 В примере показано [CRect::CenterPoint](#crect__centerpoint).  
  
##  <a name="a-namecrectunionrecta-crectunionrect"></a><a name="crect__unionrect"></a>  CRect::UnionRect  
 Делает размеры `CRect` равно объединение двух исходных прямоугольников.  
  
```  
 
    BOOL UnionRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect1`  
 Указывает [RECT](RECT%20Structure1.md) или `CRect` содержащий исходного прямоугольника.  
  
 `lpRect2`  
 Указывает на `RECT` или `CRect` содержащий исходного прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объединение не пуста; 0, если объединение является пустым.  
  
### <a name="remarks"></a>Примечания  
 Объединение является наименьший прямоугольник, содержащий оба исходного прямоугольника.  
  
 Windows игнорирует размеры пустой прямоугольник; то есть, прямоугольник, который имеет не высота или ширина не.  
  
> [!NOTE]
>  Оба прямоугольника должно быть нормализовано или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольников перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#56](../../atl-mfc-shared/codesnippet/CPP/crect-class_33.cpp)]  
  
##  <a name="a-namecrectwidtha-crectwidth"></a><a name="crect__width"></a>  CRect::Width  
 Вычисляет ширину `CRect` путем вычитания значения слева от правильного значения.  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина `CRect`.  
  
### <a name="remarks"></a>Примечания  
 Ширина может быть отрицательным.  
  
> [!NOTE]
>  Должны быть нормализованы прямоугольника или эта функция может завершиться ошибкой. Можно вызвать [NormalizeRect](#crect__normalizerect) нормализовать прямоугольник перед вызовом этой функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#57](../../atl-mfc-shared/codesnippet/CPP/crect-class_34.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CPoint](../Topic/CPoint%20Class.md)   
 [Класс CSize](../../atl-mfc-shared/reference/csize-class.md)   
 [RECT](RECT%20Structure1.md)

