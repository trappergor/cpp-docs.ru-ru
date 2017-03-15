---
title: "Класс time_put | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::time_put"
  - "time_put"
  - "xloctime/std::time_put"
  - "std.time_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put - класс"
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс time_put
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Данный класс шаблона описывает объект, который можно использовать как аспект языкового стандарта для управления преобразованием значений времени в последовательности типа `CharType`.  
  
## Синтаксис  
  
```  
template <  
   class CharType,  
   class OutputIterator = ostreambuf_iterator<CharType>  
> class time_put : public locale::facet;  
```  
  
#### Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов.  
  
 `OutputIterator`  
 Тип итератора, в который функции записи времени записывают свои выходные данные.  
  
## Заметки  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю.  Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **идентификаторе.**  
  
### Конструкторы  
  
|||  
|-|-|  
|[time\_put](../Topic/time_put::time_put.md)|Конструктор для объектов типа `time_put`.|  
  
### Определения типов  
  
|||  
|-|-|  
|[char\_type](../Topic/time_put::char_type.md)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[iter\_type](../Topic/time_put::iter_type.md)|Тип, который описывает итератор вывода.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[do\_put](../Topic/time_put::do_put.md)|Виртуальная функция, выводящая информацию о времени и дате в виде последовательности `CharType`.|  
|[put](../Topic/time_put::put.md)|Выводит информацию о времени и дате в виде последовательности `CharType`.|  
  
## Требования  
 **Заголовок:** \<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<locale\>](../standard-library/locale.md)   
 [Класс time\_base](../Topic/time_base%20Class.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)