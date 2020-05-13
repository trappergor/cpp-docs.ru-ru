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
ms.openlocfilehash: ce2710da1a745efedcd6e9e524355eda41e26de2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374712"
---
# <a name="tiled_extent-class"></a>Класс tiled_extent

Объект `tiled_extent` — `extent` это объект одного-трех измерений, который разделяет пространство в одно-, двух- или трехмерное.

## <a name="syntax"></a>Синтаксис

```cpp
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
Длина наиболее значительного измерения.

*_Dim1*<br/>
Длина следующего к самому значительному измерению.

*_Dim2*<br/>
Длина наименее значимого измерения.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[tiled_extent конструктор](#ctor)|Инициализирует новый экземпляр класса `tiled_extent`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|Возвращает `extent` объект, который фиксирует `tiled_extent` значения аргументов шаблона, `_Dim0` `_Dim1`и `_Dim2`.|
|[Площадку](#pad)|Возвращает новый `tiled_extent` объект с отрегулированными размерами, чтобы быть равномерно делится на размеры плитки.|
|[truncate](#truncate)|Возвращает новый `tiled_extent` объект с скорректированными размерами, чтобы быть равномерно делится на размеры плитки.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператора](#operator_eq)|Копирует содержимое указанного `tiled_index` объекта в этот.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[tile_dim0 Констант](#tile_dim0)|Хранит длину наиболее значительного измерения.|
|[tile_dim1 Констант](#tile_dim1)|Хранит длину следующего к самому значительному измерению.|
|[tile_dim2 Констант](#tile_dim2)|Хранит длину наименее значительного измерения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[tile_extent](#tile_extent)|Получает `extent` объект, который фиксирует `tiled_extent` значения аргументов шаблона, `_Dim0` `_Dim1`и `_Dim2`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`extent`

`tiled_extent`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="tiled_extent-constructor"></a><a name="ctor"> </a> tiled_extent конструктор

Инициализирует новый экземпляр класса `tiled_extent`.

### <a name="syntax"></a>Синтаксис

```cpp
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `extent` `tiled_extent` или объект для копирования.

## <a name="get_tile_extent"></a><a name="get_tile_extent"> </a> get_tile_extent

Возвращает `extent` объект, который фиксирует `tiled_extent` значения аргументов шаблона, `_Dim0` `_Dim1`и `_Dim2`.

### <a name="syntax"></a>Синтаксис

```cpp
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `extent` который фиксирует размеры этого `tiled_extent` экземпляра.

## <a name="pad"></a><a name="pad"> </a> колодка

Возвращает новый `tiled_extent` объект с отрегулированными размерами, чтобы быть равномерно делится на размеры плитки.

### <a name="syntax"></a>Синтаксис

```cpp
tiled_extent pad() const;
```

### <a name="return-value"></a>Возвращаемое значение

Новый `tiled_extent` объект, по стоимости.

## <a name="truncate"></a><a name="truncate"> </a> усечение

Возвращает новый `tiled_extent` объект с скорректированными размерами, чтобы быть равномерно делится на размеры плитки.

### <a name="syntax"></a>Синтаксис

```cpp
tiled_extent truncate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает новый `tiled_extent` объект с скорректированными размерами, чтобы быть равномерно делится на размеры плитки.

## <a name="operator"></a><a name="operator_eq"> </a> оператора

Копирует содержимое указанного `tiled_index` объекта в этот.

### <a name="syntax"></a>Синтаксис

```cpp
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `tiled_index` для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `tiled_index` этот экземпляр.

## <a name="tile_dim0"></a><a name="tile_dim0"> </a> tile_dim0

Хранит длину наиболее значительного измерения.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tile_dim1"> </a> tile_dim1

Хранит длину следующего к самому значительному измерению.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tile_dim2"> </a> tile_dim2

Хранит длину наименее значительного измерения.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"></a><a name="tile_extent"> </a> tile_extent

Получает `extent` объект, который фиксирует `tiled_extent` значения аргументов шаблона, `_Dim0` `_Dim1`и `_Dim2`.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
