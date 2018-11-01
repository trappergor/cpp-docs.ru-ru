---
title: Класс CD2DGeometry
ms.date: 11/04/2016
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
ms.openlocfilehash: 929926129ddee0efdee4f1b02494b503755811d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610695"
---
# <a name="cd2dgeometry-class"></a>Класс CD2DGeometry

Оболочка для ID2D1Geometry.

## <a name="syntax"></a>Синтаксис

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Создает объект CD2DGeometry.|
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Деструктор Вызывается при уничтожении объекта geometry D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometry::Attach](#attach)|Присоединяет существующий интерфейс ресурса к объекту|
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Объединяет данной геометрии с заданной геометрий и сохраняет результат в ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Описывает пересечение между данной геометрии и заданной геометрий. Сравнение выполняется с заданным допуском уплощения.|
|[CD2DGeometry::ComputeArea](#computearea)|Вычисляется площадь геометрию, после ее преобразование с заданной матрицы и выпрямления с заданным допуском.|
|[CD2DGeometry::ComputeLength](#computelength)|Вычисляет длину геометрии, как если бы каждый сегмент было развернутые в строку.|
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Вычисляет точку и тангенс вектора на заданном расстоянии вдоль геометрического объекта, после ее преобразование с заданной матрицы и выпрямления с заданным допуском.|
|[CD2DGeometry::destroy](#destroy)|Уничтожает объект CD2DGeometry. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DGeometry::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Указывает, будет ли область, заполняемую геометрии содержать указанной точки, заданной уплощения заданного допуска.|
|[CD2DGeometry::Get](#get)|Возвращает интерфейс ID2D1Geometry|
|[CD2DGeometry::GetBounds](#getbounds)||
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Получает границы геометрического объекта, после того как расширенная объектом заданный штрих ширину и стиль и преобразование с заданной матрицы.|
|[CD2DGeometry::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DGeometry::Outline](#outline)|Вычисляет контур геометрии и записывает результат ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::Simplify](#simplify)|Создание упрощенной версии объекта geometry, который содержит только линий и кривых Безье (при необходимости) третьего и записывает результат в ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Определяет, содержит ли Обводка геометрии указанной точки, заданной толщина штриха указанного, стиль и преобразования.|
|[CD2DGeometry::Tessellate](#tessellate)|Создает набор повернутых по часовой стрелке треугольников, покрывающих геометрию после ее преобразования с помощью заданной матрицы и выпрямления с заданным допуском.|
|[CD2DGeometry::Widen](#widen)|Расширяет геометрии, заданный штрих и записывает результат ID2D1SimplifiedGeometrySink после ее преобразование с заданной матрицы и выпрямления с заданным допуском.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|Возвращает интерфейс ID2D1Geometry|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
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

Присоединяет существующий интерфейс ресурса к объекту

```
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурсов. Не может иметь значение NULL

##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry

Создает объект CD2DGeometry.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на целевой объект отрисовки.

*bAutoDestroy*<br/>
Указывает, что объект будет уничтожен владельца (pParentTarget).

##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry

Объединяет данной геометрии с заданной геометрий и сохраняет результат в ID2D1SimplifiedGeometrySink.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*inputGeometry*<br/>
Геометрия для комбинирования с данным экземпляром.

*combineMode*<br/>
Тип выполняемой операции объединения.

*inputGeometryTransform*<br/>
Преобразование для применения к inputGeometry перед объединением.

*geometrySink*<br/>
Результат операции объединения.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry

Описывает пересечение между данной геометрии и заданной геометрий. Сравнение выполняется с заданным допуском уплощения.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*inputGeometry*<br/>
Геометрия для проверки.

*inputGeometryTransform*<br/>
Преобразование для применения к inputGeometry.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="computearea"></a>  CD2DGeometry::ComputeArea

Вычисляется площадь геометрию, после ее преобразование с заданной матрицы и выпрямления с заданным допуском.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*worldTransform*<br/>
Преобразование для применения к данной геометрии перед вычислением его области.

*Область*<br/>
При возвращении данного метода содержит указатель на область, преобразованный, сведенное версию данной геометрии. Для этого параметра необходимо выделить хранилище.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="computelength"></a>  CD2DGeometry::ComputeLength

Вычисляет длину геометрии, как если бы каждый сегмент было развернутые в строку.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*worldTransform*<br/>
Преобразование применяется к данной геометрии, до расчета его длины.

*length*<br/>
При возвращении данного метода содержит указатель на длину геометрии. Для закрытых контуров длина включает сегменту неявное закрытие. Для этого параметра необходимо выделить хранилище.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength

Вычисляет точку и тангенс вектора на заданном расстоянии вдоль геометрического объекта, после ее преобразование с заданной матрицы и выпрямления с заданным допуском.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*length*<br/>
Расстояние вдоль геометрии точки и тангенс для поиска. Если это расстояние меньше затем 0, этот метод вычисляет первой точки геометрии. Если это расстояние больше, чем длина геометрии, этот метод вычисляет последнюю точку геометрии.

*worldTransform*<br/>
Преобразование применяется к данной геометрии, до расчета заданной точки и тангенс.

*точка*<br/>
Расположение на заданном расстоянии вдоль геометрического объекта. Если данная геометрия пуста, эта точка содержат NaN в виде x и y значения.

*unitTangentVector*<br/>
При возвращении данного метода содержит указатель на касательный вектор на заданном расстоянии вдоль геометрического объекта. Если данная геометрия пуста, данный вектор содержит NaN как x и y значения. Для этого параметра необходимо выделить хранилище.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="destroy"></a>  CD2DGeometry::destroy

Уничтожает объект CD2DGeometry.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DGeometry::Detach

Отсоединяет интерфейс ресурса из объекта

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс отсоединенных ресурсов.

##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint

Указывает, будет ли область, заполняемую геометрии содержать указанной точки, заданной уплощения заданного допуска.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*точка*<br/>
Точка для проверки.

*worldTransform*<br/>
Преобразование применяется к данной геометрии до тестирования для включения.

*Содержит*<br/>
При возвращении данного метода содержит логическое значение, равное TRUE, если область, заполняемую геометрия содержит точку. в противном случае — значение FALSE. Для этого параметра необходимо выделить хранилище.

*flatteningTolerance*<br/>
Числовой точности, с которым точное геометрического пути и пересечения путь вычисляется. Точки, отсутствующий заливка с меньшим, чем допуск по-прежнему считаются внутри. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

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

*worldTransform*<br/>
*Границы*

### <a name="return-value"></a>Возвращаемое значение

##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds

Получает границы геометрического объекта, после того как расширенная объектом заданный штрих ширину и стиль и преобразование с заданной матрицы.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*strokeWidth*<br/>
Величина, на которую должна расширять по Обводка его контура геометрии.

*strokeStyle*<br/>
Стиль штрих, который может быть расширен геометрии.

*worldTransform*<br/>
Преобразование для применения к данной геометрии, после того, как преобразовать геометрии и был нарисован геометрии.

*Границы*<br/>
При возвращении данного метода содержит границы расширенными геометрического объекта. Для этого параметра необходимо выделить хранилище.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

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

Вычисляет контур геометрии и записывает результат ID2D1SimplifiedGeometrySink.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*worldTransform*<br/>
Преобразование для контура геометрии.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink, к которому добавляется преобразованные контура геометрии.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="simplify"></a>  CD2DGeometry::Simplify

Создание упрощенной версии объекта geometry, который содержит только линий и кривых Безье (при необходимости) третьего и записывает результат в ID2D1SimplifiedGeometrySink.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*simplificationOption*<br/>
Значение, указывающее, содержат ли упрощенной геометрии кривых.

*worldTransform*<br/>
Преобразование для применения к упрощенной геометрии.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink, к которому добавляется упрощенной геометрии.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint

Определяет, содержит ли Обводка геометрии указанной точки, заданной толщина штриха указанного, стиль и преобразования.

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

*точка*<br/>
Точка для проверки на включение.

*strokeWidth*<br/>
Толщина штриха для применения.

*strokeStyle*<br/>
Стиль штриха для применения.

*worldTransform*<br/>
Преобразование для применения к обводки геометрии.

*Содержит*<br/>
При возвращении данного метода содержит логическое значение присвоено значение TRUE, если обводки геометрии содержит указанную точку; в противном случае — значение FALSE. Для этого параметра необходимо выделить хранилище.

*flatteningTolerance*<br/>
Числовой точности, с которым точное геометрического пути и пересечения путь вычисляется. Точки, отсутствующий штрих с меньшим, чем допуск по-прежнему считаются внутри. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="tessellate"></a>  CD2DGeometry::Tessellate

Создает набор повернутых по часовой стрелке треугольников, покрывающих геометрию после ее преобразования с помощью заданной матрицы и выпрямления с заданным допуском.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*worldTransform*<br/>
Преобразование для применения к этим geometry, или значение NULL.

*tessellationSink*<br/>
ID2D1TessellationSink, к которому мозаичное добавляется.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="widen"></a>  CD2DGeometry::Widen

Расширяет геометрии, заданный штрих и записывает результат ID2D1SimplifiedGeometrySink после ее преобразование с заданной матрицы и выпрямления с заданным допуском.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*strokeWidth*<br/>
Величина, на которую должна расширять геометрии.

*strokeStyle*<br/>
Стиль штриха для применения к геометрии или значение NULL.

*worldTransform*<br/>
Применяется к данной геометрии, после его расширяющее преобразование.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink, к которому добавляется расширенными геометрии.

*flatteningTolerance*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Меньшие значения точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
