---
title: "Класс tiled_extent | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tiled_extent"
dev_langs: 
  - "C++"
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс tiled_extent
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Объект `tiled_extent` — это объект `extent`, имеющий от одного до трех измерений , который разделяет пространство рамки на одно\-, двух\-, или трехмерную мозаику.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `_Dim0`  
 Длина самого значительного измерения.  
  
 `_Dim1`  
 Длина измерения, следующего за самым значительным измерением.  
  
 `_Dim2`  
 Длина наименее значительного измерения.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор tiled\_extent::tiled\_extent](../Topic/tiled_extent::tiled_extent%20Constructor.md)|Инициализирует новый экземпляр класса `tiled_extent`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод tiled\_extent::get\_tile\_extent](../Topic/tiled_extent::get_tile_extent%20Method.md)|Возвращает объект `extent`, который фиксирует значения аргументов `_Dim0`, `_Dim1` и `_Dim2` `tiled_extent`.|  
|[Метод tiled\_extent::pad](../Topic/tiled_extent::pad%20Method.md)|Возвращает новый объект `tiled_extent` с завышенными границами для того, чтобы обеспечить равномерное разделение объекта в соответствии с размерами изображений.|  
|[Метод tiled\_extent::truncate](../Topic/tiled_extent::truncate%20Method.md)|Возвращает новый объект `tiled_extent` с заниженными границами для того, чтобы обеспечить равномерное разделение объекта в соответствии с размерами изображений.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор tiled\_extent::operator\=](../Topic/tiled_extent::operator=%20Operator.md)|Копирует содержимое указанного объекта `tiled_index` в данный объект.|  
  
### Открытые константы  
  
|Name|Описание|  
|----------|--------------|  
|[Константа tiled\_extent::tile\_dim0](../Topic/tiled_extent::tile_dim0%20Constant.md)|Хранит длину наиболее значительного измерения.|  
|[Константа tiled\_extent::tile\_dim1](../Topic/tiled_extent::tile_dim1%20Constant.md)|Хранит длину измерения, следующего за самым значительным измерением.|  
|[Константа tiled\_extent::tile\_dim2](../Topic/tiled_extent::tile_dim2%20Constant.md)|Хранит длину наименее значительного измерения.|  
  
### Открытые члены данных  
  
|Name|Описание|  
|----------|--------------|  
|[Элемент данных tiled\_extent::tile\_extent](../Topic/tiled_extent::tile_extent%20Data%20Member.md)|Получает объект `extent`, который записывает значения аргументов `_Dim0`, `_Dim1` и `_Dim2` шаблона `tiled_extent`.|  
  
## Иерархия наследования  
 `extent`  
  
 `tiled_extent`  
  
## Требования  
 **Заголовок:** amp.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)