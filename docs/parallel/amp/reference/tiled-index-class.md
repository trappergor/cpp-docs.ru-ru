---
title: "Класс tiled_index | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tiled_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tiled_index - класс"
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс tiled_index
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Предоставляет индекс в объекте [tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md).  Этот класс содержит свойства для доступа к элементам относительно локального начального положения плитки и относительно глобального начального положения.  Дополнительные сведения о замощенных пространствах см. в разделе [Использование плиток](../../../parallel/amp/using-tiles.md).  
  
## Синтаксис  
  
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
|[Конструктор tiled\_index::tiled\_index](../Topic/tiled_index::tiled_index%20Constructor.md)|Инициализирует новый экземпляр класса `tile_index`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод tiled\_index::get\_tile\_extent](../Topic/tiled_index::get_tile_extent%20Method.md)|Возвращает объект [extent](../Topic/extent%20Class%20\(C++%20AMP\).md), который содержит значения аргументов `_Dim0`, `_Dim1` и `_Dim2` шаблона [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md).|  
  
### Открытые константы  
  
|Name|Описание|  
|----------|--------------|  
|[Константа tiled\_index::barrier](../Topic/tiled_index::barrier%20Constant.md)|Хранит объект [tile\_barrier](../Topic/tile_barrier%20Class.md), представляющий барьер в текущей мозаике потоков.|  
|||  
|[Константа tiled\_index::global](../Topic/tiled_index::global%20Constant.md)|Хранит объект [index](../../../parallel/amp/reference/index-class.md) ранга 1, 2 или 3, представляющий собой глобальный индекс в объекте [grid](http://msdn.microsoft.com/ru-ru/f7d1b6a6-586c-4345-b09a-bfc26c492cb0).|  
|[Константа tiled\_index::local](../Topic/tiled_index::local%20Constant.md)|Хранит объект `index` ранга 1, 2 или 3, представляющий относительный индекс в текущей мозаике объекта [tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md).|  
|[Константа tiled\_index::rank](../Topic/tiled_index::rank%20Constant.md)|Хранит ранг объекта [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md).|  
|[Константа tiled\_index::tile](../Topic/tiled_index::tile%20Constant.md)|Хранит объект `index` ранга 1, 2 или 3, представляющий координаты текущей мозаики объекта `tiled_extent`.|  
|[Константа tiled\_index::tile\_dim0](../Topic/tiled_index::tile_dim0%20Constant.md)|Хранит длину наиболее значительного измерения.|  
|[Константа tiled\_index::tile\_dim1](../Topic/tiled_index::tile_dim1%20Constant.md)|Хранит длину измерения, следующего за самым значительным измерением.|  
|[Константа tiled\_index::tile\_dim2](../Topic/tiled_index::tile_dim2%20Constant.md)|Хранит длину наименее значительного измерения.|  
|[Константа tiled\_index::tile\_origin](../Topic/tiled_index::tile_origin%20Constant.md)|Хранит объект `index` ранга 1, 2 или 3, представляющего глобальные координаты начального положения текущей мозаики в объекте `tiled_extent`.|  
  
### Открытые члены данных  
  
|Name|Описание|  
|----------|--------------|  
|[Элемент данных tiled\_index::tile\_extent](../Topic/tiled_index::tile_extent%20Data%20Member.md)|Получает объект [extent](../Topic/extent%20Class%20\(C++%20AMP\).md), который содержит значения аргументов `_Dim0`, `_Dim1` и `_Dim2` шаблона [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) шаблона [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md).|  
  
## Иерархия наследования  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## Требования  
 **Заголовок:** amp.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)