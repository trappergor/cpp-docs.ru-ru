---
title: "Класс CD2DGeometrySink | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
dev_langs: C++
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b070dce706ab1fa63c71ac84b68f36c596b812d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[CD2DGeometrySink::AddBezier](#addbezier)|Создает кривую Безье третьего порядка между текущей и заданной конечной точками.|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Создается последовательность кривых Безье третьего порядка и добавляет их в приемник geometry.|  
|[CD2DGeometrySink::AddLine](#addline)|Создает сегмент линии между текущей точкой и заданной конечной точкой и добавляет его в приемник geometry.|  
|[CD2DGeometrySink::AddLines](#addlines)|Создает последовательность линий с использованием указанных точек и добавляет их в приемник geometry.|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Создает кривую Безье второго порядка между текущей и заданной конечной точками.|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Добавляет последовательность сегментов Безье второго как массив в рамках одного вызова.|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Открывает новую фигуру в заданной точке.|  
|[CD2DGeometrySink::Close](#close)|Закрывает геометрического объекта-приемника|  
|[CD2DGeometrySink::EndFigure](#endfigure)|Завершает текущую фигуру; При необходимости закрывает его.|  
|[CD2DGeometrySink::Get](#get)|Возвращает интерфейс ID2D1GeometrySink|  
|[CD2DGeometrySink::IsValid](#isvalid)|Проверяет допустимость приемник geometry|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|Определяет метод, используемый для определения, которые находятся внутри геометрического объекта, описываемого этим приемником геометрии и которые точки находятся за пределами.|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Указывает параметры обводки и соединения для применения к новые сегменты, добавлен в приемник geometry.|  
  
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
  
##  <a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink:: ~ CD2DGeometrySink  
 Деструктор Вызывается при уничтожении объекта D2D geometry приемника.  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="addarc"></a>CD2DGeometrySink::AddArc  
 Добавляет одну дугу по геометрическому пути  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>Параметры  
 `arc`  
 Добавляемый сегмент дуги к рисунку  
  
##  <a name="addbezier"></a>CD2DGeometrySink::AddBezier  
 Создает кривую Безье третьего порядка между текущей и заданной конечной точками.  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Параметры  
 `bezier`  
 Структура, описывающая контрольные точки и конечные точки кривой Безье для добавления.  
  
##  <a name="addbeziers"></a>CD2DGeometrySink::AddBeziers  
 Создается последовательность кривых Безье третьего порядка и добавляет их в приемник geometry.  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Параметры  
 `beziers`  
 Массив сегментов Безье, описывающий кривых Безье для создания. Кривая строится с текущего места в приемник geometry (конечная точка рисуется последнего сегмента или местоположении, заданном свойством BeginFigure) в конечную точку первого сегмента Безье в массиве. Если массив содержит дополнительные сегменты Безье, каждый последующий сегмент Безье использует конечную точку предыдущего сегмента Безье в качестве начальной точки.  
  
##  <a name="addline"></a>CD2DGeometrySink::AddLine  
 Создает сегмент линии между текущей точкой и заданной конечной точкой и добавляет его в приемник geometry.  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Конечная точка линии для рисования.  
  
##  <a name="addlines"></a>CD2DGeometrySink::AddLines  
 Создает последовательность линий с использованием указанных точек и добавляет их в приемник geometry.  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>Параметры  
 `points`  
 Массив одну или несколько точек, описывающие линии для рисования. Линия с текущего места в приемник geometry (конечная точка рисуется последнего сегмента или местоположении, заданном свойством BeginFigure) первой точки в массиве. Если в массиве содержатся дополнительные точки, линия берет начало от первой точки ко второй точке в массиве, с второй точки для третьей и т. д. Массив из последовательности для конечных точек, линий для отрисовки.  
  
##  <a name="addquadraticbezier"></a>CD2DGeometrySink::AddQuadraticBezier  
 Создает кривую Безье второго порядка между текущей и заданной конечной точками.  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Параметры  
 `bezier`  
 Структура, описывающая контрольную точку и конечную точку для добавления квадратичной кривой Безье.  
  
##  <a name="addquadraticbeziers"></a>CD2DGeometrySink::AddQuadraticBeziers  
 Добавляет последовательность сегментов Безье второго как массив в рамках одного вызова.  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Параметры  
 `beziers`  
 Массив из последовательности сегментов Безье второго.  
  
##  <a name="beginfigure"></a>CD2DGeometrySink::BeginFigure  
 Открывает новую фигуру в заданной точке.  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>Параметры  
 `startPoint`  
 Точка, с которого начинается новой фигуры.  
  
 `figureBegin`  
 Ли новая фигура должна быть пустой или заливкой.  
  
##  <a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink  
 Создает объект CD2DGeometrySink из CD2DPathGeometry объекта.  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>Параметры  
 `pathGeometry`  
 Существующий объект CD2DPathGeometry.  
  
##  <a name="close"></a>CD2DGeometrySink::Close  
 Закрывает геометрического объекта-приемника  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — значение FALSE.  
  
##  <a name="endfigure"></a>CD2DGeometrySink::EndFigure  
 Завершает текущую фигуру; При необходимости закрывает его.  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>Параметры  
 `figureEnd`  
 Значение, указывающее, закрыт ли текущей фигуры. Если рисунок закрыт, отображается линия между текущей точкой и заданные BeginFigure начальную точку.  
  
##  <a name="get"></a>CD2DGeometrySink::Get  
 Возвращает интерфейс ID2D1GeometrySink  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1GeometrySink или значение NULL, если объект еще не инициализирован.  
  
##  <a name="isvalid"></a>CD2DGeometrySink::IsValid  
 Проверяет допустимость приемник geometry  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если приемник geometry допустима; в противном случае — значение FALSE.  
  
##  <a name="m_psink"></a>CD2DGeometrySink::m_pSink  
 Указатель на ID2D1GeometrySink.  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::operator ID2D1GeometrySink *  
 Возвращает интерфейс ID2D1GeometrySink  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1GeometrySink или значение NULL, если объект еще не инициализирован.  
  
##  <a name="setfillmode"></a>CD2DGeometrySink::SetFillMode  
 Определяет метод, используемый для определения, которые находятся внутри геометрического объекта, описываемого этим приемником геометрии и которые точки находятся за пределами.  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>Параметры  
 `fillMode`  
 Метод, используемый, чтобы определить, является ли заданная точка частью геометрии.  
  
##  <a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags  
 Указывает параметры обводки и соединения для применения к новые сегменты, добавлен в приемник geometry.  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `vertexFlags`  
 Параметры обводки и соединения для применения к новые сегменты, добавлен в приемник geometry.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
