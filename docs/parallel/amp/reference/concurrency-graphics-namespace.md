---
title: "Пространство имен Concurrency::graphics | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics"
  - "amp_short_vectors/Concurrency::graphics"
dev_langs: 
  - "C++"
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Пространство имен Concurrency::graphics
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Пространство имен graphics предоставляет типы и функции, которые предназначены для программирования графики.  
  
## Синтаксис  
  
```  
namespace graphics;  
```  
  
## Члены  
  
### Пространства имен  
  
|Name|Описание|  
|----------|--------------|  
|[Пространство имен Concurrency::graphics::direct3d](../../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md)|Предоставляет функции для взаимодействия Direct3D.|  
  
### Определения типов  
  
|Name|Описание|  
|----------|--------------|  
|`uint`|Тип элемента для [Класс uint\_2](../../../parallel/amp/reference/uint-2-class.md), [Класс uint\_3](../../../parallel/amp/reference/uint-3-class.md) и [Класс uint\_4](../../../parallel/amp/reference/uint-4-class.md).  Определен как `typedef unsigned int uint;`.|  
  
### Перечисления  
  
|Name|Описание|  
|----------|--------------|  
|[Перечисление address\_mode](../Topic/address_mode%20Enumeration.md)|Задает режимы адреса, поддерживаемые для дискретизации текстур.|  
|[Перечисление filter\_mode](../Topic/filter_mode%20Enumeration.md)|Задает режимы фильтра, поддерживаемые для дискретизации текстур.|  
  
### Классы  
  
|Name|Описание|  
|----------|--------------|  
|[Класс texture](../Topic/texture%20Class.md)|Текстура — это агрегат данных в accelerator\_view в домене области памяти.  Это коллекция переменных, по одной для каждого элемента в домене области памяти.  Каждая переменная содержит значение, соответствующее простому типу C\+\+ \(unsigned int, int, float, double\) или скалярному типу norm или unorm \(определенному в concurrency::graphics\) или подходящие типы короткого вектора, определенные в concurrency::graphics.|  
|[Класс writeonly\_texture\_view](../Topic/writeonly_texture_view%20Class.md)|Класс writeonly\_texture\_view предоставляет доступ к текстуре только для записи.|  
|[Класс double\_2](../Topic/double_2%20Class.md)|Представляет короткий вектор из 2 значений `double`.|  
|[Класс double\_3](../../../parallel/amp/reference/double-3-class.md)|Представляет короткий вектор из 3 значений `double`.|  
|[Класс double\_4](../Topic/double_4%20Class.md)|Представляет короткий вектор из 4 значений `double`.|  
|[Класс float\_2](../../../parallel/amp/reference/float-2-class.md)|Представляет короткий вектор из 2 значений `float`.|  
|[Класс float\_3](../../../parallel/amp/reference/float-3-class.md)|Представляет короткий вектор из 3 значений `float`.|  
|[Класс float\_4](../../../parallel/amp/reference/float-4-class.md)|Представляет короткий вектор из 4 значений `float`.|  
|[Класс int\_2](../Topic/int_2%20Class.md)|Представляет короткий вектор из 2 значений `int`.|  
|[Класс int\_3](../../../parallel/amp/reference/int-3-class.md)|Представляет короткий вектор из 3 значений `int`.|  
|[Класс int\_4](../../../parallel/amp/reference/int-4-class.md)|Представляет короткий вектор из 4 значений `int`.|  
|[Класс norm\_2](../../../parallel/amp/reference/norm-2-class.md)|Представляет короткий вектор из 2 значений `norm`.|  
|[Класс norm\_3](../../../parallel/amp/reference/norm-3-class.md)|Представляет короткий вектор из 3 значений `norm`.|  
|[Класс norm\_4](../../../parallel/amp/reference/norm-4-class.md)|Представляет короткий вектор из 4 значений `norm`.|  
|[Класс uint\_2](../../../parallel/amp/reference/uint-2-class.md)|Представляет короткий вектор из 2 значений `uint`.|  
|[Класс uint\_3](../../../parallel/amp/reference/uint-3-class.md)|Представляет короткий вектор из 3 значений `uint`.|  
|[Класс uint\_4](../../../parallel/amp/reference/uint-4-class.md)|Представляет короткий вектор из 4 значений `uint`.|  
|[Класс unorm\_2](../../../parallel/amp/reference/unorm-2-class.md)|Представляет короткий вектор из 2 значений `unorm`.|  
|[Класс unorm\_3](../../../parallel/amp/reference/unorm-3-class.md)|Представляет короткий вектор из 3 значений `unorm`.|  
|[Класс unorm\_4](../../../parallel/amp/reference/unorm-4-class.md)|Представляет короткий вектор из 4 значений `unorm`.|  
|[Класс sampler](../../../parallel/amp/reference/sampler-class.md)|Представляет конфигурацию образца, используемую для выборки текстуры.|  
|[Структура short\_vector](../../../parallel/amp/reference/short-vector-structure.md)|Предоставляет базовую реализацию короткого вектора значений.|  
|[Структура short\_vector\_traits](../../../parallel/amp/reference/short-vector-traits-structure.md)|Предоставляет получение длины и типа короткого вектора.|  
|[Класс texture\_view](../../../parallel/amp/reference/texture-view-class.md)|Предоставляет доступ на чтение и запись в текстуре.|  
  
### Функции  
  
|Name|Описание|  
|----------|--------------|  
|[Функция copy](../Topic/copy%20Function.md)|Перегружен.  Копирует содержимое исходной текстуры в буфер узла назначения.|  
|[Функция copy\_async](../Topic/copy_async%20Function.md)|Перегружен.  Асинхронно копирует содержимое исходной текстуры в буфер узла назначения.|  
  
## Требования  
 **Заголовок:** amp\_graphics.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)