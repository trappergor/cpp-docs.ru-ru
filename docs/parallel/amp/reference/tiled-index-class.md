---
title: "Класс tiled_index | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4acda08cac0e67559db48525e634cd21cdf5a8f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="tiledindex-class"></a>Класс tiled_index
Предоставляет индекс в [tiled_extent](tiled-extent-class.md) объекта. Этот класс содержит свойства для доступа к элементам относительно Плитка локального источника, так и относительно глобального источника. Дополнительные сведения о пространствах Мозаичная см [с помощью плитки](../../../parallel/amp/using-tiles.md).  
  
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
 `_Dim0`  
 Длина наиболее значимых измерения.  
  
 `_Dim1`  
 Длина Далее наиболее значительные измерения.  
  
 `_Dim2`  
 Длина младших измерения.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор tiled_index](#ctor)|Инициализирует новый экземпляр класса `tile_index`.|  

  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_tile_extent](#tiled_index__get_tile_extent)|Возвращает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  


  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Барьер константа](#tiled_index__barrier)|Магазины [tile_barrier](tile-barrier-class.md) , представляющий барьер в текущий tile потоков.|  
|||  
|[Глобальные константы](#tiled_index__global)|Магазины [индекс](index-class.md) объекта ранг 1, 2 или 3, представляющий глобальный индекса в [сетки](http://msdn.microsoft.com/en-us/f7d1b6a6-586c-4345-b09a-bfc26c492cb0) объекта.|  
|[Local-константа](#tiled_index__local)|Магазины `index` объекта ранг 1, 2 или 3, представляющий относительный индекс в текущей плитки [tiled_extent](tiled-extent-class.md) объекта.|  
|[Ранг константа](#tiled_index__rank)|Сохраняет ранг объекта `tiled_index` объекта.|  
|[Tile-константа](#tiled_index__tile)|Магазины `index` объекта ранга 1, 2 или 3, который представляет координаты относительно текущего расположения, из `tiled_extent` объекта.|  
|[Константа tile_dim0](#tiled_index__tile_dim0)|Сохраняет длину наиболее значимых измерения.|  
|[Константа tile_dim1](#tiled_index__tile_dim1)|Сохраняет длину измерения значительные Далее для большинства.|  
|[Константа tile_dim2](#tiled_index__tile_dim2)|Сохраняет длину младших измерения.|  
|[Константа tile_origin](#tiled_index__tile_origin)|Магазины `index` объекта координат ранг 1, 2 или 3, представляющий глобальный происхождения текущего расположения в `tiled_extent` объекта.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|Возвращает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  

  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  


## <a name="tiled_index__ctor"></a>Конструктор tiled_index  
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
 `_Global`  
 Глобальный [индекс](index-class.md) из сконструированного `tiled_index`.  
  
 `_Local`  
 Локальный [индекс](index-class.md) из сконструированного`tiled_index`  
  
 `_Tile`  
 Плитки [индекс](index-class.md) из сконструированного`tiled_index`  
  
 `_Tile_origin`  
 Плитка источника [индекс](index-class.md) из сконструированного`tiled_index`  
  
 `_Barrier`  
 [Tile_barrier](tile-barrier-class.md) сформированный объект `tiled_index`.  
  
 `_Other`  
 `tile_index` Копируемого объекта для сконструированный `tiled_index`.  
  
## <a name="overloads"></a>Overloads  
  
|||  
|-|-|  
|Имя|Описание|  
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Инициализирует новый экземпляр `tile_index` класса из индекса плитку на глобальные координаты и относительное положение в плитке в локальной системе координат. `_Global` И `_Tile_origin` вычисляются параметры.|  
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Инициализирует новый экземпляр `tile_index` , копируя указанный `tiled_index` объекта.|  


## <a name="tiled_index__get_tile_extent"></a>get_tile_extent
Возвращает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
extent<rank> get_tile_extent()restrict(amp,cpu);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `extent` Объект, имеющий значения `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  

## <a name="tiled_index__barrier"></a>Барьер   
Магазины [tile_barrier](tile-barrier-class.md) , представляющий барьер в текущий tile потоков.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const tile_barrier barrier;  
```  

## <a name="tiled_index__global"></a>глобальные   
Магазины [индекс](index-class.md) объекта ранга 1, 2 или 3, представляющее индекс глобального объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> global;  
```  
  
## <a name="tiled_index__local"></a>локальные   
Магазины [индекс](index-class.md) объекта ранг 1, 2 или 3, представляющий относительный индекс в текущей плитки [tiled_extent](tiled-extent-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> local;  
```  
  
## <a name="tiled_index__rank"></a>Ранг   
Сохраняет ранг объекта `tiled_index` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int rank = _Rank;  
```  

## <a name="tiled_index__tile"></a>плитки   
Магазины [индекс](index-class.md) объекта ранга 1, 2 или 3, который представляет координаты относительно текущего расположения, из [tiled_extent](tiled-extent-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> tile;  
```  
  
## <a name="tiled_index__tile_dim0"></a>tile_dim0  
Сохраняет длину наиболее значимых измерения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim0 = _Dim0;  
```  
   
## <a name="tiled_index__tile_dim1"></a>tile_dim1   
Сохраняет длину измерения значительные Далее для большинства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_index__tile_dim2"></a>tile_dim2   
Сохраняет длину младших измерения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_index__tile_origin"></a>tile_origin   
Магазины [индекс](index-class.md) объекта координат ранг 1, 2 или 3, представляющий глобальный происхождения текущего расположения в [tiled_extent](tiled-extent-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
const index<rank> tile_origin  
```  
## <a name="tile_extent"></a>tile_extent
  Возвращает [экстент](extent-class.md) объект, имеющий значения `tiled_index` аргументов шаблона `tiled_index` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
