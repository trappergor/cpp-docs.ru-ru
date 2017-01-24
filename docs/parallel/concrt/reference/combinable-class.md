---
title: "Класс combinable | Microsoft Docs"
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
  - "ppl/concurrency::combinable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combinable - класс"
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс combinable
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Объект `combinable<T>` предназначен для предоставления потокозакрытых копий данных для выполнения свободных от блокировок потоколокальных подвычислений в процессе параллельных алгоритмов.  В конце параллельной операции потокозакрытые подвыражения могут быть объединены в окончательный результат.  Этот класс может использоваться вместо общей переменной и может привести к улучшение производительности, если бы иначе на общей переменной была сильная конкуренция.  
  
## Синтаксис  
  
```  
template<  
   typename _Ty  
>  
class combinable;  
```  
  
#### Параметры  
 `_Ty`  
 Тип данных итогового слитого результата.  Тип должен иметь конструктор копирования и конструктор по умолчанию.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор combinable::combinable](../Topic/combinable::combinable%20Constructor.md)|Перегружен.  Создает новый объект `combinable`.|  
|[Деструктор combinable::~combinable](../Topic/combinable::~combinable%20Destructor.md)|Удаляет объект `combinable`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод combinable::clear](../Topic/combinable::clear%20Method.md)|Очищает все промежуточные вычислительные результаты из предыдущего использования.|  
|[Метод combinable::combine](../Topic/combinable::combine%20Method.md)|Вычисляет окончательное значение из набора потоколокальных подвычислений, вызывая предоставленный функтор объединения.|  
|[Метод combinable::combine\_each](../Topic/combinable::combine_each%20Method.md)|Вычисляет окончательное значение из набора потоколокальных подвычислений, вызывая предоставленный функтор объединения один раз за потоколокальное подвычсиление.  Окончательный результат аккумулирован объектом функции.|  
|[Метод combinable::local](../Topic/combinable::local%20Method.md)|Перегружен.  Возвращает ссылку на потокозакрытое подвычисление.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор combinable::operator\=](../Topic/combinable::operator=%20Operator.md)|Назначает объекту `combinable` из другого объекта `combinable`.|  
  
## Заметки  
 Для получения дополнительной информации см. [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Иерархия наследования  
 `combinable`  
  
## Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)