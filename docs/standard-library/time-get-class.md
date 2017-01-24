---
title: "Класс time_get | Microsoft Docs"
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
  - "std.time_get"
  - "xloctime/std::time_get"
  - "time_get"
  - "std::time_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_get - класс"
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс time_get
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Данный класс шаблона описывает объект, который можно использовать как аспект языкового стандарта для управления преобразованиями последовательностей типа `CharType` в значения времени.  
  
## Синтаксис  
  
```  
template <  
   class CharType,  
   class InputIterator = istreambuf_iterator<CharType>  
> class time_get : public time_base;  
```  
  
#### Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов.  
  
 `InputIterator`  
 Итератор, из которого считываются значения времени.  
  
## Заметки  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю.  Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **идентификаторе.**  
  
### Конструкторы  
  
|||  
|-|-|  
|[time\_get](../Topic/time_get::time_get.md)|Конструктор для объектов типа `time_get`.|  
  
### Определения типов  
  
|||  
|-|-|  
|[char\_type](../Topic/time_get::char_type.md)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[iter\_type](../Topic/time_get::iter_type.md)|Тип, который описывает итератор ввода.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[date\_order](../Topic/time_get::date_order.md)|Возвращает порядок даты, используемый аспектом.|  
|[do\_date\_order](../Topic/time_get::do_date_order.md)|Защищенная виртуальная функция\-член, вызываемая для возврата порядка даты использовала аспектом.|  
|[do\_get](../Topic/time_get::do_get.md)|Считывает и преобразует символьные данные в значение времени.|  
|[do\_get\_date](../Topic/time_get::do_get_date.md)|Защищенная виртуальная функция\-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве даты, созданной спецификатором `x` для `strftime`.|  
|[do\_get\_monthname](../Topic/time_get::do_get_monthname.md)|Защищенная виртуальная функция\-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия месяца.|  
|[do\_get\_time](../Topic/time_get::do_get_time.md)|Защищенная виртуальная функция\-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве даты, созданной спецификатором `X` для `strftime`.|  
|[do\_get\_weekday](../Topic/time_get::do_get_weekday.md)|Защищенная виртуальная функция\-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия дня недели.|  
|[do\_get\_year](../Topic/time_get::do_get_year.md)|Защищенная виртуальная функция\-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия года.|  
|[get](../Topic/time_get::get.md)|Считывает данные из источника символьных данных и преобразует их в значение времени, сохраняемое в структуре времени.|  
|[get\_date](../Topic/time_get::get_date.md)|Анализирует строку как дату, созданную спецификатором `x` для `strftime`.|  
|[get\_monthname](../Topic/time_get::get_monthname.md)|Анализирует строку как название месяца.|  
|[get\_time](../Topic/time_get::get_time.md)|Анализирует строку как дату, созданную спецификатором `X` для `strftime`.|  
|[get\_weekday](../Topic/time_get::get_weekday.md)|Анализирует строку как название дня недели.|  
|[get\_year](../Topic/time_get::get_year.md)|Анализирует строку как название года.|  
  
## Требования  
 **Заголовок:** \<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<locale\>](../standard-library/locale.md)   
 [Класс time\_base](../Topic/time_base%20Class.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)