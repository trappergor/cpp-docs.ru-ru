---
title: "&lt;chrono&gt; | Microsoft Docs"
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
  - "chrono/std::chrono::nanoseconds"
  - "chrono/std::chrono::minutes"
  - "chrono/std::chrono::seconds"
  - "<chrono>"
  - "chrono/std::chrono::hours"
  - "chrono/std::chrono::milliseconds"
  - "chrono/std::chrono::microseconds"
dev_langs: 
  - "C++"
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
caps.latest.revision: 17
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;chrono&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Включите стандартный заголовок \<chrono\> для определения классов и функций, которые представляют и манипулируют интервалами и моментами времени.  
  
 **\(Visual Studio 2015:\)** Реализация `steady_clock` была изменена для обеспечения соответствия требованиям стандарта C\+\+ к постоянству и монотонности.  `steady_clock` теперь основан на функции QueryPerformanceCounter\(\), а `high_resolution_clock` теперь является определением типа для `steady_clock`.  В результате в Visual C\+\+ `steady_clock::time_point` теперь является определением типа для `chrono::time_point<steady_clock>`, однако в других реализациях это может быть не так.  
  
## Синтаксис  
  
```cpp  
#include <chrono>  
```  
  
### Литералы  
 Литералы в заголовке \<chrono\> являются членами встроенного пространства имен literals::chrono\_literals.  Дополнительные сведения см. в разделе [Литералы chrono](../Topic/chrono%20literals.md).  
  
|||  
|-|-|  
|operator "" h\(unsigned long long Val\) operator "" h\(long double Val\)|Указывает, что значение представляет часы.|  
|operator "" min\(unsigned long long Val\)  operator "" min\(long double Val\)|Указывает, что значение представляет минуты.|  
|operator "" s\(unsigned long long Val\)operator "" s\(long double Val\)|Указывает, что значение представляет секунды.|  
|operator "" ms\(unsigned long long Val\)operator "" ms\(long double Val\)|Указывает, что значение представляет миллисекунды.|  
|operator "" us\(unsigned long long Val\)operator "" us\(long double Val\)|Указывает, что значение представляет микросекунды.|  
|operator "" ns\(unsigned long long Val\)operator "" ns\(long double Val\)|Указывает, что значение представляет наносекунды.|  
  
### Классы  
  
|Имя|Описание|  
|---------|--------------|  
|[Класс duration](../standard-library/duration-class.md)|Описывает тип, содержащий интервал времени.|  
|[Класс time\_point](../standard-library/time-point-class.md)|Описывает тип, представляющий момент времени.|  
  
### Структуры  
  
|Имя|Описание|  
|---------|--------------|  
|[Структура common\_type](../standard-library/common-type-structure.md)|Описывает специализации класса шаблона [common\_type](../standard-library/common-type-class.md) для создания экземпляров `duration` и `time_point`.|  
|[Структура duration\_values](../standard-library/duration-values-structure.md)|Предоставляет конкретные значения для параметра `Rep` шаблона `duration`.|  
|[Структура steady\_clock](../Topic/steady_clock%20struct.md)|Представляет часы `steady`.|  
|[Структура system\_clock](../standard-library/system-clock-structure.md)|Представляет *тип clock*, использующий данные системных часов в реальном времени.|  
|[Структура treat\_as\_floating\_point](../standard-library/treat-as-floating-point-structure.md)|Указывает, может ли тип рассматриваться как тип с плавающей запятой.|  
  
### Функции  
  
|Имя|Описание|  
|---------|--------------|  
|[Функция duration\_cast](../Topic/duration_cast%20Function.md)|Приводит объект `duration` к указанному типу.|  
|[Функция time\_point\_cast](../Topic/time_point_cast%20Function.md)|Приводит объект `time_point` к указанному типу.|  
  
### Операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор operator\- \(STL\)](../Topic/operator-%20Operator%20\(STL\)1.md)|Оператор вычитания или отрицания объектов `duration` и `time_point`.|  
|[Оператор operator\!\= \(STL\)](../Topic/operator!=%20Operator%20\(STL\).md)|Оператор неравенства, используемый с объектами `duration` или `time_point`.|  
|[Оператор остатка от деления \(STL\)](../Topic/operator%20modulo%20\(STL\).md)|Оператор для операций вычисления остатка от деления над объектами `duration`.|  
|[Оператор operator\* \(STL\)](../Topic/operator*%20Operator%20\(STL\).md)|Оператор умножения для объектов `duration`.|  
|[Оператор operator\/ \(STL\)](../Topic/operator-%20Operator%20\(STL\)2.md)|Оператор деления для объектов `duration`.|  
|[Оператор operator\+ \(STL\)](../Topic/operator+%20Operator%20\(STL\).md)|Складывает объекты `duration` и `time_point`.|  
|[Оператор operator\< \(STL\)](../Topic/operator%3C%20Operator%20\(STL\).md)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` меньше, чем другой объект `duration` или `time_point`.|  
|[Оператор operator\<\= \(STL\)](../Topic/operator%3C=%20Operator%20\(STL\).md)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` меньше или равен другому объекту `duration` или `time_point`.|  
|[Оператор operator\=\= \(STL\)](../Topic/operator==%20Operator%20\(STL\).md)|Определяет, справедливо ли, что два объекта `duration` представляют интервалы времени, имеющие одинаковую длину, или, что два объекта `time_point` представляют один и тот же момент времени.|  
|[Оператор operator\> \(STL\)](../Topic/operator%3E%20Operator%20\(STL\).md)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` больше, чем другой объект `duration` или `time_point`.|  
|[Оператор operator\>\= \(STL\)](../Topic/operator%3E=%20Operator%20\(STL\).md)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` больше или равен другому объекту `duration` или `time_point`.|  
  
### Предопределенные типы длительности  
 Дополнительные сведения о типах "отношение", используемых в следующих определениях типов, см. в статье [\<ratio\>](../standard-library/ratio.md).  
  
|Typedef|Описание|  
|-------------|--------------|  
|`typedef duration<long long, nano> nanoseconds;`|Синоним для типа `duration` с тактовым периодом равным 1 наносекунде.|  
|`typedef duration<long long, micro> microseconds;`|Синоним для типа `duration` с тактовым периодом равным 1 микросекунде.|  
|`typedef duration<long long, milli> milliseconds;`|Синоним для типа `duration` с тактовым периодом равным 1 миллисекунде.|  
|`typedef duration<long long> seconds;`|Синоним для типа `duration` с тактовым периодом равным 1 секунде.|  
|`typedef duration<int, ratio<60> > minutes;`|Синоним для типа `duration` с тактовым периодом равным 1 минуте.|  
|`typedef duration<int, ratio<3600> > hours;`|Синоним для типа `duration` с тактовым периодом равным 1 часу.|  
  
### Литералы  
 **\(C\+\+ 11\)** Заголовок \<chrono\> определяет следующие [определяемые пользователем литералы](../Topic/User-Defined%20Literals%20%20\(C++\).md), которые можно использовать для большего удобства, типобезопасности и обслуживаемости кода.  Такие литералы определяются во встроенном пространстве имен `literals::chrono_literals` и находятся в области действия, когда std::chrono находится в области действия.  
  
|Литерал|Описание|  
|-------------|--------------|  
|chrono::hours operator "" h\(unsigned long long Val\)|Указывает часы как целочисленное значение.|  
|chrono::duration\<double, ratio\<3600\> \> operator "" h\(long double Val\)|Указывает часы как значение с плавающей запятой.|  
|chrono::minutes \(operator "" min\)\(unsigned long long Val\)|Указывает минуты как целочисленное значение.|  
|chrono::duration\<double, ratio\<60\> \> \(operator "" min\)\( long double Val\)|Указывает минуты как значение с плавающей запятой.|  
|chrono::seconds operator "" s\(unsigned long long Val\)|Указывает минуты как целочисленное значение.|  
|chrono::duration\<double\> operator "" s\(long double Val\)|Указывает секунды как значение с плавающей запятой.|  
|chrono::milliseconds operator "" ms\(unsigned long long Val\)|Указывает миллисекунды как целочисленное значение.|  
|chrono::duration\<double, milli\> operator "" ms\(long double Val\)|Указывает миллисекунды как значение с плавающей запятой.|  
|chrono::microseconds operator "" us\(unsigned long long Val\)|Указывает микросекунды как целочисленное значение.|  
|chrono::duration\<double, micro\> operator "" us\(long double Val\)|Указывает микросекунды как значение с плавающей запятой.|  
|chrono::nanoseconds operator "" ns\(unsigned long long Val\)|Указывает наносекунды как целочисленное значение.|  
|chrono::duration\<double, nano\> operator "" ns\(long double Val\)|Указывает наносекунды как значение с плавающей запятой.|  
|||  
  
## Заметки  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)