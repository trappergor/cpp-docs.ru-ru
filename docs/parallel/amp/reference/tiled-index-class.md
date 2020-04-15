---
title: Класс tiled_index
ms.date: 03/27/2019
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
ms.openlocfilehash: 46a6b3548526f0917c4e022a12bf859242e70b20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375471"
---
# <a name="tiled_index-class"></a>Класс tiled_index

Обеспечивает индекс в [tiled_extent](tiled-extent-class.md) объект. Этот класс имеет свойства для доступа к элементам относительно локального происхождения плитки и относительно глобального происхождения. Для получения дополнительной информации о кафельных пространствах [см.](../../../parallel/amp/using-tiles.md)

## <a name="syntax"></a>Синтаксис

```cpp
template <
    int _Dim0,
    int _Dim1 = 0,
    int _Dim2 = 0
>
class tiled_index : public _Tiled_index_base<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;

template <
    int _Dim0
>
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;
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
|[tiled_index конструктор](#ctor)|Инициализирует новый экземпляр класса `tile_index`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|Возвращает объект [степени,](extent-class.md) который имеет `tiled_index` значения `_Dim0`аргументов `_Dim1`шаблона, и `_Dim2`.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[барьер Констант](#tiled_index__barrier)|Хранит [tile_barrier](tile-barrier-class.md) объект, представляющий собой барьер в текущей плитке потоков.|
|||
|[глобальная константа](#tiled_index__global)|Хранит [объект индекса](index-class.md) ранга 1, 2 или 3, представляющий глобальный индекс в объекте сетки.|
|[local - константа](#tiled_index__local)|Хранит `index` объект ранга 1, 2 или 3, представляющий относительный индекс в текущей плитке [tiled_extent](tiled-extent-class.md) объекта.|
|[ранг константа](#tiled_index__rank)|Хранит ранг `tiled_index` объекта.|
|[плитка Констант](#tiled_index__tile)|Хранит `index` объект ранга 1, 2 или 3, представляющий координаты текущей плитки `tiled_extent` объекта.|
|[tile_dim0 Констант](#tiled_index__tile_dim0)|Хранит длину наиболее значительного измерения.|
|[tile_dim1 Констант](#tiled_index__tile_dim1)|Хранит длину следующего к самому значительному измерению.|
|[tile_dim2 Констант](#tiled_index__tile_dim2)|Хранит длину наименее значительного измерения.|
|[tile_origin Констант](#tiled_index__tile_origin)|Хранит `index` объект ранга 1, 2 или 3, представляющий глобальные координаты происхождения текущей плитки в объекте. `tiled_extent`|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[tile_extent](#tile_extent)|Получает [объект степени,](extent-class.md) который имеет `tiled_index` значения `tiled_index` шаблона аргументы шаблона аргументы `_Dim0`, `_Dim1`и `_Dim2`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="tiled_index-constructor"></a><a name="ctor"></a>tiled_index конструктор

Инициализирует новый экземпляр класса `tiled_index`.

### <a name="syntax"></a>Синтаксис

```cpp
tiled_index(
    const index<rank>& _Global,
    const index<rank>& _Local,
    const index<rank>& _Tile,
    const index<rank>& _Tile_origin,
    const tile_barrier& _Barrier ) restrict(amp,cpu);

tiled_index(
    const tiled_index& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Global*<br/>
Глобальный [индекс](index-class.md) построен. `tiled_index`

*_Local*<br/>
Локальный [индекс](index-class.md) построенного`tiled_index`

*_Tile*<br/>
[Индекс](index-class.md) плитки построенных`tiled_index`

*_Tile_origin*<br/>
[Индекс](index-class.md) происхождения плитки построенного`tiled_index`

*_Barrier*<br/>
Объект [tile_barrier](tile-barrier-class.md) построен. `tiled_index`

*_Other*<br/>
Объект, `tile_index` который будет скопирован `tiled_index`на построенный .

### <a name="overloads"></a>Overloads

|||
|-|-|
|Имя|Описание|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Инициализирует новый экземпляр `tile_index` класса из индекса плитки в глобальных координатах и относительное положение в плитке в локальных координатах. Вычисляются `_Global` параметры и `_Tile_origin` параметры.|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Инициализирует новый экземпляр `tile_index` класса, `tiled_index` копируя указанный объект.|

## <a name="get_tile_extent"></a><a name="tiled_index__get_tile_extent"></a>get_tile_extent

Возвращает объект [степени,](extent-class.md) который имеет `tiled_index` значения `_Dim0`аргументов `_Dim1`шаблона, и `_Dim2`.

### <a name="syntax"></a>Синтаксис

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `extent` который имеет значения `tiled_index` `_Dim0`аргументов шаблона, `_Dim1`и `_Dim2`.

## <a name="barrier"></a><a name="tiled_index__barrier"></a>Барьер

Хранит [tile_barrier](tile-barrier-class.md) объект, представляющий собой барьер в текущей плитке потоков.

### <a name="syntax"></a>Синтаксис

```cpp
const tile_barrier barrier;
```

## <a name="global"></a><a name="tiled_index__global"></a>Глобального

Хранит [объект индекса](index-class.md) ранга 1, 2 или 3, представляющий глобальный индекс объекта.

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> global;
```

## <a name="local"></a><a name="tiled_index__local"></a>Местных

Хранит [объект индекса](index-class.md) ранга 1, 2 или 3, представляющий относительный индекс в текущей плитке [tiled_extent](tiled-extent-class.md) объекта.

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> local;
```

## <a name="rank"></a><a name="tiled_index__rank"></a>Ранга

Хранит ранг `tiled_index` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
static const int rank = _Rank;
```

## <a name="tile"></a><a name="tiled_index__tile"></a>Плитки

Хранит [объект индекса](index-class.md) ранга 1, 2 или 3, представляющий координаты текущей плитки [tiled_extent](tiled-extent-class.md) объекта.

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> tile;
```

## <a name="tile_dim0"></a><a name="tiled_index__tile_dim0"></a>tile_dim0

Хранит длину наиболее значительного измерения.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tiled_index__tile_dim1"></a>tile_dim1

Хранит длину следующего к самому значительному измерению.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tiled_index__tile_dim2"></a>tile_dim2

Хранит длину наименее значительного измерения.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_origin"></a><a name="tiled_index__tile_origin"></a>tile_origin

Хранит [объект индекса](index-class.md) ранга 1, 2 или 3, представляющий глобальные координаты происхождения текущей плитки в [tiled_extent](tiled-extent-class.md) объекте.

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a><a name="tile_extent"></a>tile_extent

Получает [объект степени,](extent-class.md) который имеет `tiled_index` значения `tiled_index` шаблона аргументы шаблона аргументы `_Dim0`, `_Dim1`и `_Dim2`.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
