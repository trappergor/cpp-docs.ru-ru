---
title: Класс CD2DGeometry | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51e3c24464ff74ab262cd241dcdce68037d530f9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955106"
---
# <a name="cd2dgeometry-class"></a>Класс CD2DGeometry
Программа-оболочка для ID2D1Geometry.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Создает объект CD2DGeometry.|  
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Деструктор Вызывается при уничтожении объекта geometry D2D.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DGeometry::Attach](#attach)|Присоединяет существующий ресурс интерфейс для объекта|  
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Эта геометрия с заданной геометрий объединяет и сохраняет результат в ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Описывает пересечение между этой и указанным геометрий. Сравнение выполняется с заданным допуском обработки прозрачности.|  
|[CD2DGeometry::ComputeArea](#computearea)|Вычисляется площадь геометрию после ее преобразования с заданной матрицы и выпрямления с заданным допуском.|  
|[CD2DGeometry::ComputeLength](#computelength)|Вычисляет длину геометрии, как если бы каждый сегмент был развернутые в строку.|  
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Вычисляет тангенс и точки вектора на заданном расстоянии вдоль геометрического объекта после ее преобразования с заданной матрицы и выпрямления с заданным допуском.|  
|[CD2DGeometry::destroy](#destroy)|Уничтожает объект CD2DGeometry. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DGeometry::Detach](#detach)|Отсоединяет интерфейса ресурсов из объекта|  
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Указывает ли область, заполняемую геометрию будет содержать указанной точки, заданной обработки заданного допуска.|  
|[CD2DGeometry::Get](#get)|Возвращает интерфейс ID2D1Geometry|  
|[CD2DGeometry::GetBounds](#getbounds)||  
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Возвращает границы геометрического объекта после его расширенная объектом stroke указанного ширину и стиль и преобразовать заданную матрицу.|  
|[CD2DGeometry::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DGeometry::Outline](#outline)|Вычисляет структуры геометрии и записывает результат ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::Simplify](#simplify)|Создает упрощенную версию, содержащий только линий и кривых Безье (необязательно) третьего и записывает результат ID2D1SimplifiedGeometrySink геометрии.|  
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Определяет, содержит ли обводки геометрии указанной точки, заданной толщину обводки указанного, стиль и преобразования.|  
|[CD2DGeometry::Tessellate](#tessellate)|Создает набор повернутых по часовой стрелке треугольников, покрывающих геометрию после ее преобразования с использованием заданной матрицы и выпрямления с заданным допуском.|  
|[CD2DGeometry::Widen](#widen)|Расширяет геометрического объекта с указанным штриха и записывает результат ID2D1SimplifiedGeometrySink после ее преобразования с заданной матрицы и выпрямления с заданным допуском.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|Возвращает интерфейс ID2D1Geometry|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|Указатель на ID2D1Geometry.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DGeometry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometry"></a>  CD2DGeometry:: ~ CD2DGeometry  
 Деструктор Вызывается при уничтожении объекта geometry D2D.  
  
```  
virtual ~CD2DGeometry();
```  
  
##  <a name="attach"></a>  CD2DGeometry::Attach  
 Присоединяет существующий ресурс интерфейс для объекта  
  
```  
void Attach(ID2D1Geometry* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 *pResource*  
 Интерфейс существующего ресурса. Не может иметь значение NULL  
  
##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry  
 Создает объект CD2DGeometry.  
  
```  
CD2DGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *pParentTarget*  
 Указатель на целевой объект отрисовки.  
  
 *bAutoDestroy*  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry  
 Эта геометрия с заданной геометрий объединяет и сохраняет результат в ID2D1SimplifiedGeometrySink.  
  
```  
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,  
    D2D1_COMBINE_MODE combineMode,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *inputGeometry*  
 Geometry для объединения с данным экземпляром.  
  
 *combineMode*  
 Тип выполняемой операции объединения.  
  
 *inputGeometryTransform*  
 Преобразование для применения к inputGeometry до объединения.  
  
 *geometrySink*  
 Результат операции объединения.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрических объектов. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry  
 Описывает пересечение между этой и указанным геометрий. Сравнение выполняется с заданным допуском обработки прозрачности.  
  
```  
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *inputGeometry*  
 Геометрия для проверки.  
  
 *inputGeometryTransform*  
 Преобразование для применения к inputGeometry.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрических объектов. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="computearea"></a>  CD2DGeometry::ComputeArea  
 Вычисляется площадь геометрию после ее преобразования с заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& area,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *worldTransform*  
 Преобразования для применения этого geometry перед вычислением его области.  
  
 *Область*  
 По возвращении из этого метода содержит указатель на область преобразованный, сведенное версии эта геометрия. Для этого параметра необходимо выделить хранилище.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрии. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="computelength"></a>  CD2DGeometry::ComputeLength  
 Вычисляет длину геометрии, как если бы каждый сегмент был развернутые в строку.  
  
```  
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& length,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *worldTransform*  
 Преобразование, применяемое к геометрии до вычисления его длину.  
  
 *length*  
 По возвращении из этого метода содержит указатель на длину геометрии. Для закрытых фигур включает сегмент неявное закрытие. Для этого параметра необходимо выделить хранилище.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрии. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength  
 Вычисляет тангенс и точки вектора на заданном расстоянии вдоль геометрического объекта после ее преобразования с заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL ComputePointAtLength(
    FLOAT length,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DPointF& point,  
    CD2DPointF& unitTangentVector,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *length*  
 Расстояние вдоль geometry точки и тангенс для поиска. Если это расстояние меньше затем 0, этот метод вычисляет первой точки геометрии. Если это расстояние больше, чем длина геометрии, этот метод вычисляет последнюю точку геометрии.  
  
 *worldTransform*  
 Преобразование, применяемое к геометрии до расчета заданной точки и тангенс.  
  
 *Точка*  
 Расположение на заданном расстоянии вдоль геометрического объекта. Если геометрия не указаны, эта точка содержит NaN как x и y значения.  
  
 *unitTangentVector*  
 По возвращении из этого метода содержит указатель касательной вектор на заданное расстояние вдоль геометрического объекта. Если геометрия пуста, данный вектор содержит NaN как x и y значения. Для этого параметра необходимо выделить хранилище.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрии. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="destroy"></a>  CD2DGeometry::destroy  
 Уничтожает объект CD2DGeometry.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DGeometry::Detach  
 Отсоединяет интерфейса ресурсов из объекта  
  
```  
ID2D1Geometry* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint  
 Указывает ли область, заполняемую геометрию будет содержать указанной точки, заданной обработки заданного допуска.  
  
```  
BOOL FillContainsPoint(
    CD2DPointF point,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *Точка*  
 Точки для проверки.  
  
 *worldTransform*  
 Преобразование, применяемое к геометрии до тестирования для включения.  
  
 *Содержит*  
 При возвращении этого метода содержит логическое значение, равное TRUE, если область, заполняемую геометрия содержит точку; в противном случае — значение FALSE. Для этого параметра необходимо выделить хранилище.  
  
 *flatteningTolerance*  
 Числовой точности, с которым точный геометрического пути и пути пересечения вычисляется. Внутри по-прежнему считаются точек отсутствующих меньше допустимого отклонения заполнения. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="get"></a>  CD2DGeometry::Get  
 Возвращает интерфейс ID2D1Geometry  
  
```  
ID2D1Geometry* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Geometry или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getbounds"></a>  CD2DGeometry::GetBounds  
  
```   
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,  
CD2DRectF& bounds) const; 
```  
  
### <a name="parameters"></a>Параметры  
 *worldTransform*  
 *границы*  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds  
 Возвращает границы геометрического объекта после его расширенная объектом stroke указанного ширину и стиль и преобразовать заданную матрицу.  
  
```  
BOOL GetWidenedBounds(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DRectF& bounds,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *strokeWidth*  
 Величина, на которую расширить область геометрии, срезом его контура.  
  
 *strokeStyle*  
 Стиль штриха, который расширяется геометрии.  
  
 *worldTransform*  
 Преобразование, выполняемое геометрии после преобразования геометрии и был нарисован геометрии.  
  
 *границы*  
 По возвращении из этого метода содержит границы расширил геометрии. Для этого параметра необходимо выделить хранилище.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрических объектов. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="isvalid"></a>  CD2DGeometry::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_pgeometry"></a>  CD2DGeometry::m_pGeometry  
 Указатель на ID2D1Geometry.  
  
```  
ID2D1Geometry* m_pGeometry;  
```  
  
##  <a name="operator_id2d1geometry_star"></a>  CD2DGeometry::operator ID2D1Geometry *  
 Возвращает интерфейс ID2D1Geometry  
  
```  
operator ID2D1Geometry*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Geometry или значение NULL, если объект еще не инициализирован.  
  
##  <a name="outline"></a>  CD2DGeometry::Outline  
 Вычисляет структуры геометрии и записывает результат ID2D1SimplifiedGeometrySink.  
  
```  
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *worldTransform*  
 Преобразование для применения к структуре geometry.  
  
 *geometrySink*  
 ID2D1SimplifiedGeometrySink, к которому добавляется структуры преобразованный geometry.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрии. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="simplify"></a>  CD2DGeometry::Simplify  
 Создает упрощенную версию, содержащий только линий и кривых Безье (необязательно) третьего и записывает результат ID2D1SimplifiedGeometrySink геометрии.  
  
```  
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *simplificationOption*  
 Значение, указывающее, содержат ли упрощенной геометрии кривых.  
  
 *worldTransform*  
 Преобразование, применяемое к упрощенной геометрии.  
  
 *geometrySink*  
 ID2D1SimplifiedGeometrySink, к которому добавляется упрощенной геометрии.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрии. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint  
 Определяет, содержит ли обводки геометрии указанной точки, заданной толщину обводки указанного, стиль и преобразования.  
  
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
 *Точка*  
 Точка для проверки на включение.  
  
 *strokeWidth*  
 Толщина штриха, вступили в силу.  
  
 *strokeStyle*  
 Стиль штриха, вступили в силу.  
  
 *worldTransform*  
 Преобразование, применяемое к обведенные геометрии.  
  
 *Содержит*  
 По возвращении из этого метода содержит логическое значение, значение TRUE, если обводки геометрии содержит указанную точку; в противном случае — значение FALSE. Для этого параметра необходимо выделить хранилище.  
  
 *flatteningTolerance*  
 Числовой точности, с которым точный геометрического пути и пути пересечения вычисляется. Внутри по-прежнему считаются точек отсутствующих штриха меньше допустимого отклонения. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="tessellate"></a>  CD2DGeometry::Tessellate  
 Создает набор повернутых по часовой стрелке треугольников, покрывающих геометрию после ее преобразования с использованием заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1TessellationSink* tessellationSink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *worldTransform*  
 Преобразование геометрии, или значение NULL.  
  
 *tessellationSink*  
 ID2D1TessellationSink, к которому тесселированных добавляется.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрии. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="widen"></a>  CD2DGeometry::Widen  
 Расширяет геометрического объекта с указанным штриха и записывает результат ID2D1SimplifiedGeometrySink после ее преобразования с заданной матрицы и выпрямления с заданным допуском.  
  
```  
BOOL Widen(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *strokeWidth*  
 Величина, на которую расширить область геометрии.  
  
 *strokeStyle*  
 Стиль штриха, чтобы применить geometry, или значение NULL.  
  
 *worldTransform*  
 Преобразование, применяемое к геометрии после расширяющих его.  
  
 *geometrySink*  
 ID2D1SimplifiedGeometrySink, к которому добавляется расширил geometry.  
  
 *flatteningTolerance*  
 Максимальный диапазон для расстояния между точками в аппроксимации геометрии. Небольшие значения дать более точные результаты, однако к более медленному выполнению.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
