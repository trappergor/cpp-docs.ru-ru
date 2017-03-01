---
title: "&lt;complex&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <complex>
- std.<complex>
- std::<complex>
dev_langs:
- C++
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: c1753b0f4f017c6d02fc41c427285e6adae6521b
ms.lasthandoff: 02/24/2017

---
# <a name="ltcomplexgt"></a>&lt;complex&gt;
Определяет комплекс классов шаблонов контейнеров и его вспомогательные шаблоны.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <complex>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Комплексные числа — это упорядоченная пара вещественных чисел. С геометрической точки зрения комплексная плоскость — это вещественная двумерная плоскость. Отличия комплексной плоскости от вещественной состоят в том, что у нее есть дополнительная алгебраическая структура. У этой структуры есть две основные операции.  
  
-   Сложение, которое определяется как (*a, b*) + (*c, d*) = (*a + c, b + d)*  
  
-   Умножение, которое определяется как (*a, b*) \* (*c, d*) = (*ac - bd, ad + bc*)  
  
 Набор комплексных чисел с операциями комплексного сложения и комплексного умножения — это поле с точки зрения стандартной алгебры:  
  
-   Операции сложения и умножения коммутативны и ассоциативны, а умножение распределяется над сложением точно так же, как для вещественного сложения и умножения в поле вещественных чисел.  
  
-   Комплексное число (*0, 0*) представляет собой аддитивный элемент, а число (*1, 0*) — мультипликативный элемент.  
  
