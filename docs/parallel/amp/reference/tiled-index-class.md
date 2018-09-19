---
title: Класс tiled_index | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47cd4cc765459acc6270c64b6cc37fe328f36757
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069421"
---
# <a name="tiledindex-class"></a>Класс tiled_index
Предоставляет индекс в [tiled_extent](tiled-extent-class.md) объекта. Этот класс содержит свойства для доступа к элементам относительно локального начального положения плитки и относительно глобального начального положения. Дополнительные сведения о замощенных пространствах см. в разделе [с помощью плитки](../../../parallel/amp/using-tiles.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
*_Dim0*<br/>
Длина самого значительного измерения.  
  
*_Dim1*<br/>
Длина измерения, следующего за самым значительным измерением.  
  
*_Dim2*<br/>
Длина наименее значительного измерения.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[tiled_index конструктор](#ctor)|Инициализирует новый экземпляр класса `tile_index`.|  

  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_tile_extent](#tiled_index__get_tile_extent)|Возвращает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  


  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание|  
|----------|-----------------|  
|[Барьер константа](#tiled_index__barrier)|Магазины [tile_barrier](tile-barrier-class.md) , представляющий барьер в текущей мозаике потоков.|  
|||  
|[Глобальная константа](#tiled_index__global)|Магазины [индекс](index-class.md) ранга 1, 2 или 3, представляющий глобальный указатель в объект сетки.|  
|[локальная константа](#tiled_index__local)|Магазины `index` ранга 1, 2 или 3, представляющий относительный индекс в текущей мозаике объекта [tiled_extent](tiled-extent-class.md) объекта.|  
|[Ранг константа](#tiled_index__rank)|Хранит ранг объекта `tiled_index` объекта.|  
|[Tile-константа](#tiled_index__tile)|Магазины `index` ранга 1, 2 или 3, представляющий координаты текущей мозаики объекта `tiled_extent` объекта.|  
|[Константа tile_dim0](#tiled_index__tile_dim0)|Хранит длину наиболее значительного измерения.|  
|[Константа tile_dim1](#tiled_index__tile_dim1)|Хранит длину измерения, следующего за самым значительным измерением.|  
|[Константа tile_dim2](#tiled_index__tile_dim2)|Хранит длину наименее значительного измерения.|  
|[tile_origin константа](#tiled_index__tile_origin)|Магазины `index` объект ранг 1, 2 или 3, представляющего глобальные координаты начального положения текущей мозаики в `tiled_extent` объекта.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|Получает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  

  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  


## <a name="tiled_index__ctor"></a>  tiled_index конструктор  
Инициализирует новый экземпляр класса `tiled_index`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
tiled_index(  
    const index<rank>& _Global,  
    const index<rank>& _Local,  
    const index<rank>& _Tile,  
    const index<rank>& _Tile_origin,  
    const tile_barrier& _Barrier ) restrict(amp,cpu);  
  
tiled_index(  
    const tiled_index& _Other ) restrict(amp,cpu);  
```  
  
#### <a name="parameters"></a>Параметры  
*_Global*<br/>
Глобальный [индекс](index-class.md) построенного `tiled_index`.  
  
*_Локальный*<br/>
Локальный [индекс](index-class.md) построенного `tiled_index`  
  
*_Tile*<br/>
Плитка [индекс](index-class.md) построенного `tiled_index`  
  
*_Tile_origin*<br/>
Начального положения плитки [индекс](index-class.md) построенного `tiled_index`  
  
*_Barrier*<br/>
[Tile_barrier](tile-barrier-class.md) построенного `tiled_index`.  
  
*_Другое*<br/>
`tile_index` Который необходимо скопировать в построенный `tiled_index`.  
  
## <a name="overloads"></a>Overloads  
  
|||  
|-|-|  
|name|Описание|  
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Инициализирует новый экземпляр класса `tile_index` класс из индекса плитки в глобальных координатах и относительной позиции в плитке в локальных координатах. `_Global` И `_Tile_origin` вычисляются параметры.|  
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Инициализирует новый экземпляр класса `tile_index` посредством копирования указанного `tiled_index` объекта.|  


## <a name="tiled_index__get_tile_extent"></a>  get_tile_extent
Возвращает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
extent<rank> get_tile_extent()restrict(amp,cpu);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `extent` Объект, имеющий значения `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  

## <a name="tiled_index__barrier"></a>  Барьер   
Магазины [tile_barrier](tile-barrier-class.md) , представляющий барьер в текущей мозаике потоков.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const tile_barrier barrier;  
```  

## <a name="tiled_index__global"></a>  Глобальные   
Магазины [индекс](index-class.md) ранга 1, 2 или 3, представляющее индекс глобального объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> global;  
```  
  
## <a name="tiled_index__local"></a>  локальный   
Магазины [индекс](index-class.md) ранга 1, 2 или 3, представляющий относительный индекс в текущей мозаике объекта [tiled_extent](tiled-extent-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> local;  
```  
  
## <a name="tiled_index__rank"></a>  Ранг   
Хранит ранг объекта `tiled_index` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int rank = _Rank;  
```  

## <a name="tiled_index__tile"></a>  Плитка   
Магазины [индекс](index-class.md) ранга 1, 2 или 3, представляющий координаты текущей мозаики объекта [tiled_extent](tiled-extent-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> tile;  
```  
  
## <a name="tiled_index__tile_dim0"></a>  tile_dim0  
Хранит длину наиболее значительного измерения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim0 = _Dim0;  
```  
   
## <a name="tiled_index__tile_dim1"></a>  tile_dim1   
Хранит длину измерения, следующего за самым значительным измерением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_index__tile_dim2"></a>  tile_dim2   
Хранит длину наименее значительного измерения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_index__tile_origin"></a>  tile_origin   
Магазины [индекс](index-class.md) объект ранг 1, 2 или 3, представляющего глобальные координаты начального положения текущей мозаики в [tiled_extent](tiled-extent-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> tile_origin  
```  
## <a name="tile_extent"></a>  tile_extent
  Получает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
