---
title: "Класс CD2DGeometry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGeometry
- afxrendertarget/CD2DGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometry class
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
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
ms.openlocfilehash: 948b2e2154259557e3a52c2045586cffce2a16f8
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgeometry-class"></a>Класс CD2DGeometry
Программа-оболочка для ID2D1Geometry.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Создает объект CD2DGeometry.|  
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Деструктор Вызывается при уничтожении объекта geometry D2D.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometry::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Объединяет этот geometry с заданной геометрий и сохраняет результат в ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Описывает пересечение этого и заданной геометрий. Сравнение выполняется с помощью заданного допуска уплощения.|  
|[CD2DGeometry::ComputeArea](#computearea)|Вычисляет области геометрического объекта после его преобразования, заданной матрицы и выпрямления с заданным допуском.|  
|[CD2DGeometry::ComputeLength](#computelength)|Вычисляет длину объекта geometry, как если бы каждый сегмент, развернутые в строку.|  
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Вычисляет тангенс и точки вектора расстояния вдоль геометрического объекта после его преобразования, заданной матрицы и выпрямления с заданным допуском.|  
|[CD2DGeometry::destroy](#destroy)|Уничтожает объект CD2DGeometry. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DGeometry::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Указывает, будет ли область, заполняемую geometry содержит указанной точки, заданной с заданной погрешностью уплощения.|  
|[CD2DGeometry::Get](#get)|Возвращает интерфейс ID2D1Geometry|  
|[CD2DGeometry::GetBounds](#getbounds)||  
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Возвращает границы геометрии после расширяются по указанным stroke ширину и стиль и преобразовать заданную матрицу.|  
|[CD2DGeometry::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DGeometry::Outline](#outline)|Вычисляет очертания объекта geometry и записывает результаты в ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::Simplify](#simplify)|Создание упрощенной версии геометрического объекта, содержащий только линий и кривых Безье третьего (при необходимости) и записывает результаты в ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Определяет, содержит ли обводки геометрии указанной точки, заданной толщина штриха указанного, стиль и преобразования.|  
|[CD2DGeometry::Tessellate](#tessellate)|Создает набор по часовой стрелке треугольников, покрывающих геометрию после его преобразования с использованием заданной матрицы и выпрямления с заданным допуском.|  
|[CD2DGeometry::Widen](#widen)|Расширяет геометрического объекта с указанным штриха и записывает результат ID2D1SimplifiedGeometrySink после его преобразования, заданной матрицы и выпрямления с заданным допуском.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|Возвращает интерфейс ID2D1Geometry|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|Указатель на ID2D1Geometry.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DGeometry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dgeometrya--cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a>CD2DGeometry:: ~ CD2DGeometry  
 Деструктор Вызывается при уничтожении объекта geometry D2D.  
  
```  
virtual ~CD2DGeometry();
```  
  
##  <a name="a-nameattacha--cd2dgeometryattach"></a><a name="attach"></a>CD2DGeometry::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1Geometry* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="a-namecd2dgeometrya--cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a>CD2DGeometry::CD2DGeometry  
 Создает объект CD2DGeometry.  
  
```  
CD2DGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
##  <a name="a-namecombinewithgeometrya--cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a>CD2DGeometry::CombineWithGeometry  
 Объединяет этот geometry с заданной геометрий и сохраняет результат в ID2D1SimplifiedGeometrySink.  
  
```  
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,  
    D2D1_COMBINE_MODE combineMode,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `inputGeometry`  
 Геометрия для комбинирования с данным экземпляром.  
  
 `combineMode`  
 Тип выполняемой операции объединения.  
  
 `inputGeometryTransform`  
 Преобразование для применения к inputGeometry до объединения.  
  
 `geometrySink`  
 Результат операции объединения.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namecomparewithgeometrya--cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a>CD2DGeometry::CompareWithGeometry  
 Описывает пересечение этого и заданной геометрий. Сравнение выполняется с помощью заданного допуска уплощения.  
  
```  
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `inputGeometry`  
 Геометрия для проверки.  
  
 `inputGeometryTransform`  
 Преобразование для применения к inputGeometry.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namecomputeareaa--cd2dgeometrycomputearea"></a><a name="computearea"></a>CD2DGeometry::ComputeArea  
 Вычисляет области геометрического объекта после его преобразования, заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& area,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `worldTransform`  
 Преобразования для применения этого geometry перед вычислением его области.  
  
 `area`  
 При возвращении данного метода содержит указатель на область преобразованные плоский версией этого geometry. Для этого параметра необходимо выделить хранилище.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namecomputelengtha--cd2dgeometrycomputelength"></a><a name="computelength"></a>CD2DGeometry::ComputeLength  
 Вычисляет длину объекта geometry, как если бы каждый сегмент, развернутые в строку.  
  
```  
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& length,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `worldTransform`  
 Преобразование, применяемое к геометрии до вычисления его длину.  
  
 `length`  
 При возвращении данного метода содержит указатель на длину геометрии. Для закрытых геометрические объекты длина включает неявные закрытия сегмента. Для этого параметра необходимо выделить хранилище.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namecomputepointatlengtha--cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a>CD2DGeometry::ComputePointAtLength  
 Вычисляет тангенс и точки вектора расстояния вдоль геометрического объекта после его преобразования, заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL ComputePointAtLength(
    FLOAT length,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DPointF& point,  
    CD2DPointF& unitTangentVector,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `length`  
 Расстояние вдоль геометрию точки и тангенс для поиска. Если это расстояние меньше затем 0, этот метод вычисляет первой точки геометрического объекта. Если это расстояние превышает длину геометрии, этот метод вычисляет последнюю точку геометрии.  
  
 `worldTransform`  
 Преобразование, применяемое к геометрии перед расчетом указанной точки и тангенс.  
  
 `point`  
 Расположение на заданном расстоянии вдоль геометрического объекта. Если данная геометрия пуста, эта точка содержит NaN как x и y значения.  
  
 `unitTangentVector`  
 При возвращении данного метода содержит указатель касания вектора расстояния вдоль геометрического объекта. Если данная геометрия пуста, этот вектор содержит NaN как x и y значения. Для этого параметра необходимо выделить хранилище.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namedestroya--cd2dgeometrydestroy"></a><a name="destroy"></a>CD2DGeometry::destroy  
 Уничтожает объект CD2DGeometry.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dgeometrydetach"></a><a name="detach"></a>CD2DGeometry::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1Geometry* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="a-namefillcontainspointa--cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a>CD2DGeometry::FillContainsPoint  
 Указывает, будет ли область, заполняемую geometry содержит указанной точки, заданной с заданной погрешностью уплощения.  
  
```  
BOOL FillContainsPoint(
    CD2DPointF point,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Точка для проверки.  
  
 `worldTransform`  
 Преобразование к геометрии до тестирования для включения.  
  
 `contains`  
 При возвращении данного метода содержит логическое значение, равное TRUE, если область, заполняемую геометрического объекта содержит точку; в противном случае — значение FALSE. Для этого параметра необходимо выделить хранилище.  
  
 `flatteningTolerance`  
 Числовой точности, с которым точный геометрического пути и пересечение путь вычисляется. Отсутствие заливки, меньше допустимого отклонения точек по-прежнему считаются внутри. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namegeta--cd2dgeometryget"></a><a name="get"></a>CD2DGeometry::Get  
 Возвращает интерфейс ID2D1Geometry  
  
```  
ID2D1Geometry* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Geometry или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namegetboundsa--cd2dgeometrygetbounds"></a><a name="getbounds"></a>CD2DGeometry::GetBounds  
  
```   
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,  
CD2DRectF& bounds) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `worldTransform`  
 `bounds`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-namegetwidenedboundsa--cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a>CD2DGeometry::GetWidenedBounds  
 Возвращает границы геометрии после расширяются по указанным stroke ширину и стиль и преобразовать заданную матрицу.  
  
```  
BOOL GetWidenedBounds(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DRectF& bounds,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strokeWidth`  
 Величина, на которую расширить область геометрии, Обводка ее структуры.  
  
 `strokeStyle`  
 Стиль штриха, который расширяется геометрии.  
  
 `worldTransform`  
 Преобразование для применения к геометрии, после преобразования геометрии и был нарисован геометрии.  
  
 `bounds`  
 При возвращении данного метода содержит границы расширенный геометрии. Для этого параметра необходимо выделить хранилище.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-nameisvalida--cd2dgeometryisvalid"></a><a name="isvalid"></a>CD2DGeometry::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="a-namempgeometrya--cd2dgeometrympgeometry"></a><a name="m_pgeometry"></a>CD2DGeometry::m_pGeometry  
 Указатель на ID2D1Geometry.  
  
```  
ID2D1Geometry* m_pGeometry;  
```  
  
##  <a name="a-nameoperatorid2d1geometrystara--cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a>CD2DGeometry::operator ID2D1Geometry *  
 Возвращает интерфейс ID2D1Geometry  
  
```  
operator ID2D1Geometry*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Geometry или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-nameoutlinea--cd2dgeometryoutline"></a><a name="outline"></a>CD2DGeometry::Outline  
 Вычисляет очертания объекта geometry и записывает результаты в ID2D1SimplifiedGeometrySink.  
  
```  
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `worldTransform`  
 Преобразование для применения к структуре geometry.  
  
 `geometrySink`  
 ID2D1SimplifiedGeometrySink, к которому добавляется структуры преобразованной геометрии.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namesimplifya--cd2dgeometrysimplify"></a><a name="simplify"></a>CD2DGeometry::Simplify  
 Создание упрощенной версии геометрического объекта, содержащий только линий и кривых Безье третьего (при необходимости) и записывает результаты в ID2D1SimplifiedGeometrySink.  
  
```  
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `simplificationOption`  
 Значение, указывающее, содержат ли упрощенный geometry кривых.  
  
 `worldTransform`  
 Преобразование для применения к упрощенный геометрии.  
  
 `geometrySink`  
 ID2D1SimplifiedGeometrySink, к которому добавляется упрощенный geometry.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namestrokecontainspointa--cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a>CD2DGeometry::StrokeContainsPoint  
 Определяет, содержит ли обводки геометрии указанной точки, заданной толщина штриха указанного, стиль и преобразования.  
  
```  
BOOL StrokeContainsPoint(
    CD2DPointF point,  
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `point`  
 Точка для проверки на включение.  
  
 `strokeWidth`  
 Толщина штриха вступили в силу.  
  
 `strokeStyle`  
 Стиль штриха, вступили в силу.  
  
 `worldTransform`  
 Преобразование для применения к обведенные геометрии.  
  
 `contains`  
 При возвращении данного метода содержит логическое значение, значение TRUE, если обводки геометрии содержит указанную точку; в противном случае — значение FALSE. Для этого параметра необходимо выделить хранилище.  
  
 `flatteningTolerance`  
 Числовой точности, с которым точный геометрического пути и пересечение путь вычисляется. Отсутствует штриха, меньше допустимого отклонения точек по-прежнему считаются внутри. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-nametessellatea--cd2dgeometrytessellate"></a><a name="tessellate"></a>CD2DGeometry::Tessellate  
 Создает набор по часовой стрелке треугольников, покрывающих геометрию после его преобразования с использованием заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1TessellationSink* tessellationSink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `worldTransform`  
 Преобразование geometry, или значение NULL.  
  
 `tessellationSink`  
 ID2D1TessellationSink, к которому мозаичное добавляется.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namewidena--cd2dgeometrywiden"></a><a name="widen"></a>CD2DGeometry::Widen  
 Расширяет геометрического объекта с указанным штриха и записывает результат ID2D1SimplifiedGeometrySink после его преобразования, заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL Widen(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strokeWidth`  
 Величина, на которую расширить область геометрии.  
  
 `strokeStyle`  
 Стиль штриха, чтобы применить geometry, или значение NULL.  
  
 `worldTransform`  
 Преобразование, применяемое к геометрии после его расширения.  
  
 `geometrySink`  
 ID2D1SimplifiedGeometrySink, к которому добавляется расширенный geometry.  
  
 `flatteningTolerance`  
 Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения выдать более точные результаты, но привести к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

