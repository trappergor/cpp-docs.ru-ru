---
title: "Класс tiled_extent | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::tiled_extent
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: c2f7ebdb9c82ae24cf74064e710ddfb177670359
ms.lasthandoff: 02/24/2017

---
# <a name="tiledextent-class"></a>Класс tiled_extent
Объект `tiled_extent` объект `extent` объект от одного до трех измерений, подразделяет пространства экстента на одно-, двух- или трехмерных плитки.  
  
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
 Длина Далее для наиболее значительные измерения.  
  
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
|[get_tile_extent метод](#tiled_extent__get_tile_extent)|Возвращает `extent` объект, который захватывает значения `tiled_extent` аргументы шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  
|[Метод рукописного ввода](#tiled_extent__pad)|Возвращает новый `tiled_extent` объекта экстентов скорректирована вверх на делится плитку измерения.|  
|[Метод усечения](#tiled_extent__truncate)|Возвращает новый `tiled_extent` объекта экстентов скорректирована вниз на делится плитку измерения.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор =-оператор](#operator_eq)|Копирует содержимое указанного `tiled_index` объекта в другой.|  

  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа tile_dim0](#tiled_extent__tile_dim0)|Сохраняет длину наиболее значимых измерения.|  
|[Константа tile_dim1](#tiled_extent__tile_dim1)|Сохраняет длину измерения значительные Далее для большинства.|  
|[Константа tile_dim2](#tiled_extent__tile_dim2)|Сохраняет длину младших измерения.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[tile_extent элемент данных](#tiled_extent__tile_extent)|Возвращает `extent` объект, который захватывает значения `tiled_extent` аргументы шаблона `_Dim0`, `_Dim1`, и `_Dim2`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `extent`  
  
 `tiled_extent`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  

## <a name="tiled_extent__ctor"></a> tiled_extent конструктор  
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
  

  

## <a name="tiled_extent__get_tile_extent"></a> get_tile_extent   
Возвращает `extent` объект, который захватывает значения `tiled_extent` аргументы шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `extent` Объект, который перехватывает это размеры `tiled_extent` экземпляра.  
  

## <a name="tiled_extent__pad"></a>  pad   
Возвращает новый `tiled_extent` объекта экстентов скорректирована вверх на делится плитку измерения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
tiled_extent pad() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый `tiled_extent` объект по значению. 
## <a name="tiled_extent__truncate"></a> усечение   
Возвращает новый `tiled_extent` объекта экстентов скорректирована вниз на делится плитку измерения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
tiled_extent truncate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает новый `tiled_extent` объекта экстентов скорректирована вниз на делится плитку измерения.  

## <a name="tiled_extent__operator_eq"></a> оператор =   
Копирует содержимое указанного `tiled_index` объекта в другой.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
tiled_extent&  operator= (  
    const tiled_extent& _Other ) restrict (amp, cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `tiled_index` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `tiled_index` экземпляра.  

## <a name="tiled_extent__tile_dim0"></a> tile_dim0   
Сохраняет длину наиболее значимых измерения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim0 = _Dim0;  
```  
  
## <a name="tiled_extent__tile_dim1"></a> tile_dim1   
Сохраняет длину измерения значительные Далее для большинства.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_extent__tile_dim2"></a> tile_dim2   
Сохраняет длину младших измерения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_extent__tile_extent"></a> tile_extent   
  Возвращает `extent` объект, который захватывает значения `tiled_extent` аргументы шаблона `_Dim0`, `_Dim1`, и `_Dim2`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;  
```  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

