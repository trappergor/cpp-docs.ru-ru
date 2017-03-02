---
title: "Класс CD2DGeometrySink | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DGeometrySink
- CD2DGeometrySink
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometrySink class
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8a51d9475437ae460340d419a88bc46effa81f5f
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgeometrysink-class"></a>Класс CD2DGeometrySink
Программа-оболочка для ID2D1GeometrySink.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DGeometrySink;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|Создает объект CD2DGeometrySink из CD2DPathGeometry объекта.|  
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Деструктор Вызывается при уничтожении объекта D2D geometry приемника.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](#addarc)|Добавляет одну дугу по геометрическому пути|  
|[CD2DGeometrySink::AddBezier](#addbezier)|Создание кривой Безье третьего порядка между текущей точкой и заданной конечной точкой.|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Создает последовательность кривых Безье третьего порядка и добавляет их в приемник geometry.|  
|[CD2DGeometrySink::AddLine](#addline)|Создает сегмент линии между текущей точкой и заданной конечной точкой и добавляет его в приемник geometry.|  
|[CD2DGeometrySink::AddLines](#addlines)|Создает последовательность строк, используя указанные точки и добавляет их в приемник geometry.|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Создание кривой Безье второго порядка между текущей точкой и заданной конечной точкой.|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Добавляет последовательность сегментов Безье, квадратичных как массив в одном вызове.|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Открывает новую фигуру в заданной точке.|  
|[CD2DGeometrySink::Close](#close)|Закрывает геометрического объекта-приемника|  
|[CD2DGeometrySink::EndFigure](#endfigure)|Заканчивает текущую фигуру; При необходимости закрывает его.|  
|[CD2DGeometrySink::Get](#get)|Возвращает интерфейс ID2D1GeometrySink|  
|[CD2DGeometrySink::IsValid](#isvalid)|Проверяет допустимость приемника geometry|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|Определяет метод, используемый для указания точки находятся внутри описываемого этот приемник геометрического объекта geometry и точек, находящихся за пределами.|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Указывает параметры обводки и соединения для применения к новые сегменты добавлен в приемник geometry.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|Возвращает интерфейс ID2D1GeometrySink|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometrySink::m_pSink](#m_psink)|Указатель на ID2D1GeometrySink.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CD2DGeometrySink`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dgeometrysinka--cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink:: ~ CD2DGeometrySink  
 Деструктор Вызывается при уничтожении объекта D2D geometry приемника.  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="a-nameaddarca--cd2dgeometrysinkaddarc"></a><a name="addarc"></a>CD2DGeometrySink::AddArc  
 Добавляет одну дугу по геометрическому пути  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>Параметры  
 `arc`  
 Чтобы добавить к рисунку сегмента дуги  
  
##  <a name="a-nameaddbeziera--cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a>CD2DGeometrySink::AddBezier  
 Создание кривой Безье третьего порядка между текущей точкой и заданной конечной точкой.  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Параметры  
 `bezier`  
 Структура, которая описывает конечную точку кривой Безье для добавления и контрольные точки.  
  
##  <a name="a-nameaddbeziersa--cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a>CD2DGeometrySink::AddBeziers  
 Создает последовательность кривых Безье третьего порядка и добавляет их в приемник geometry.  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Параметры  
 `beziers`  
 Массив сегментов Безье, описывающий Создание кривых Безье. Кривая строится из текущей точки приемника geometry (конечной точки последнего сегмента рисования или местоположении, заданном свойством BeginFigure) в конечную точку первого сегмента Безье в массиве. Если массив содержит дополнительные сегменты Безье, каждый последующий сегмент Безье использует конечную точку предыдущего сегмента Безье в качестве начальной точки.  
  
##  <a name="a-nameaddlinea--cd2dgeometrysinkaddline"></a><a name="addline"></a>CD2DGeometrySink::AddLine  
 Создает сегмент линии между текущей точкой и заданной конечной точкой и добавляет его в приемник geometry.  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Конечная точка линии для рисования.  
  
##  <a name="a-nameaddlinesa--cd2dgeometrysinkaddlines"></a><a name="addlines"></a>CD2DGeometrySink::AddLines  
 Создает последовательность строк, используя указанные точки и добавляет их в приемник geometry.  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>Параметры  
 `points`  
 Массив из одной или нескольких точек, описывающих линии для рисования. Линия берет начало от текущей точки приемника geometry (конечной точки последнего сегмента рисования или местоположении, заданном свойством BeginFigure) точки в массиве. Если массив содержит дополнительные точки, линия с первой точки до второй точки в массиве, из вторую точку для третьей точки и т. д. Массив из последовательности конечных точек для рисования линий.  
  
##  <a name="a-nameaddquadraticbeziera--cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a>CD2DGeometrySink::AddQuadraticBezier  
 Создание кривой Безье второго порядка между текущей точкой и заданной конечной точкой.  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Параметры  
 `bezier`  
 Структура, которая описывает контрольную точку и конечную точку кривой Безье второго порядка для добавления.  
  
##  <a name="a-nameaddquadraticbeziersa--cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a>CD2DGeometrySink::AddQuadraticBeziers  
 Добавляет последовательность сегментов Безье, квадратичных как массив в одном вызове.  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Параметры  
 `beziers`  
 Массив из последовательности квадратичных Безье сегментов.  
  
##  <a name="a-namebeginfigurea--cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a>CD2DGeometrySink::BeginFigure  
 Открывает новую фигуру в заданной точке.  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>Параметры  
 `startPoint`  
 Точка, с которой начинается новая фигура.  
  
 `figureBegin`  
 Новая фигура должна ли пустыми или заполнены.  
  
##  <a name="a-namecd2dgeometrysinka--cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink  
 Создает объект CD2DGeometrySink из CD2DPathGeometry объекта.  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>Параметры  
 `pathGeometry`  
 Существующий объект CD2DPathGeometry.  
  
##  <a name="a-nameclosea--cd2dgeometrysinkclose"></a><a name="close"></a>CD2DGeometrySink::Close  
 Закрывает геометрического объекта-приемника  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — значение FALSE.  
  
##  <a name="a-nameendfigurea--cd2dgeometrysinkendfigure"></a><a name="endfigure"></a>CD2DGeometrySink::EndFigure  
 Заканчивает текущую фигуру; При необходимости закрывает его.  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>Параметры  
 `figureEnd`  
 Значение, указывающее, закрыт ли текущую фигуру. При закрытии рисунке линия между текущей точкой и заданные BeginFigure начальной точки.  
  
##  <a name="a-namegeta--cd2dgeometrysinkget"></a><a name="get"></a>CD2DGeometrySink::Get  
 Возвращает интерфейс ID2D1GeometrySink  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1GeometrySink или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-nameisvalida--cd2dgeometrysinkisvalid"></a><a name="isvalid"></a>CD2DGeometrySink::IsValid  
 Проверяет допустимость приемника geometry  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если приемник geometry является допустимым; в противном случае — значение FALSE.  
  
##  <a name="a-namempsinka--cd2dgeometrysinkmpsink"></a><a name="m_psink"></a>CD2DGeometrySink::m_pSink  
 Указатель на ID2D1GeometrySink.  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="a-nameoperatorid2d1geometrysinkstara--cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::operator ID2D1GeometrySink *  
 Возвращает интерфейс ID2D1GeometrySink  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1GeometrySink или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namesetfillmodea--cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a>CD2DGeometrySink::SetFillMode  
 Определяет метод, используемый для указания точки находятся внутри описываемого этот приемник геометрического объекта geometry и точек, находящихся за пределами.  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>Параметры  
 `fillMode`  
 Метод, используемый, чтобы определить, является ли заданная точка частью геометрии.  
  
##  <a name="a-namesetsegmentflagsa--cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags  
 Указывает параметры обводки и соединения для применения к новые сегменты добавлен в приемник geometry.  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `vertexFlags`  
 Параметры обводки и соединения для применения к новые сегменты добавлен в приемник geometry.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

