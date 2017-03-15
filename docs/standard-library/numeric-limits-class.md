---
title: "Класс numeric_limits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::numeric_limits"
  - "std.numeric_limits"
  - "numeric_limits"
  - "limits/std::numeric_limits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс numeric_limits"
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# Класс numeric_limits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона описывает арифметические свойства встроенных числовых типов.  
  
## Синтаксис  
  
```  
template<classType> class numeric_limits  
```  
  
#### Параметры  
 `Type`  
 Базовый тип данных элемента, свойства которого проверяются, запрашиваются или устанавливаются.  
  
## Заметки  
 Заголовок определяет явные специализации для типов `wchar_t`, `bool`, `char`, `signed char`, `unsigned char`, `short`, `unsigned short`, `int`, `unsigned int`, `long`, `unsigned long`, `float`, `double`, `long double`**,** `long long`, `unsigned long long`, `char16_t` и `char32_t`. Для этих явных специализаций член [numeric\_limits::is\_specialized](../Topic/numeric_limits::is_specialized.md) является `true`, а все соответствующие элементы имеют значимые значения. Программа может предоставлять дополнительные явные специализации. Большинство функций — членов класса описывают или проверяют возможные реализации `float`.  
  
 Для произвольной специализации у членов нет значимых значений. Объект\-член, у которого нет значимых значений, сохраняет ноль \(или `false`\), а функция\-член, не возвращающая значимое значение, возвращает `Type(0)`.  
  
### Статические функции и константы  
  
|||  
|-|-|  
|[denorm\_min](../Topic/numeric_limits::denorm_min.md)|Возвращает наименьшее ненулевое денормализованное значение.|  
|[digits](../Topic/numeric_limits::digits.md)|Возвращает количество цифр основания системы счисления, которое тип может представлять без потери точности.|  
|[digits10](../Topic/numeric_limits::digits10.md)|Возвращает количество дробных десятичных цифр, которое тип может представлять без потери точности.|  
|[epsilon](../Topic/numeric_limits::epsilon.md)|Возвращает разницу между 1 и наименьшим значением больше 1, которое этот тип данных может представлять.|  
|[has\_denorm](../Topic/numeric_limits::has_denorm.md)|Проверяет, допускает ли тип денормализованные значения.|  
|[has\_denorm\_loss](../Topic/numeric_limits::has_denorm_loss.md)|Проверяет, обнаружена ли потеря точности как потеря денормализации, а не неточный результат.|  
|[has\_infinity](../Topic/numeric_limits::has_infinity.md)|Проверяет, может ли тип представлять положительную бесконечность.|  
|[has\_quiet\_NaN](../Topic/numeric_limits::has_quiet_NaN.md)|Проверяет, может ли тип представлять "тихое" нечисло \(NAN\), которое является несигнализирующим.|  
|[has\_signaling\_NaN](../Topic/numeric_limits::has_signaling_NaN.md)|Проверяет, может ли тип представлять сообщения об обнаружении нечисла \(NAN\).|  
|[infinity](../Topic/numeric_limits::infinity.md)|Представление положительной бесконечности для типа, если доступно.|  
|[is\_bounded](../Topic/numeric_limits::is_bounded.md)|Проверяет, конечен ли набор значений, представляемый типом.|  
|[is\_exact](../Topic/numeric_limits::is_exact.md)|Проверяет, не содержат ли вычисления с типом ошибок округления.|  
|[is\_iec559](../Topic/numeric_limits::is_iec559.md)|Проверяет, соответствует ли тип стандартам IEC 559.|  
|[is\_integer](../Topic/numeric_limits::is_integer.md)|Проверяет, может ли тип представлять целые числа.|  
|[is\_modulo](../Topic/numeric_limits::is_modulo.md)|Проверяет, может ли тип представлять модуль.|  
|[is\_signed](../Topic/numeric_limits::is_signed.md)|Проверяет, может ли тип представлять числа со знаком.|  
|[is\_specialized](../Topic/numeric_limits::is_specialized.md)|Проверяет, задана ли для типа явная специализация в классе шаблона `numeric_limits`.|  
|[lowest](../Topic/numeric_limits::lowest.md)|Возвращает наибольшее отрицательное конечное значение.|  
|[max](../Topic/numeric_limits::max.md)|Возвращает максимальное конечное значение типа.|  
|[max\_digits10](../Topic/numeric_limits::max_digits10.md)|Возвращает количество цифр дробной части, необходимых, чтобы у двух различных значений типа были уникальные десятичные представления.|  
|[max\_exponent](../Topic/numeric_limits::max_exponent.md)|Возвращает максимальную положительную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении основания системы счисления в эту степень.|  
|[max\_exponent10](../Topic/numeric_limits::max_exponent10.md)|Возвращает максимальную положительную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении десяти в эту степень.|  
|[min](../Topic/numeric_limits::min.md)|Возвращает минимальное нормализованное значение для типа.|  
|[min\_exponent](../Topic/numeric_limits::min_exponent.md)|Возвращает максимальную отрицательную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении основания системы счисления в эту степень.|  
|[min\_exponent10](../Topic/numeric_limits::min_exponent10.md)|Возвращает максимальную отрицательную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении десяти в эту степень.|  
|[quiet\_NaN](../Topic/numeric_limits::quiet_NaN.md)|Возвращает представление "тихого" нечисла \(NAN\) для типа.|  
|[radix](../Topic/numeric_limits::radix.md)|Возвращает целочисленное основание системы счисления, используемое для представления типа.|  
|[round\_error](../Topic/numeric_limits::round_error.md)|Возвращает максимальную ошибку округления для типа.|  
|[round\_style](../Topic/numeric_limits::round_style.md)|Возвращает значение, описывающее различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.|  
|[signaling\_NaN](../Topic/numeric_limits::signaling_NaN.md)|Возвращает представление обозначения нечисла \(NAN\) для типа.|  
|[tinyness\_before](../Topic/numeric_limits::tinyness_before.md)|Проверяет, может ли тип определить, что значение слишком мало для представления в качестве нормализованного значения, до его округления.|  
|[traps](../Topic/numeric_limits::traps.md)|Проверяет, реализованы ли для типа исключения при выполнении арифметических операций.|  
  
## Требования  
 **Заголовок:** \<limits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)