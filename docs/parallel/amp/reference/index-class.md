---
title: "Класс index | Microsoft Docs"
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
  - "amp/Concurrency::index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "index - структура"
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс index
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Определяет *N*\-мерную точку индекса.  
  
## Синтаксис  
  
```  
template <  
   int _Rank  
>  
class index;  
```  
  
#### Параметры  
 `_Rank`  
 Ранг или число измерений.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор index::index](../Topic/index::index%20Constructor.md)|Инициализирует новый экземпляр класса `index`.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор index::operator\-\-](../Topic/index::operator--%20Operator.md)|Уменьшает каждый элемент объекта `index`.|  
|[Оператор index::operator\(mod\)\=](../Topic/index::operator\(mod\)=%20Operator.md)|Вычисляет модуль \(остаток от деления\) каждого элемента в объекте `index` при делении этого элемента на число.|  
|[Оператор index::operator\*\=](../Topic/index::operator*=%20Operator.md)|Умножает каждый элемент объекта `index` на число.|  
|[Оператор index::operator\/\=](../Topic/index::operator-=%20Operator2.md)|Делит каждый элемент объекта `index` на число.|  
|[index::operatorOperator](../Topic/index::operatorOperator.md)|Возвращает элемент, находящийся по указанному индексу.|  
|[Оператор index::operator\+\+](../Topic/index::operator++%20Operator.md)|Увеличивает на единицу каждый элемент объекта `index`.|  
|[Оператор index::operator\+\=](../Topic/index::operator+=%20Operator.md)|Добавляет указанное число к каждому элементу объекта `index`.|  
|[Оператор index::operator\=](../Topic/index::operator=%20Operator.md)|Копирует содержимое указанного объекта `index` в данный объект.|  
|[Оператор index::operator\-\=](../Topic/index::operator-=%20Operator1.md)|Вычитает указанное число из каждого элемента объекта `index`.|  
  
### Открытые константы  
  
|Name|Описание|  
|----------|--------------|  
|[Константа index::rank](../Topic/index::rank%20Constant.md)|Хранит ранг объекта `index`.|  
  
## Иерархия наследования  
 `index`  
  
## Примечания  
 Структура `index` представляет координатный вектор из *N* целых чисел, указывающий уникальный позицию в *N*\-мерном пространстве.  Значения в векторе упорядочены от наиболее значимых к наименее значимым.  Можно получить значения компонентов с помощью [Оператор index::operator\=](../Topic/index::operator=%20Operator.md).  
  
## Требования  
 **Заголовок:** amp.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)