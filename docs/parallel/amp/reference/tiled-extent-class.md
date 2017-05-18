---
title: "Класс tiled_extent | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: e295b56290435a1d87ac2f0dbc0951850600534d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="tiledextent-class"></a>Класс tiled_extent
Объект `tiled_extent` объект `extent` объект одного до трех измерений, разделения задачи пространства экстента на одно-, двух- или трехмерные плитки.  
  
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
|[Конструктор tiled_extent](#ctor)|Инициализирует новый экземпляр класса `tiled_extent`.|  

  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_tile_extent](#get_tile_extent)|Возвращает `extent` объект, который перехватывает значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  
|[Панель](#pad)|Возвращает новый `tiled_extent` объекта с экстентами скорректировать вверх, чтобы нацело делиться на размеры плитки.|  
|[усечение](#truncate)|Возвращает новый `tiled_extent` объекта с экстентами скорректировать вниз, чтобы нацело делиться на размеры плитки.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[operator=](#operator_eq)|Копирует содержимое указанного `tiled_index` объекта в другой.|  

  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа tile_dim0](#tile_dim0)|Сохраняет длину наиболее значимых измерения.|  
|[Константа tile_dim1](#tile_dim1)|Сохраняет длину измерения значительные Далее для большинства.|  
|[Константа tile_dim2](#tile_dim2)|Сохраняет длину младших измерения.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|Возвращает `extent` объект, который перехватывает значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `extent`  
  
 `tiled_extent`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  

## <a name="ctor"></a> tiled_extent конструктор  
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
 `_Other`  
 `extent` Или `tiled_extent` объект, подлежащий копированию.  
  

  

## <a name="get_tile_extent"></a> get_tile_extent   
Возвращает `extent` объект, который перехватывает значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `extent` Объект, который перехватывает это размеры `tiled_extent` экземпляра.  
  

## <a name="pad"></a>  pad   
Возвращает новый `tiled_extent` объекта с экстентами скорректировать вверх, чтобы нацело делиться на размеры плитки.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
tiled_extent pad() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый `tiled_extent` объект по значению. 
## <a name="truncate"></a> усечение   
Возвращает новый `tiled_extent` объекта с экстентами скорректировать вниз, чтобы нацело делиться на размеры плитки.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
tiled_extent truncate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает новый `tiled_extent` объекта с экстентами скорректировать вниз, чтобы нацело делиться на размеры плитки.  

## <a name="operator_eq"></a> оператор =   
Копирует содержимое указанного `tiled_index` объекта в другой.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
tiled_extent&  operator= (  
    const tiled_extent& _Other ) restrict (amp, cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `tiled_index` Объект для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `tiled_index` экземпляра.  

## <a name="tile_dim0"></a> tile_dim0   
Сохраняет длину наиболее значимых измерения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim0 = _Dim0;  
```  
  
## <a name="tile_dim1"></a> tile_dim1   
Сохраняет длину измерения значительные Далее для большинства.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tile_dim2"></a> tile_dim2   
Сохраняет длину младших измерения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tile_extent"></a> tile_extent   
  Возвращает `extent` объект, который перехватывает значения `tiled_extent` аргументов шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;  
```  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

