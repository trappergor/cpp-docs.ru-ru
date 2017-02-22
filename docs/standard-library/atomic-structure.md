---
title: "Структура atomic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "atomic/std::atomic"
dev_langs: 
  - "C++"
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Структура atomic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, выполняющий атомарных операций, хранящиеся в значение типа `Ty`.  
  
## Синтаксис  
  
```  
template <class Ty>  
struct atomic;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор atomic::atomic](../Topic/atomic::atomic%20Constructor.md)|Построение атомарный объект.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор atomic::operator Ty](../Topic/atomic::operator%20Ty%20Operator.md)|Считывает и возвращает сохраненный значение. \([Метод atomic::load](../Topic/atomic::load%20Method.md)\)|  
|[Оператор atomic::operator\=](../Topic/atomic::operator=%20Operator.md)|Использует указанное значение, чтобы заменить, хранящееся значение. \([Метод atomic::store](../Topic/atomic::store%20Method.md)\)|  
|||  
|[Оператор atomic::operator\+\+](../Topic/atomic::operator++%20Operator.md)|Увеличивает хранящееся значение.  Используется только специализациями и всей указателя.|  
|[Оператор atomic::operator\+\=](../Topic/atomic::operator+=%20Operator.md)|Добавляет указанное хранящееся значение.  Используется только специализациями и всей указателя.|  
|[Оператор atomic::operator\-\-](../Topic/atomic::operator--%20Operator.md)|Уменьшает хранящееся значение.  Используется только специализациями и всей указателя.|  
|[Оператор atomic::operator\-\=](../Topic/atomic::operator-=%20Operator.md)|Вычитает указанное значение из сохраненного значения.  Используется только специализациями и всей указателя.|  
|[Оператор atomic::operator&\=](../Topic/atomic::operator&=%20Operator.md)|Выполняет операцию побитового `and` на заданном значении и хранимого значения.  Используется только целочисленными специализациями.|  
|[Оператор atomic::operator&#124;\=](../Topic/atomic::operator%7C=%20Operator.md)|Выполняет операцию побитового `or` на заданном значении и хранимого значения.  Используется только целочисленными специализациями.|  
|[Оператор atomic::operator^\=](../Topic/atomic::operator%5E=%20Operator.md)|Выполняет операцию побитового `exclusive or` на заданном значении и хранимого значения.  Используется только целочисленными специализациями.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод atomic::compare\_exchange\_strong](../Topic/atomic::compare_exchange_strong%20Method.md)|Выполняет операцию `atomic_compare_and_exchange` на `this` и возвращает результат.|  
|[Метод atomic::compare\_exchange\_weak](../Topic/atomic::compare_exchange_weak%20Method.md)|Выполняет операцию `weak_atomic_compare_and_exchange` на `this` и возвращает результат.|  
|[Метод atomic::fetch\_add](../Topic/atomic::fetch_add%20Method.md)|Добавляет указанное хранящееся значение.|  
|[Метод atomic::fetch\_and](../Topic/atomic::fetch_and%20Method.md)|Выполняет операцию побитового `and` на заданном значении и хранимого значения.|  
|[Метод atomic::fetch\_or](../Topic/atomic::fetch_or%20Method.md)|Выполняет операцию побитового `or` на заданном значении и хранимого значения.|  
|[Метод atomic::fetch\_sub](../Topic/atomic::fetch_sub%20Method.md)|Вычитает указанное значение из сохраненного значения.|  
|[Метод atomic::fetch\_xor](../Topic/atomic::fetch_xor%20Method.md)|Выполняет операцию побитового `exclusive or` на заданном значении и хранимого значения.|  
|[Метод atomic::is\_lock\_free](../Topic/atomic::is_lock_free%20Method.md)|Определяет, является ли атомарных операций на `this`*блокировка не*.  Атомарный тип *блокировка не* при отсутствии атомарные операции с этими использовании типа не блокируют.|  
|[Метод atomic::load](../Topic/atomic::load%20Method.md)|Считывает и возвращает сохраненный значение.|  
|[Метод atomic::store](../Topic/atomic::store%20Method.md)|Использует указанное значение, чтобы заменить, хранящееся значение.|  
  
## Заметки  
 Тип `Ty` должен быть *тривиальным копируемым*.  То есть, используя [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), чтобы скопировать его в байтах должен создать допустимого объекта `Ty`, сравнивает равенство в исходный объект.  Функции\-члены `compare_exchange_weak` и `compare_exchange_strong` используют [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md), чтобы определить, является ли значения `Ty` равны 2.  Эти функции не используется `Ty`\- указанное `operator==`.  Функции\-члены `atomic` используют `memcpy` для копирования значений типа `Ty`.  
  
 Частично специализация, `atomic<Ty *>`, существует для всех типов указателя.  Специализация включает добавление смещения в управляемый указатель значение или вычитание смещения из нее.  Арифметические операции принимают аргумент типа `ptrdiff_t` и настройка этот аргумент в соответствии с размером `Ty`, чтобы быть согласованными с обычной арифметической операции адреса.  
  
 Специализация существует для каждого целого типа, за исключением `bool`.  Каждая специализация предоставляет большой набор методов для атомарной арифметической операции и логических операций.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 Целочисленные специализации являются производными от соответствующих типов `atomic_``integral`.  Например, `atomic<unsigned int>` является производным от `atomic_uint`.  
  
## Требования  
 **Заголовок:** atomic  
  
 **Пространство имен:** std  
  
## См. также  
 [\<atomic\>](../standard-library/atomic.md)   
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)