-   Аддитивная инверсия комплексного числа (*a, b*) — (*-a,-b*), а мультипликативная инверсия для всех таких комплексных чисел, за исключением (*0, 0*), равна  
  
     (*a*/(*a*<sup>2</sup> + *b*<sup>2</sup>), -*b*/(*a*<sup>2</sup> + *b*<sup>2</sup>)  
  
 Если представить комплексное число *z = (a, b)* в виде *z = a + bi*, где *i*<sup>2</sup> *=* -1, то правила алгебры вещественных чисел могут применяться к комплексным числам и их компонентам. Пример:  
  
 (1 + 2*i*) \* (2 + 3*i*)    = 1\*(2 + 3*i*) + 2*i*\*(2 + 3*i*) = (2 + 3*i*) + (4*i* + 6*i*<sup>2</sup>)  
  
 = (2 –6) + (3 + 4)*i* = -4 + 7*i*  
  
 Система комплексных чисел — это поле, но оно не упорядоченное. Для комплексных чисел не существует порядка, как для алгебраических или вещественных чисел и их подмножеств, поэтому отношение неравенства не может применяться к комплексным числам, как к вещественным, которые представляют собой упорядоченное поле.  
  
 Существует три общие формы представления комплексного числа *z*:  
  
-   арифметическая: *z = a + bi*  
  
-   тригонометрическая: *z = r* (cos *+ i*sin)  
  
-   показательная: *z = r \** exp()  
  
 В этих стандартных представлениях комплексных чисел используются следующие термины.  
  
-   Вещественный компонент арифметического представления или действительная часть *a*.  
  
-   Мнимый компонент арифметического представления или мнимая часть *b*.  
  
-   Модуль или абсолютное значение комплексного числа P.  
  
-   Аргумент или угол фазы.  
  
 Если не указано иное, функции, которые могут возвращать несколько значений, должны возвращать основное значение для их аргументов, которые больше -pi и меньше или равны +pi, чтобы обеспечить одно значение. Все углы должны выражаться в радианах, где в круге 2 pi радиан (360 градусов).  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[abs](../standard-library/complex-functions.md#abs)|Вычисляет модуль комплексного числа.|  
|[arg](../standard-library/complex-functions.md#arg)|Извлекает аргумент из комплексного числа.|  
|[conj](../standard-library/complex-functions.md#conj)|Возвращает комплексно-сопряженную величину комплексного числа.|  
|[cos](../standard-library/complex-functions.md#cos)|Возвращает косинус комплексного числа.|  
|[cosh](../standard-library/complex-functions.md#cosh)|Возвращает гиперболический косинус комплексного числа.|  
|[exp](../standard-library/complex-functions.md#exp)|Возвращает экспоненциальную функцию комплексного числа.|  
|[imag](../standard-library/complex-functions.md#imag)|Извлекает мнимую часть комплексного числа.|  
|[log](../standard-library/complex-functions.md#log)|Возвращает натуральный логарифм комплексного числа.|  
|[log10](../standard-library/complex-functions.md#log10)|Возвращает десятичный логарифм комплексного числа.|  
|[norm](../standard-library/complex-functions.md#norm)|Извлекает норму комплексного числа.|  
|[polar](../standard-library/complex-functions.md#polar)|Возвращает комплексное число, соответствующее указанному модулю и аргументу, в декартовой форме.|  
|[pow](../standard-library/complex-functions.md#pow)|Вычисляет комплексное число, получаемое в результате возведения основания (комплексное число) в степень другого комплексного числа.|  
|[real](../standard-library/complex-functions.md#real)|Извлекает вещественную часть комплексного числа.|  
|[sin](../standard-library/complex-functions.md#sin)|Возвращает синус комплексного числа.|  
|[sinh](../standard-library/complex-functions.md#sinh)|Возвращает гиперболический синус комплексного числа.|  
|[sqrt](../standard-library/complex-functions.md#sqrt)|Возвращает квадратный корень комплексного числа.|  
|[tan](../standard-library/complex-functions.md#tan)|Возвращает тангенс комплексного числа.|  
|[tanh](../standard-library/complex-functions.md#tanh)|Возвращает гиперболический тангенс комплексного числа.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[operator!=](../standard-library/complex-operators.md#operator_neq)|Проверяет на неравенство два комплексных числа, по крайней мере одно из которых может принадлежать к подмножеству типа для вещественной и мнимой частей.|  
|[operator*](../standard-library/complex-operators.md#operator_star)|Умножает два комплексных числа, по крайней мере одно из которых может принадлежать к подмножеству типа для вещественной и мнимой частей.|  
|[operator+](../standard-library/complex-operators.md#operator_add)|Складывает два комплексных числа, по крайней мере одно из которых может принадлежать к подмножеству типа для вещественной и мнимой частей.|  
|[operator-](../standard-library/complex-operators.md#operator-)|Вычитает два комплексных числа, по крайней мере одно из которых может принадлежать к подмножеству типа для вещественной и мнимой частей.|  
|[operator/](../standard-library/complex-operators.md#operator_)|Делит два комплексных числа, по крайней мере одно из которых может принадлежать к подмножеству типа для вещественной и мнимой частей.|  
|[operator<\<](../standard-library/complex-operators.md#operator_lt__lt_)|Функция шаблона, вставляющая комплексное число в поток вывода.|  
|[operator==](../standard-library/complex-operators.md#operator_eq_eq)|Проверяет на равенство два комплексных числа, по крайней мере одно из которых может принадлежать к подмножеству типа для вещественной и мнимой частей.|  
|[operator>>](../standard-library/complex-operators.md#operator_gt__gt_)|Функция шаблона, извлекающая комплексное число из входного потока.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[complex\<double>](../standard-library/complex-double.md)|Явно специализированный класс шаблона, описывающий объект, который хранит упорядоченную пару объектов типа **double***,*; первый представляет действительную часть комплексного числа, а второй — мнимую.|  
|[complex\<float>](../standard-library/complex-float.md)|Явно специализированный класс шаблона, описывающий объект, который хранит упорядоченную пару объектов типа **float***,*; первый представляет действительную часть комплексного числа, а второй — мнимую.|  
|[complex\<long double>](../standard-library/complex-long-double.md)|Явно специализированный класс шаблона, описывающий объект, который хранит упорядоченную пару объектов типа `long double`*,*; первый представляет действительную часть комплексного числа, а второй — мнимую.|  
|[complex](../standard-library/complex-class.md)|Этот класс шаблона описывает объект, используемый для представления системы комплексных чисел и выполнения сложных арифметических операций.|  
  
### <a name="literals"></a>Литералы  
 Заголовок \<complex> определяет следующие [пользовательские литералы](../cpp/user-defined-literals-cpp.md), которые создают комплексное число с нулевой действительной частью и мнимой частью, являющейся значением входного параметра.  
  
|||  
|-|-|  
|`constexpr complex<long double> operator""il(long double d)il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|Возвращает `complex<long double>{0.0L, static_cast<long double>(d)}`.|  
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|Возвращает `complex<double>{0.0, static_cast<double>(d)}`.|  
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|Возвращает `complex<float>{0.0f, static_cast<float>(d)}`.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




