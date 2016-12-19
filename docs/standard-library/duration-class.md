---
title: "Класс duration | Microsoft Docs"
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
  - "chrono/std::chrono::duration"
dev_langs: 
  - "C++"
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс duration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание типа, содержащего *интервал времени*, затраченного времени между точками 2 времени.  
  
## Синтаксис  
  
```  
template<  
   class Rep,  
   class Period = ratio<1>  
>  
class duration;  
template<  
   class Rep,  
   class Period  
>  
class duration;  
template<  
   class Rep,  
   class Period1,  
   class Period2  
>  
class duration  
   <duration<Rep, Period1>, Period2>;  
```  
  
## Заметки  
 Аргумент `Rep` шаблона описывает тип, используемый для хранения тиканий количество часов в интервале времени.  Аргумент `Period` шаблона создание [отношение](../standard-library/ratio.md), которое описывает размер интервала, каждый такт представляет.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|[duration::period Typedef](http://msdn.microsoft.com/ru-ru/ebf2a1b9-769f-475f-8c66-cf9ed12015f2)|Представляет синоним для параметра `Period` шаблона.|  
|[duration::rep Typedef](http://msdn.microsoft.com/ru-ru/f47b8abb-ae2c-4dc8-858a-f44695156950)|Представляет синоним для параметра `Rep` шаблона.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор duration::duration](../Topic/duration::duration%20Constructor.md)|Создает объект `duration`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод duration::count](../Topic/duration::count%20Method.md)|Возвращает количество тиканий часов в интервале времени.|  
|[Метод duration::max](../Topic/duration::max%20Method.md)|Статический.  Возвращает максимально допустимое значение параметра `Ref` шаблона.|  
|[Метод duration::min](../Topic/duration::min%20Method.md)|Статический.  Возвращает наименьшее допустимое значение параметра `Ref` шаблона.|  
|[Метод duration::zero](../Topic/duration::zero%20Method.md)|Статический.  В результате возвращает `Rep`\(0\).|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор duration::operator\-](../Topic/duration::operator-%20Operator.md)|Возвращает копию объекта `duration` вместе с отрицанным счетчиком тактов.|  
|[Оператор duration::operator\-\-](../Topic/duration::operator--%20Operator.md)|Уменьшает хранимое значение счетчика тактов.|  
|[Оператор duration::operator\=](../Topic/duration::operator=%20Operator.md)|Уменьшает хранящийся остаток от деления указанное значение счетчика тактов.|  
|[Оператор duration::operator\*\=](../Topic/duration::operator*=%20Operator.md)|Умножает сохраненного указанное значение счетчика тактов.|  
|[Оператор duration::operator\/\=](../Topic/duration::operator-=%20Operator1.md)|Делит сохраненного счетчика тактов счетчиком тактов указанного объекта `duration`.|  
|[Оператор duration::operator\+](../Topic/duration::operator+%20Operator.md)|Возвращает `*this`.|  
|[Оператор duration::operator\+\+](../Topic/duration::operator++%20Operator.md)|Увеличивает хранимое значение счетчика тактов.|  
|[Оператор duration::operator\+\=](../Topic/duration::operator+=%20Operator.md)|Добавляет счетчик тактов указанного объекта `duration` на хранимый счетчик тактов.|  
|[Оператор duration::operator\-\=](../Topic/duration::operator-=%20Operator2.md)|Вычитает счетчик тактов указанного объекта `duration` из сохраненного счетчика тактов.|  
  
## Требования  
 **Заголовок:**  chrono  
  
 **Пространство имен:**  std::chrono  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [Структура duration\_values](../standard-library/duration-values-structure.md)