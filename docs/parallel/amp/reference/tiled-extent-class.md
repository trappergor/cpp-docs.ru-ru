---
title: Класс tiled_extent
ms.date: 11/04/2016
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
ms.openlocfilehash: 51e7696b8103e81d42beec0987a49f26fe041643
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264339"
---
# <a name="tiledextent-class"></a>Класс tiled_extent

Объект `tiled_extent` объект `extent` объект от одного до трех измерений, подразделяет пространство на одно-, двух- или трехмерную мозаику.

### <a name="syntax"></a>Синтаксис

```
template <
    int _Dim0,
    int _Dim1,
    int _Dim2
>
class tiled_extent : public Concurrency::extent<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;

template <
    int _Dim0
>
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;
```

### <a name="parameters"></a>Параметры

*_Dim0*<br/>
Длина самого значительного измерения.

*_Dim1*<br/>
Длина измерения, следующего за самым значительным измерением.

*_Dim2*<br/>
Длина наименее значительного измерения.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор tiled_extent](#ctor)|Инициализирует новый экземпляр класса `tiled_extent`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|Возвращает `extent` объект, который фиксирует значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|
|[Панель](#pad)|Возвращает новый `tiled_extent` объекта с экстентами максимально возможное нацело делиться с размерами.|
|[truncate](#truncate)|Возвращает новый `tiled_extent` объекта с экстентами скорректировать вниз, чтобы нацело делиться с размерами.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `tiled_index` в данный объект.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание:|
|----------|-----------------|
|[Константа tile_dim0](#tile_dim0)|Хранит длину наиболее значительного измерения.|
|[Константа tile_dim1](#tile_dim1)|Хранит длину измерения, следующего за самым значительным измерением.|
|[Константа tile_dim2](#tile_dim2)|Хранит длину наименее значительного измерения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[tile_extent](#tile_extent)|Получает `extent` объект, который фиксирует значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`extent`

`tiled_extent`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен:** Параллельность

## <a name="ctor"> </a>  Конструктор tiled_extent

Инициализирует новый экземпляр класса `tiled_extent`.

### <a name="syntax"></a>Синтаксис

```
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`extent` Или `tiled_extent` копируемый объект.

## <a name="get_tile_extent"> </a>  get_tile_extent

Возвращает `extent` объект, который фиксирует значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.

### <a name="syntax"></a>Синтаксис

```
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

`extent` Объект, который получает размеры этого `tiled_extent` экземпляра.

## <a name="pad"> </a>  Панель

Возвращает новый `tiled_extent` объекта с экстентами максимально возможное нацело делиться с размерами.

### <a name="syntax"></a>Синтаксис

```
tiled_extent pad() const;
```

### <a name="return-value"></a>Возвращаемое значение

Новый `tiled_extent` объект по значению.
## <a name="truncate"> </a>  усечение

Возвращает новый `tiled_extent` объекта с экстентами скорректировать вниз, чтобы нацело делиться с размерами.

### <a name="syntax"></a>Синтаксис

```
tiled_extent truncate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает новый `tiled_extent` объекта с экстентами скорректировать вниз, чтобы нацело делиться с размерами.

## <a name="operator_eq"> </a>  оператор =

Копирует содержимое указанного объекта `tiled_index` в данный объект.

### <a name="syntax"></a>Синтаксис

```
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`tiled_index` Для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `tiled_index` экземпляра.

## <a name="tile_dim0"> </a>  tile_dim0

Хранит длину наиболее значительного измерения.

### <a name="syntax"></a>Синтаксис

```
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"> </a>  tile_dim1

Хранит длину измерения, следующего за самым значительным измерением.

### <a name="syntax"></a>Синтаксис

```
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"> </a>  tile_dim2

Хранит длину наименее значительного измерения.

### <a name="syntax"></a>Синтаксис

```
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"> </a>  tile_extent
  Получает `extent` объект, который фиксирует значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.

### <a name="syntax"></a>Синтаксис

```
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
