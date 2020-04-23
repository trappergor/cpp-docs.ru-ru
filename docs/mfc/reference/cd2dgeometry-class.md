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
ms.openlocfilehash: 4727f7b1799604001134ee2f4d2d2e1ce6db87fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754782"
---
# <a name="cd2dgeometry-class"></a>Класс CD2DGeometry

Обертка для ID2D1Geometry.

## <a name="syntax"></a>Синтаксис

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DГеометрия::CD2DГеометрия](#cd2dgeometry)|Строит объект CD2DGeometry.|
|[CD2DГеометрия:: »CD2DГеометрия](#_dtorcd2dgeometry)|Деструктор Вызывается при уничтожении объекта геометрии D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DГеометрия::Прикрепите](#attach)|Прикрепляет существующий интерфейс ресурса к объекту|
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Комбинирует эту геометрию с указанной геометрией и сохраняет результат в ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry:CompareWithGeometry](#comparewithgeometry)|Описывает пересечение между этой геометрией и указанной геометрией. Сравнение выполняется с использованием указанной допуска к уплощению.|
|[CD2DГеометрия:ComputeArea](#computearea)|Вычисляет область геометрии после того, как она была преобразована указанной матрицей и сплющена с помощью указанной допуски.|
|[CD2DGeometry::Вычислить длину](#computelength)|Вычисляет длину геометрии, как будто каждый сегмент был развернут в линию.|
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Вычисляет точку и касательный вектор на указанном расстоянии вдоль геометрии после того, как он был преобразован указанной матрицей и сплющен с помощью указанной допуски.|
|[CD2DGeometry::Destroy](#destroy)|Уничтожает объект CD2DGeometry. (Переопределяет [CD2DРесурс::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DГеометрия::Dэтах](#detach)|Открепите интерфейс ресурса с объекта|
|[CD2DГеометрия::FillContainsPoint](#fillcontainspoint)|Указывает, будет ли область, заполненная геометрией, содержать указанную точку с учетом указанной допуска к выравниванию.|
|[CD2DГеометрия::Получить](#get)|Возвращает интерфейс ID2D1Geometry|
|[CD2DГеометрия::GetBounds](#getbounds)||
|[CD2DГеометрия::GetWidenedBounds](#getwidenedbounds)|Получает границы геометрии после того, как она была расширена указанной шириной и стилем хода и преобразована указанной матрицей.|
|[CD2DГеометрия::Действительно](#isvalid)|Проверка достоверности ресурса (Переопределения [CD2DРесурса:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DGeometry::Outline](#outline)|Вычисляет контур геометрии и записывает результат на ID2D1SimplifiedGeometrySink.|
|[CD2DГеометрия::Упрощение](#simplify)|Создает упрощенную версию геометрии, которая содержит только линии и (по желанию) кубические кривые Безье и записывает результат на ID2D1SimplifiedGeometrySink.|
|[CD2DГеометрия::StrokeContainsPoint](#strokecontainspoint)|Определяет, содержит ли штрих геометрии указанную точку с учетом заданной толщины хода, стиля и преобразования.|
|[CD2DГеометрия::Tessellate](#tessellate)|Создает набор повернутых по часовой стрелке треугольников, покрывающих геометрию после ее преобразования с использованием заданной матрицы и выпрямления с заданным допуском.|
|[CD2DГеометрия::Widen](#widen)|Расширяет геометрию указанным штрихом и записывает результат на ID2D1SimplifiedGeometrySink после того, как он был преобразован указанной матрицей и сплющен с помощью указанной допуски.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometry::оператор ID2D1Геометрия](#operator_id2d1geometry_star)|Возвращает интерфейс ID2D1Geometry|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DГеометрия::m_pGeometry](#m_pgeometry)|Указатель на ID2D1Geometry.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a>CD2DГеометрия:: »CD2DГеометрия

Деструктор Вызывается при уничтожении объекта геометрии D2D.

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a>CD2DГеометрия::Прикрепите

Прикрепляет существующий интерфейс ресурса к объекту

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>Параметры

*pResource*<br/>
Существующий интерфейс ресурса. Не может быть NULL

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a>CD2DГеометрия::CD2DГеометрия

Строит объект CD2DGeometry.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a>CD2DGeometry::CombineWithGeometry

Комбинирует эту геометрию с указанной геометрией и сохраняет результат в ID2D1SimplifiedGeometrySink.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*вхотоза*<br/>
Геометрия, чтобы объединить с этим экземпляром.

*combineMode*<br/>
Тип комбинированной операции для выполнения.

*вхотливыйGeometryTransform*<br/>
Преобразование для применения к вхтотеgeometry перед объединением.

*геометрияСинк*<br/>
Результат работы комбайна.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a>CD2DGeometry:CompareWithGeometry

Описывает пересечение между этой геометрией и указанной геометрией. Сравнение выполняется с использованием указанной допуска к уплощению.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*вхотоза*<br/>
Геометрия для проверки.

*вхотливыйGeometryTransform*<br/>
Преобразование для применения к вхтотеgeometry.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a>CD2DГеометрия:ComputeArea

Вычисляет область геометрии после того, как она была преобразована указанной матрицей и сплющена с помощью указанной допуски.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*мирТрансформен*<br/>
Преобразование для применения к этой геометрии перед вычислением ее области.

*Области*<br/>
Когда этот метод возвращается, содержит указатель на область преобразованной, сплющенный вариант этой геометрии. Для этого параметра необходимо выделить хранилище.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a>CD2DGeometry::Вычислить длину

Вычисляет длину геометрии, как будто каждый сегмент был развернут в линию.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*мирТрансформен*<br/>
Преобразование для применения к геометрии перед расчетом ее длины.

*length*<br/>
Когда этот метод возвращается, содержит указатель на длину геометрии. Для закрытых геометрий длина включает в себя неявное закрытие сегмента. Для этого параметра необходимо выделить хранилище.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a>CD2DGeometry::ComputePointAtLength

Вычисляет точку и касательный вектор на указанном расстоянии вдоль геометрии после того, как он был преобразован указанной матрицей и сплющен с помощью указанной допуски.

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
Расстояние вдоль геометрии точки и касательной, чтобы найти. Если это расстояние меньше 0, этот метод вычисляет первую точку в геометрии. Если это расстояние больше, чем длина геометрии, этот метод вычисляет последнюю точку геометрии.

*мирТрансформен*<br/>
Преобразование для применения к геометрии перед расчетом указанной точки и касательной.

*Точки*<br/>
Расположение на указанном расстоянии вдоль геометрии. Если геометрия пуста, эта точка содержит NaN в качестве значений x и y.

*unitTangentВектор*<br/>
Когда этот метод возвращается, содержит указатель на касательный вектор на указанном расстоянии вдоль геометрии. Если геометрия пуста, этот вектор содержит NaN в качестве значений x и y. Для этого параметра необходимо выделить хранилище.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a>CD2DGeometry::Destroy

Уничтожает объект CD2DGeometry.

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a>CD2DГеометрия::Dэтах

Открепите интерфейс ресурса с объекта

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отдельный интерфейс ресурса.

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a>CD2DГеометрия::FillContainsPoint

Указывает, будет ли область, заполненная геометрией, содержать указанную точку с учетом указанной допуска к выравниванию.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Точка для проверки.

*мирТрансформен*<br/>
Преобразование для применения к геометрии до тестирования на сдерживание.

*Содержит*<br/>
Когда этот метод возвращается, содержит значение bool, которое является правдой, если область, заполненная геометрией, содержит точку; в противном случае, FALSE. Для этого параметра необходимо выделить хранилище.

*уплощениетолерантности*<br/>
Численная точность, с которой рассчитывается точная геометрическая траектория и пересечение пути. Очки, пропускаемые заполнения меньше, чем допуск, по-прежнему считаются внутри. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometryget"></a><a name="get"></a>CD2DГеометрия::Получить

Возвращает интерфейс ID2D1Geometry

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Geometry или NULL, если объект еще не инициализирован.

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a>CD2DГеометрия::GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>Параметры

*мирТрансформен*<br/>
*Границ*

### <a name="return-value"></a>Возвращаемое значение

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a>CD2DГеометрия::GetWidenedBounds

Получает границы геометрии после того, как она была расширена указанной шириной и стилем хода и преобразована указанной матрицей.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*инсультВширина*<br/>
Сумма, с помощью которой можно расширить геометрию, поглаживая ее контур.

*инсультСтиль*<br/>
Стиль штриха, который расширяет геометрию.

*мирТрансформен*<br/>
Преобразование для применения к геометрии после преобразования геометрии и после поглагива геометрии.

*Границ*<br/>
Когда этот метод возвращается, содержит границы расширенной геометрии. Для этого параметра необходимо выделить хранилище.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации данных геометрий. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a>CD2DГеометрия::Действительно

Проверка достоверности ресурса

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a>CD2DГеометрия::m_pGeometry

Указатель на ID2D1Geometry.

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a>CD2DGeometry::оператор ID2D1Геометрия

Возвращает интерфейс ID2D1Geometry

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1Geometry или NULL, если объект еще не инициализирован.

## <a name="cd2dgeometryoutline"></a><a name="outline"></a>CD2DGeometry::Outline

Вычисляет контур геометрии и записывает результат на ID2D1SimplifiedGeometrySink.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*мирТрансформен*<br/>
Преобразование для применения к контуру геометрии.

*геометрияСинк*<br/>
ID2D1SimplifiedGeometrySink, к которому прилагается геометрия преобразована контур.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a>CD2DГеометрия::Упрощение

Создает упрощенную версию геометрии, которая содержит только линии и (по желанию) кубические кривые Безье и записывает результат на ID2D1SimplifiedGeometrySink.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*упрощениеВариант*<br/>
Значение, оцениваево, должна ли упрощенная геометрия содержать кривые.

*мирТрансформен*<br/>
Преобразование для применения к упрощенной геометрии.

*геометрияСинк*<br/>
ID2D1SimplifiedGeometrySink, к которому приложена упрощенная геометрия.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a>CD2DГеометрия::StrokeContainsPoint

Определяет, содержит ли штрих геометрии указанную точку с учетом заданной толщины хода, стиля и преобразования.

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

*Точки*<br/>
Точка для проверки на включение.

*инсультВширина*<br/>
Толщина хода для нанесения.

*инсультСтиль*<br/>
Стиль удара применять.

*мирТрансформен*<br/>
Преобразование для применения к погладил геометрии.

*Содержит*<br/>
Когда этот метод возвращается, содержит значение boolean, установленное к TRUE, если ход геометрии содержит указанную точку; в противном случае, FALSE. Для этого параметра необходимо выделить хранилище.

*уплощениетолерантности*<br/>
Численная точность, с которой рассчитывается точная геометрическая траектория и пересечение пути. Очки, пропускаемые ударом меньше, чем допуск, по-прежнему считаются внутри. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a>CD2DГеометрия::Tessellate

Создает набор повернутых по часовой стрелке треугольников, покрывающих геометрию после ее преобразования с использованием заданной матрицы и выпрямления с заданным допуском.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*мирТрансформен*<br/>
Преобразование для применения к этой геометрии, или NULL.

*tessellationСкук*<br/>
ID2D1TessellationSink, к которому приложено tessellated.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="cd2dgeometrywiden"></a><a name="widen"></a>CD2DГеометрия::Widen

Расширяет геометрию указанным штрихом и записывает результат на ID2D1SimplifiedGeometrySink после того, как он был преобразован указанной матрицей и сплющен с помощью указанной допуски.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Параметры

*инсультВширина*<br/>
Сумма, на которую можно расширить геометрию.

*инсультСтиль*<br/>
Стиль штриха для применения к геометрии, или NULL.

*мирТрансформен*<br/>
Преобразование для применения к геометрии после ее расширения.

*геометрияСинк*<br/>
ID2D1SimplifiedGeometrySink, к которому приложена расширенная геометрия.

*уплощениетолерантности*<br/>
Максимальный диапазон для расстояния между точками кусочно-линейной аппроксимации геометрии. Чем меньше значения, тем точнее результаты и медленнее производится выполнение.

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
