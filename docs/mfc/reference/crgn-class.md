---
title: "CRgn-класс | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRgn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRGN"
  - "CRgn - класс"
  - "регионы, MFC"
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRgn-класс
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует область интерфейса графических устройств Windows (GDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRgn : public CGdiObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRgn::CRgn](#crgn__crgn)|Создает объект `CRgn`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRgn::CombineRgn](#crgn__combinergn)|Наборы `CRgn` таким образом, чтобы он эквивалентен объединения двух указанных `CRgn` объектов.|  
|[CRgn::CopyRgn](#crgn__copyrgn)|Наборы `CRgn` таким образом, чтобы он является копией указанного `CRgn` объекта.|  
|[CRgn::CreateEllipticRgn](#crgn__createellipticrgn)|Инициализирует `CRgn` объекта с эллиптической областью.|  
|[CRgn::CreateEllipticRgnIndirect](#crgn__createellipticrgnindirect)|Инициализирует `CRgn` объект с эллиптической области, определяемой [RECT](RECT%20Structure1.md) структуры.|  
|[CRgn::CreateFromData](#crgn__createfromdata)|Создает область из заданной области и преобразования данных.|  
|[CRgn::CreateFromPath](#crgn__createfrompath)|Создает область из пути, который выбран в контекст устройства.|  
|[CRgn::CreatePolygonRgn](#crgn__createpolygonrgn)|Инициализирует `CRgn` объекта многоугольную область. Система замыкает многоугольник автоматически, при необходимости рисования линии из последнего вершин с первым.|  
|[CRgn::CreatePolyPolygonRgn](#crgn__createpolypolygonrgn)|Инициализирует `CRgn` объект с областью, состоящий из набора закрытых многоугольников. Может быть несвязанным многоугольников, или они могут перекрываться.|  
|[CRgn::CreateRectRgn](#crgn__createrectrgn)|Инициализирует `CRgn` объект с прямоугольной области.|  
|[CRgn::CreateRectRgnIndirect](#crgn__createrectrgnindirect)|Инициализирует `CRgn` объект с прямоугольной области, определяемой [RECT](RECT%20Structure1.md) структуры.|  
|[CRgn::CreateRoundRectRgn](#crgn__createroundrectrgn)|Инициализирует `CRgn` объект с прямоугольную область со скругленными углами.|  
|[CRgn::EqualRgn](#crgn__equalrgn)|Проверяет два `CRgn` объектов, чтобы определить, являются ли они эквивалентными.|  
|[CRgn::FromHandle](#crgn__fromhandle)|Возвращает указатель на `CRgn` объект для заданного дескриптора в регионе Windows.|  
|[CRgn::GetRegionData](#crgn__getregiondata)|Заполняет указанный буфер данных, описывающих данной области.|  
|[CRgn::GetRgnBox](#crgn__getrgnbox)|Получает координаты ограничивающего прямоугольника `CRgn` объекта.|  
|[CRgn::OffsetRgn](#crgn__offsetrgn)|Перемещает `CRgn` объекта с заданными смещениями.|  
|[CRgn::PtInRegion](#crgn__ptinregion)|Определяет, является ли указанная точка в регионе.|  
|[CRgn::RectInRegion](#crgn__rectinregion)|Определяет, является ли какой-либо части заданного прямоугольника в пределах области.|  
|[CRgn::SetRectRgn](#crgn__setrectrgn)|Наборы `CRgn` объекта для указанной прямоугольной области.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRgn::operator HRGN](#crgn__operator_hrgn)|Возвращает дескриптор Windows, содержащихся в `CRgn` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Область — это эллипса или многоугольную область в окне. Чтобы использовать регионы, использовать функции-члены класса `CRgn` с обрезки функции, определенные как члены класса `CDC`.  
  
 Функции-члены `CRgn` создания, изменения и получения сведений об объекте области, для которой они вызываются.  
  
 Дополнительные сведения об использовании `CRgn`, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecrgncombinergna-crgncombinergn"></a><a name="crgn__combinergn"></a>  CRgn::CombineRgn  
 Создает новую область GDI путем объединения двух существующих областей.  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>Параметры  
 `pRgn1`  
 Идентифицирует существующей области.  
  
 `pRgn2`  
 Идентифицирует существующей области.  
  
 `nCombineMode`  
 Указывает операции, выполняемые при объединении двух исходных областей. Это может быть одно из следующих значений:  
  
- **RGN_AND** использует перекрывающиеся области обоих регионах (пересечение).  
  
- **RGN_COPY** создает копию области 1 (идентифицируются `pRgn1`).  
  
- **RGN_DIFF** создает область, состоящую из области региона 1 (идентифицируются `pRgn1`), не являются частью области 2 (идентифицируются `pRgn2`).  
  
- **RGN_OR** объединяет обе области целиком (объединение).  
  
- **RGN_XOR** объединяет обе области, но удаляет перекрывающиеся области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает тип результирующего области. Он может принимать одно из следующих значений:  
  
- **COMPLEXREGION** Новая область имеет перекрывающиеся границы.  
  
- **ОШИБКА** не новая область создана.  
  
- **NULLREGION** Новая область пуста.  
  
- **SIMPLEREGION** Новая область имеет перекрывающиеся границы отсутствуют.  
  
### <a name="remarks"></a>Примечания  
 Области объединяются в соответствии с `nCombineMode`.  
  
 Два указанных области объединяются, и полученный дескриптор области хранится в `CRgn` объекта. Таким образом, любые области хранится в `CRgn` области объединенных заменить объект.  
  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 Используйте [CopyRgn](#crgn__copyrgn) для простого копирования одного региона в другой области.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/CPP/crgn-class_1.cpp)]  
  
##  <a name="a-namecrgncopyrgna-crgncopyrgn"></a><a name="crgn__copyrgn"></a>  CRgn::CopyRgn  
 Копирует области, определяемой `pRgnSrc` в `CRgn` объекта.  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `pRgnSrc`  
 Идентифицирует существующей области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает тип результирующего области. Он может принимать одно из следующих значений:  
  
- **COMPLEXREGION** Новая область имеет перекрывающиеся границы.  
  
- **ОШИБКА** не новая область создана.  
  
- **NULLREGION** Новая область пуста.  
  
- **SIMPLEREGION** Новая область имеет перекрывающиеся границы отсутствуют.  
  
### <a name="remarks"></a>Примечания  
 Новая область заменяет ранее хранятся в области `CRgn` объекта. Эта функция является особым случаем [CombineRgn](#crgn__combinergn) функции-члена.  
  
### <a name="example"></a>Пример  
  В примере показано [CRgn::CreateEllipticRgn](#crgn__createellipticrgn).  
  
##  <a name="a-namecrgncreateellipticrgna-crgncreateellipticrgn"></a><a name="crgn__createellipticrgn"></a>  CRgn::CreateEllipticRgn  
 Создает область эллипса.  
  
```  
BOOL CreateEllipticRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>Параметры  
 `x1`  
 Указывает логические координаты по оси x верхнего левого угла ограничивающего прямоугольника эллипса.  
  
 `y1`  
 Указывает логический Координата y верхнего левого угла ограничивающего прямоугольника эллипса.  
  
 `x2`  
 Указывает логическую координату x нижнего правого угла ограничивающего прямоугольника эллипса.  
  
 `y2`  
 Указывает логическую координату y нижнего правого угла ограничивающего прямоугольника эллипса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Области, определяемый ограничивающим прямоугольником, заданным с `x1`, `y1`, `x2`, и `y2`. Область хранится в `CRgn` объекта.  
  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 После его завершения области, созданные с помощью `CreateEllipticRgn` функции приложения следует выбрать регион из контекста устройства и использовать `DeleteObject` функции, чтобы удалить его.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/CPP/crgn-class_2.cpp)]  
  
##  <a name="a-namecrgncreateellipticrgnindirecta-crgncreateellipticrgnindirect"></a><a name="crgn__createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect  
 Создает область эллипса.  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает `RECT` структуры или `CRect` объект, который содержит логические координаты верхний левый и правый нижний углы прямоугольника, ограничивающего эллипс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Область определяется структура или объект, на который указывает `lpRect` и хранится в `CRgn` объекта.  
  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 После его завершения области, созданные с помощью `CreateEllipticRgnIndirect` функции приложения следует выбрать регион из контекста устройства и использовать `DeleteObject` функции, чтобы удалить его.  
  
### <a name="example"></a>Пример  
  В примере показано [CRgn::CreateRectRgnIndirect](#crgn__createrectrgnindirect).  
  
##  <a name="a-namecrgncreatefromdataa-crgncreatefromdata"></a><a name="crgn__createfromdata"></a>  CRgn::CreateFromData  
 Создает область из заданной области и преобразования данных.  
  
```  
BOOL CreateFromData(
    const XFORM* lpXForm,  
    int nCount,  
    const RGNDATA* pRgnData);
```  
  
### <a name="parameters"></a>Параметры  
 *lpXForm*  
 Указывает [XFORM](../../mfc/reference/xform-structure.md) структуру данных, определяющий преобразование, которое необходимо выполнить в области. Если этот указатель имеет **NULL**, используется единичное преобразование.  
  
 `nCount`  
 Указывает число байтов, на который указывает `pRgnData`.  
  
 `pRgnData`  
 Указывает [RGNDATA](../../mfc/reference/rgndata-structure.md) структуру данных, содержащую данные этой области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложение может извлечь данные для региона, вызвав `CRgn::GetRegionData` функции.  
  
##  <a name="a-namecrgncreatefrompatha-crgncreatefrompath"></a><a name="crgn__createfrompath"></a>  CRgn::CreateFromPath  
 Создает область из пути, который выбран в контекст устройства.  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Определяет контекст устройства, который содержит замкнутый контур.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Контекст устройства, идентифицируемый `pDC` параметр должен содержать замкнутый контур. После `CreateFromPath` преобразует путь в регионе, Windows удаляет замкнутый контур из контекста устройства.  
  
##  <a name="a-namecrgncreatepolygonrgna-crgncreatepolygonrgn"></a><a name="crgn__createpolygonrgn"></a>  CRgn::CreatePolygonRgn  
 Создает область из многоугольников.  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPoints`  
 Указывает массив **ТОЧКИ** структуры или массив `CPoint` объектов. Каждая структура задает координаты x и y координаты одной вершины многоугольника.  **ТОЧКИ** структура имеет следующий вид:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `nCount`  
 Указывает количество **ТОЧКИ** структуры или `CPoint` объектов в массиве, на который указывает `lpPoints`.  
  
 `nMode`  
 Задает режим заполнения для региона. Этот параметр может быть либо **АЛЬТЕРНАТИВНЫЙ** или **ПОВОРОТА**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Система замыкает многоугольник автоматически, при необходимости рисования линии из последнего вершин с первым. Полученный региона хранится в `CRgn` объекта.  
  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 Когда режим заполнения многоугольников — **АЛЬТЕРНАТИВНЫЙ**, система заполняет область между сторон нечетных и четных многоугольников для каждой строки. То есть система заполняет область между первой и второй стороны, между третьей и четвертой части и т. д.  
  
 Когда режим заполнения многоугольников — **ПОВОРОТА**, система использует направление, в котором был нарисован рисунок для определения необходимости заполнения области. Каждого сегмента линии многоугольника отрисовывается в часовой или против часовой стрелки. Каждый раз, когда воображаемой линии, соединяющей замкнутой области фигуры за пределы проходит через по часовой стрелке отрезок, значение счетчика увеличивается. Когда строка проходит через против часовой стрелки отрезок, уменьшается. Область заполняется, если счетчик имеет ненулевое значение, при достижении строки за пределами рисунка.  
  
 Когда приложение завершило области, созданные с помощью `CreatePolygonRgn` функции, его следует выбрать регион из контекста устройства и использовать `DeleteObject` функции, чтобы удалить его.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/CPP/crgn-class_3.cpp)]  
  
##  <a name="a-namecrgncreatepolypolygonrgna-crgncreatepolypolygonrgn"></a><a name="crgn__createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn  
 Создает область, состоящий из набора закрытых многоугольников.  
  
```  
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount,  
    int nPolyFillMode);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPoints`  
 Указывает массив **ТОЧКИ** структуры или массив `CPoint` объекты, определяющего вершины закрашиваемого многоугольников. Каждый многоугольник необходимо явным образом закрыта, поскольку системе не закрывает их автоматически. Последовательно указываются многоугольников.  **ТОЧКИ** структура имеет следующий вид:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `lpPolyCounts`  
 Указывает массив целых чисел. Первое число указывает количество вершин в первый многоугольника в `lpPoints` массива, второе указывает число вершин в многоугольник второй и т. д.  
  
 `nCount`  
 Указывает общее число целых чисел в `lpPolyCounts` массива.  
  
 `nPolyFillMode`  
 Задает режим заполнения многоугольников. Это значение может быть либо **АЛЬТЕРНАТИВНЫЙ** или **ПОВОРОТА**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Полученный региона хранится в `CRgn` объекта.  
  
 Может быть несвязанным многоугольников, или они могут перекрываться.  
  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 Когда режим заполнения многоугольников — **АЛЬТЕРНАТИВНЫЙ**, система заполняет область между сторон нечетных и четных многоугольников для каждой строки. То есть система заполняет область между первой и второй стороны, между третьей и четвертой части и т. д.  
  
 Когда режим заполнения многоугольников — **ПОВОРОТА**, система использует направление, в котором был нарисован рисунок для определения необходимости заполнения области. Каждого сегмента линии многоугольника отрисовывается в часовой или против часовой стрелки. Каждый раз, когда воображаемой линии, соединяющей замкнутой области фигуры за пределы проходит через по часовой стрелке отрезок, значение счетчика увеличивается. Когда строка проходит через против часовой стрелки отрезок, уменьшается. Область заполняется, если счетчик имеет ненулевое значение, при достижении строки за пределами рисунка.  
  
 Когда приложение завершило области, созданные с помощью `CreatePolyPolygonRgn` функции, его следует выбрать регион из контекста устройства и использовать [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) функции-члена для его удаления.  
  
##  <a name="a-namecrgncreaterectrgna-crgncreaterectrgn"></a><a name="crgn__createrectrgn"></a>  CRgn::CreateRectRgn  
 Создает прямоугольную область, которая хранится в `CRgn` объекта.  
  
```  
BOOL CreateRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>Параметры  
 `x1`  
 Указывает логическую координату x верхнего левого угла области.  
  
 `y1`  
 Указывает логическую координату y верхнего левого угла области.  
  
 `x2`  
 Указывает логическую координату x нижнего правого угла области.  
  
 `y2`  
 Указывает логическую координату y нижнего правого угла области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 После его завершения области, созданные с помощью `CreateRectRgn`, приложение должно использовать [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) функция-член для удаления области.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/CPP/crgn-class_4.cpp)]  
  
 Дополнительный пример в разделе [CRgn::CombineRgn](#crgn__combinergn).  
  
##  <a name="a-namecrgncreaterectrgnindirecta-crgncreaterectrgnindirect"></a><a name="crgn__createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect  
 Создает прямоугольную область, которая хранится в `CRgn` объекта.  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает `RECT` структуры или `CRect` объект, который содержит логические координаты верхний левый и правый нижний углы области.  `RECT` Структура имеет следующий вид:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 После его завершения области, созданные с помощью `CreateRectRgnIndirect`, приложение должно использовать [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) функция-член для удаления области.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/CPP/crgn-class_5.cpp)]  
  
##  <a name="a-namecrgncreateroundrectrgna-crgncreateroundrectrgn"></a><a name="crgn__createroundrectrgn"></a>  CRgn::CreateRoundRectRgn  
 Создает со скругленными углами, которые хранятся в прямоугольную область `CRgn` объекта.  
  
```  
BOOL CreateRoundRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3);
```  
  
### <a name="parameters"></a>Параметры  
 `x1`  
 Указывает логическую координату x верхнего левого угла области.  
  
 `y1`  
 Указывает логическую координату y верхнего левого угла области.  
  
 `x2`  
 Указывает логическую координату x нижнего правого угла области.  
  
 `y2`  
 Указывает логическую координату y нижнего правого угла области.  
  
 *X3*  
 Задает ширину эллипса, используемый для создания прямоугольника с закругленными углами.  
  
 `y3`  
 Указывает высоту эллипса, используемый для создания прямоугольника с закругленными углами.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Размер области ограничен 32 767 32 767, логические устройства или 64 КБ памяти, какое из значений меньше.  
  
 Когда приложение завершило области, созданные с помощью `CreateRoundRectRgn` функции, его следует выбрать регион из контекста устройства и использовать [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) функции-члена для его удаления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/CPP/crgn-class_6.cpp)]  
  
##  <a name="a-namecrgncrgna-crgncrgn"></a><a name="crgn__crgn"></a>  CRgn::CRgn  
 Создает объект `CRgn`.  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>Примечания  
  `m_hObject` Член данных не содержит допустимую область Windows GDI до инициализации объекта с одним или несколькими другого `CRgn` функции-члены.  
  
### <a name="example"></a>Пример  
  В примере показано [CRgn::CreateRoundRectRgn](#crgn__createroundrectrgn).  
  
##  <a name="a-namecrgnequalrgna-crgnequalrgn"></a><a name="crgn__equalrgn"></a>  CRgn::EqualRgn  
 Определяет, является ли данной области эквивалентно регион, хранящиеся в `CRgn` объекта.  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `pRgn`  
 Определяет область.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в двух регионах эквивалентны; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/CPP/crgn-class_7.cpp)]  
  
##  <a name="a-namecrgnfromhandlea-crgnfromhandle"></a><a name="crgn__fromhandle"></a>  CRgn::FromHandle  
 Возвращает указатель на `CRgn` объект для заданного дескриптора в регионе Windows.  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>Параметры  
 `hRgn`  
 Указывает дескриптор область Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `CRgn`. Если функция не прошла успешно, возвращаемое значение равно **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CRgn` объект еще не присоединен к дескриптору временный `CRgn` объект создается и прикрепляется. Этот временный `CRgn` допустимо только до следующей приложение имеет время простоя в свой цикл событий, после чего график все временные объекты удаляются. Другими словами является что временный объект допустима только во время обработки одного окна сообщения.  
  
##  <a name="a-namecrgngetregiondataa-crgngetregiondata"></a><a name="crgn__getregiondata"></a>  CRgn::GetRegionData  
 Заполняет указанный буфер данных, описывающих области.  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `lpRgnData`  
 Указывает [RGNDATA](../../mfc/reference/rgndata-structure.md) Структура данных, которая получает данные. Если этот параметр равен **NULL**, возвращаемое значение содержит число байтов, необходимое для области данных.  
  
 `nCount`  
 Указывает размер в байтах, `lpRgnData` буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно и `nCount` указывает достаточного числа байтов, возвращаемое значение всегда равно `nCount`. Если функция завершается с ошибкой или `nCount` указывает меньше, чем достаточного количества байтов, возвращаемое значение равно 0 (ошибка).  
  
### <a name="remarks"></a>Примечания  
 Эти данные включают размеры прямоугольника, составляющие области. Эта функция используется в сочетании с `CRgn::CreateFromData` функции.  
  
##  <a name="a-namecrgngetrgnboxa-crgngetrgnbox"></a><a name="crgn__getrgnbox"></a>  CRgn::GetRgnBox  
 Получает координаты ограничивающего прямоугольника `CRgn` объекта.  
  
```  
int GetRgnBox(LPRECT lpRect) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает `RECT` структуры или `CRect` объект для получения координаты ограничивающего прямоугольника.  `RECT` Структура имеет следующий вид:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает тип области. Может принимать одно из следующих значений:  
  
- **COMPLEXREGION** область имеет перекрывающиеся границы.  
  
- **NULLREGION** область пуста.  
  
- **ОШИБКА** `CRgn` объект не указывает допустимую область.  
  
- **SIMPLEREGION** область имеет перекрывающиеся границы отсутствуют.  
  
### <a name="example"></a>Пример  
  В примере показано [CRgn::CreatePolygonRgn](#crgn__createpolygonrgn).  
  
##  <a name="a-namecrgnoffsetrgna-crgnoffsetrgn"></a><a name="crgn__offsetrgn"></a>  CRgn::OffsetRgn  
 Перемещение области, хранящиеся в `CRgn` объекта с заданными смещениями.  
  
```  
int OffsetRgn(
    int x,  
    int y);

 
int OffsetRgn(
    POINT point);
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Указывает число единиц для перемещения влево или вправо.  
  
 *y*  
 Указывает число единиц для перемещения вверх или вниз.  
  
 `point`  
 Координата по оси x `point` Указывает число единиц для перемещения влево или вправо. Координата по оси y `point` Указывает число единиц для перемещения вверх или вниз.  `point` Параметра могут быть либо **ТОЧКИ** структуры или `CPoint` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип новой области. Это может быть одно из следующих значений:  
  
- **COMPLEXREGION** область имеет перекрывающиеся границы.  
  
- **ОШИБКА** Недопустимый дескриптор области.  
  
- **NULLREGION** область пуста.  
  
- **SIMPLEREGION** область имеет перекрывающиеся границы отсутствуют.  
  
### <a name="remarks"></a>Примечания  
 Функция перемещает области *x* единиц вдоль оси x и *y* единицы по оси y.  
  
 Значения координат области должен быть меньше или равно 32 767 и больше или равно –32,768.  *x* и *y* параметров необходимо выбирать так, чтобы предотвратить координаты недопустимый регион.  
  
### <a name="example"></a>Пример  
  В примере показано [CRgn::CreateEllipticRgn](#crgn__createellipticrgn).  
  
##  <a name="a-namecrgnoperatorhrgna-crgnoperator-hrgn"></a><a name="crgn__operator_hrgn"></a>  CRgn::operator HRGN  
 Этот оператор используется получить дескриптор вложенного Windows GDI `CRgn` объекта.  
  
''' оператор HRGN() константу;

 
```  
  
### Return Value  
 If successful, a handle to the Windows GDI object represented by the `CRgn` object; otherwise **NULL**.  
  
### Remarks  
 This operator is a casting operator, which supports direct use of an **HRGN** object.  
  
 For more information about using graphic objects, see the article [Graphic Objects](http://msdn.microsoft.com/library/windows/desktop/dd144962) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="crgn__ptinregion"></a>  CRgn::PtInRegion  
 Checks whether the point given by *x* and *y* is in the region stored in the `CRgn` object.  
  
```  
BOOL PtInRegion (int x,  
    int y) константу;

 
 
PtInRegion BOOL (ТОЧКА-точка) константу;

 
```  
  
### Parameters  
 *x*  
 Specifies the logical x-coordinate of the point to test.  
  
 *y*  
 Specifies the logical y-coordinate of the point to test.  
  
 `point`  
 The x- and y-coordinates of `point` specify the x- and y-coordinates of the point to test the value of. The `point` parameter can either be a **POINT** structure or a `CPoint` object.  
  
### Return Value  
 Nonzero if the point is in the region; otherwise 0.  
  
##  <a name="crgn__rectinregion"></a>  CRgn::RectInRegion  
 Determines whether any part of the rectangle specified by `lpRect` is within the boundaries of the region stored in the `CRgn` object.  
  
```  
BOOL RectInRegion(LPCRECT lpRect) константу;

 
```  
  
### Parameters  
 `lpRect`  
 Points to a `RECT` structure or `CRect` object. The `RECT` structure has the following form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### Return Value  
 Nonzero if any part of the specified rectangle lies within the boundaries of the region; otherwise 0.  
  
##  <a name="crgn__setrectrgn"></a>  CRgn::SetRectRgn  
 Creates a rectangular region.  
  
```  
void SetRectRgn (int x1,  
    int y1  
    int x2,  
    int y2);

 
void SetRectRgn (LPCRECT lpRect);
```  
  
### Parameters  
 `x1`  
 Specifies the x-coordinate of the upper-left corner of the rectangular region.  
  
 `y1`  
 Specifies the y-coordinate of the upper-left corner of the rectangular region.  
  
 `x2`  
 Specifies the x-coordinate of the lower-right corner of the rectangular region.  
  
 `y2`  
 Specifies the y-coordinate of the lower-right corner of the rectangular region.  
  
 `lpRect`  
 Specifies the rectangular region. Can be either a pointer to a `RECT` structure or a `CRect` object.  
  
### Remarks  
 Unlike [CreateRectRgn](#crgn__createrectrgn), however, it does not allocate any additional memory from the local Windows application heap. Instead, it uses the space allocated for the region stored in the `CRgn` object. This means that the `CRgn` object must already have been initialized with a valid Windows region before calling `SetRectRgn`. The points given by `x1`, `y1`, `x2`, and `y2` specify the minimum size of the allocated space.  
  
 Use this function instead of the `CreateRectRgn` member function to avoid calls to the local memory manager.  
  
## See Also  
 [CWnd Class](../Topic/CWnd%20Class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)



