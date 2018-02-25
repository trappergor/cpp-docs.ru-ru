---
title: "Класс cauchy_distribution | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::cauchy_distribution
- random/std::cauchy_distribution::reset
- random/std::cauchy_distribution::a
- random/std::cauchy_distribution::b
- random/std::cauchy_distribution::param
- random/std::cauchy_distribution::min
- random/std::cauchy_distribution::max
- random/std::cauchy_distribution::operator()
- random/std::cauchy_distribution::param_type
- random/std::cauchy_distribution::param_type::a
- random/std::cauchy_distribution::param_type::b
- random/std::cauchy_distribution::param_type::operator==
- random/std::cauchy_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::cauchy_distribution [C++]
- std::cauchy_distribution [C++], reset
- std::cauchy_distribution [C++], a
- std::cauchy_distribution [C++], b
- std::cauchy_distribution [C++], param
- std::cauchy_distribution [C++], min
- std::cauchy_distribution [C++], max
- std::cauchy_distribution [C++], param_type
- std::cauchy_distribution [C++], param_type
ms.assetid: 21522351-f2f1-46d9-97f0-d358c932356c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 432f8ea360f80b85d34d423b41fe0bf9f4d2b5af
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cauchydistribution-class"></a>Класс cauchy_distribution
Формирует распределение Коши.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class RealType = double>  
class cauchy_distribution {  
public:  
   // types 
   typedef RealType result_type;  
   struct param_type;  
   
   // constructor and reset functions  
   explicit cauchy_distribution(result_type a = 0.0, result_type b = 1.0);
   explicit cauchy_distribution(const param_type& parm);
   void reset();
   
   // generating functions 
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions 
   result_type a() const;
   result_type b() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```  
  
### <a name="parameters"></a>Параметры  
*RealType*  
По умолчанию тип с плавающей запятой имеет тип `double`. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  
  
*РГСЧ*, механизм генератора случайных чисел. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  

## <a name="remarks"></a>Примечания  
Класс шаблона описывает распределение Коши, которое формирует значения указанного пользователем типа с плавающей запятой или типа `double`, если тип не указан. В следующей таблице представлены ссылки на статьи об отдельных членах.  
  
||||  
|-|-|-|  
|[cauchy_distribution](#cauchy_distribution)|`cauchy_distribution::a`|`cauchy_distribution::param`|  
|`cauchy_distribution::operator()`|`cauchy_distribution::b`|[param_type](#param_type)|  
  
Функции свойств `a()` и `b()` возвращают соответствующие значения для хранимых параметров распределения `a` и `b`.  
  
Член свойства `param()` устанавливает или возвращает хранимый пакет параметров распределения `param_type`.  

Функции-члены `min()` и `max()` возвращают наименьший и наибольший из возможных результатов соответственно.  
  
Функция-член `reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.  
  
Функции-члены `operator()` возвращают следующее значение, созданное механизмом РГСЧ, из текущего или указанного пакета параметров.
  
Дополнительные сведения о классах распределения и их членах см. в разделе [\<random>](../standard-library/random.md).  
  
Подробные сведения о нормальном F-распределении см. в статье в Wolfram MathWorld [Распределение Коши](http://go.microsoft.com/fwlink/p/?linkid=400523).  
  
## <a name="example"></a>Пример  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
  
    std::mt19937 gen(1701);  
  
    std::cauchy_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;  
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "  
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'a' distribution parameter: ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'b' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
```  
  
Первый запуск:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 0  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 0.0000000000  
b() == 1.0000000000  
Distribution for 10 samples:  
    1: -3.4650392984  
    2: -2.6369564174  
    3: -0.0786978867  
    4: -0.0609632093  
    5: 0.0589387400  
    6: 0.0589539764  
    7: 0.1004592006  
    8: 1.0965724260  
    9: 1.4389408122  
    10: 2.5253154706  
```  
  
Второй запуск:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 0  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 10  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 0.0000000000  
b() == 10.0000000000  
Distribution for 10 samples:  
    1: -34.6503929840  
    2: -26.3695641736  
    3: -0.7869788674  
    4: -0.6096320926  
    5: 0.5893873999  
    6: 0.5895397637  
    7: 1.0045920062  
    8: 10.9657242597  
    9: 14.3894081218  
    10: 25.2531547063  
```  
  
Третий запуск:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 10  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 10  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 10.0000000000  
b() == 10.0000000000  
Distribution for 10 samples:  
    1: -24.6503929840  
    2: -16.3695641736  
    3: 9.2130211326  
    4: 9.3903679074  
    5: 10.5893873999  
    6: 10.5895397637  
    7: 11.0045920062  
    8: 20.9657242597  
    9: 24.3894081218  
    10: 35.2531547063  
```  
  
## <a name="requirements"></a>Требования  
**Заголовок:** \<random>  
  
**Пространство имен:** std  
  
##  <a name="cauchy_distribution"></a>  cauchy_distribution::cauchy_distribution  
Формирует распределение.  
  
```  
explicit cauchy_distribution(result_type a = 0.0, result_type b = 1.0);
explicit cauchy_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Параметры  
*a*  
Параметр распределения `a`.  
  
*b*  
Параметр распределения `b`.  
  
*parm*  
Структура `param_type`, используемая для формирования распределения.  
  
### <a name="remarks"></a>Примечания  
**Предусловие:** `0.0 < b`  
  
Первый конструктор создает объект, хранимое значение `a` которого содержит значение *a*, а значение `b` содержит значение *b*.  
  
Второй конструктор создает объект, хранимые параметры которого инициализируются из *parm*. Вы можете получить и задать текущие параметры существующего распределения, вызвав функцию-член `param()`.  
  
##  <a name="param_type"></a>  cauchy_distribution::param_type  
Сохраняет все параметры распределения.  
  
```cpp    
struct param_type {  
   typedef cauchy_distribution<result_type> distribution_type;  
   param_type(result_type a = 0.0, result_type b = 1.0);
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>Параметры  
*a*  
Параметр распределения `a`.  
  
*b*  
Параметр распределения `b`.  
  
*right*  
Объект `param_type`, который требуется сравнить с данным объектом.  
  
### <a name="remarks"></a>Примечания  
**Предусловие:** `0.0 < b`  
  
Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.  
  
## <a name="see-also"></a>См. также  
[\<random>](../standard-library/random.md)



