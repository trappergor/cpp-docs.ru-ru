---
title: Класс CD2DGeometrySink
ms.date: 11/04/2016
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
ms.openlocfilehash: cb51c7b11f75debece61105bf20a201b6eab80a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369242"
---
# <a name="cd2dgeometrysink-class"></a>Класс CD2DGeometrySink

Обертка для ID2D1GeometrySink.

## <a name="syntax"></a>Синтаксис

```
class CD2DGeometrySink;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|Строит объект CD2DGeometrySink с объекта CD2DPathGeometry.|
|[CD2DGeometrySink:: »CD2DGeometrySink](#_dtorcd2dgeometrysink)|Деструктор Вызывается при уничтожении объекта раковины геометрии D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometrySink::AddArc](#addarc)|Добавляет одну дугу к геометрии пути|
|[CD2DGeometrySink::AddBezier](#addbezier)|Создает кривую Безье третьего порядка между текущей и заданной конечной точками.|
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Создает последовательность кубических кривых Безье и добавляет их в раковину геометрии.|
|[CD2DGeometrySink::AddLine](#addline)|Создает сегмент линии между текущей точкой и указанной конечной точкой и добавляет ее в раковину геометрии.|
|[CD2DGeometrySIn::AddLines](#addlines)|Создает последовательность линий, используя указанные точки и добавляет их в раковину геометрии.|
|[CD2DGeometrySink::AddquadraticBezier](#addquadraticbezier)|Создает кривую Безье второго порядка между текущей и заданной конечной точками.|
|[CD2DGeometrySink:AddquadraticBeziers](#addquadraticbeziers)|Добавляет последовательность сегментов квадрата Безье в качестве массива в одном вызове.|
|[CD2DGeometryS': БегинаРисунка](#beginfigure)|Запускает новую фигуру в указанной точке.|
|[CD2DGeometrySin::Закрыть](#close)|Закрывает раковину геометрии|
|[CD2DGeometrySink::EndFigure](#endfigure)|Завершает текущую цифру; дополнительно, закрывает его.|
|[CD2DGeometryS': Получить](#get)|Возвращает интерфейс ID2D1GeometrySink|
|[CD2DGeometrySink::IsValid](#isvalid)|Проверка достоверности геометрии раковины|
|[CD2DGeometrySink::SetFillMode](#setfillmode)|Определяет метод, используемый для определения того, какие точки находятся внутри геометрии, описанной этой раковиной геометрии, и какие точки находятся снаружи.|
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Обрабражает параметры штриха и соединения, которые будут применяться к новым сегментам, добавленным к раковине геометрии.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometrySink::оператор ID2D1GeometrySink](#operator_id2d1geometrysink_star)|Возвращает интерфейс ID2D1GeometrySink|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DGeometryS:::m_pSink](#m_psink)|Указатель на ID2D1GeometrySink.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CD2DGeometrySink`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink:: »CD2DGeometrySink

Деструктор Вызывается при уничтожении объекта раковины геометрии D2D.

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a>CD2DGeometrySink::AddArc

Добавляет одну дугу к геометрии пути

```
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>Параметры

*Дуги*<br/>
Сегмент дуги для добавления к рисунку

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a>CD2DGeometrySink::AddBezier

Создает кривую Безье третьего порядка между текущей и заданной конечной точками.

```
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Параметры

*Безье*<br/>
Структура, описывающая точки управления и конечную точку кривой Безье для добавления.

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a>CD2DGeometrySink::AddBeziers

Создает последовательность кубических кривых Безье и добавляет их в раковину геометрии.

```
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Параметры

*Безье*<br/>
Массив сегментов Безье, описывающий кривые Безье для создания. Кривая нарисована из текущей точки раковины геометрии (конечная точка последнего сегмента или местоположения, указанного BeginFigure) до конечной точки первого сегмента Безье в массиве. если массив содержит дополнительные сегменты Bezier, каждый последующий сегмент Bezier использует конечную точку предыдущего сегмента Bezier в качестве отправной точки.

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a>CD2DGeometrySink::AddLine

Создает сегмент линии между текущей точкой и указанной конечной точкой и добавляет ее в раковину геометрии.

```
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Конечная точка линии для рисования.

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a>CD2DGeometrySIn::AddLines

Создает последовательность линий, используя указанные точки и добавляет их в раковину геометрии.

```
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Массив одного или нескольких точек, описывающие линии для рисования. Линия нарисована из текущей точки раковины геометрии (конечная точка последнего сегмента или местоположения, указанного BeginFigure) до первой точки массива. если массив содержит дополнительные точки, то линия нарисована от первой точки до второй точки массива, от второй точки до третьей точки и так далее. Массив последовательности конечных точек линий для рисования.

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a>CD2DGeometrySink::AddquadraticBezier

Создает кривую Безье второго порядка между текущей и заданной конечной точками.

```
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Параметры

*Безье*<br/>
Структура, описывающая контрольную точку и конечную точку квадратной кривой Безье, чтобы добавить.

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a>CD2DGeometrySink:AddquadraticBeziers

Добавляет последовательность сегментов квадрата Безье в качестве массива в одном вызове.

```
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Параметры

*Безье*<br/>
Массив последовательности сегментов квадратного Безье.

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a>CD2DGeometryS': БегинаРисунка

Запускает новую фигуру в указанной точке.

```
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>Параметры

*startPoint*<br/>
Точка, с которой начать новую фигуру.

*фигурыБегеБег*<br/>
Должна ли новая фигура быть полой или заполненной.

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink

Строит объект CD2DGeometrySink с объекта CD2DPathGeometry.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>Параметры

*Pathgeometry*<br/>
Существующий объект CD2DPathGeometry.

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a>CD2DGeometrySin::Закрыть

Закрывает раковину геометрии

```
BOOL Close();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; в противном случае FALSE.

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a>CD2DGeometrySink::EndFigure

Завершает текущую цифру; дополнительно, закрывает его.

```
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>Параметры

*figureEnd*<br/>
Значение, указывавое на то, закрыто ли текущее значение. Если фигура закрыта, проводится линия между текущей точкой и точкой старта, указанной BeginFigure.

## <a name="cd2dgeometrysinkget"></a><a name="get"></a>CD2DGeometryS': Получить

Возвращает интерфейс ID2D1GeometrySink

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1GeometrySink или NULL, если объект еще не инициализирован.

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a>CD2DGeometrySink::IsValid

Проверка достоверности геометрии раковины

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если геометрия раковина действительна; в противном случае FALSE.

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a>CD2DGeometryS:::m_pSink

Указатель на ID2D1GeometrySink.

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::оператор ID2D1GeometrySink

Возвращает интерфейс ID2D1GeometrySink

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1GeometrySink или NULL, если объект еще не инициализирован.

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a>CD2DGeometrySink::SetFillMode

Определяет метод, используемый для определения того, какие точки находятся внутри геометрии, описанной этой раковиной геометрии, и какие точки находятся снаружи.

```
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>Параметры

*fillMode*<br/>
Метод, используемый для определения того, является ли заданная точка частью геометрии.

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags

Обрабражает параметры штриха и соединения, которые будут применяться к новым сегментам, добавленным к раковине геометрии.

```
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>Параметры

*вершиныФлаги*<br/>
Инсульт и соедините параметры, которые будут применены к новым сегментам, добавленным к раковине геометрии.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
