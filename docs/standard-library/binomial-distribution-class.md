---
title: "Класс binomial_distribution | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- binomial_distribution
- random/std::binomial_distribution
- random/std::binomial_distribution::reset
- random/std::binomial_distribution::p
- random/std::binomial_distribution::t
- random/std::binomial_distribution::param
- random/std::binomial_distribution::min
- random/std::binomial_distribution::max
- random/std::binomial_distribution::operator()
- random/std::binomial_distribution::param_type
- random/std::binomial_distribution::param_type::p
- random/std::binomial_distribution::param_type::t
- random/std::binomial_distribution::param_type::operator==
- random/std::binomial_distribution::param_type::operator!=
- random/std::binomial_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- binomial_distribution class
ms.assetid: b7c8a26a-da8c-45a5-a3a8-208f7a3609ce
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 38de1b8245612bca84c381c143b4a12e9f08c83e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="binomialdistribution-class"></a>Класс binomial_distribution
Формирует биномиальное распределение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class IntType = int>
class binomial_distribution  
   {  
public:  
   // types  
   typedef IntType result_type;  
   struct param_type;  
   
   // constructors and reset functions  
   explicit binomial_distribution(result_type t = 1, double p = 0.5);
   explicit binomial_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   result_type t() const;
   double p() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```  
#### <a name="parameters"></a>Параметры  
*IntType*  
По умолчанию целочисленный тип результата имеет тип `int`. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  
  
*РГСЧ*, механизм генератора случайных чисел. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  

## <a name="remarks"></a>Примечания  
Класс шаблона описывает распределение, которое формирует значения указанного пользователем целочисленного типа или типа `int` (если тип не указан), распределенные в соответствии с дискретной функцией вероятности биномиального распределения. В следующей таблице представлены ссылки на статьи об отдельных членах.  
  
||||  
|-|-|-|  
|[binomial_distribution](#binomial_distribution)|`binomial_distribution::t`|`binomial_distribution::param`|  
|`binomial_distribution::operator()`|`binomial_distribution::p`|[param_type](#param_type)|  
  
Члены свойств `t()` и `p()` возвращают текущие хранимые значения параметров распределения `t` и `p` соответственно.  
  
Член свойства `param()` устанавливает или возвращает хранимый пакет параметров распределения `param_type`.  

Функции-члены `min()` и `max()` возвращают наименьший и наибольший из возможных результатов соответственно.  
  
Функция-член `reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.  
  
Функции-члены `operator()` возвращают следующее значение, созданное механизмом РГСЧ, из текущего или указанного пакета параметров.
  
Дополнительные сведения о классах распределения и их членах см. в разделе [\<random>](../standard-library/random.md).  
  
Дополнительные сведения о дискретной функции вероятности биномиального распределения см. в статье [Биномиальное распределение](http://go.microsoft.com/fwlink/LinkId=398469) на веб-сайте Wolfram MathWorld.  
  
## <a name="example"></a>Пример  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const int t, const double p, const int& s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::binomial_distribution<> distr(t, p);  
  
    std::cout << std::endl;  
    std::cout << "p == " << distr.p() << std::endl;  
    std::cout << "t == " << distr.t() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Histogram for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    int    t_dist = 1;  
    double p_dist = 0.5;  
    int    samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for t distribution (where 0 <= t): ";  
    std::cin >> t_dist;  
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for a sample count: ";  
    std::cin >> samples;  
  
    test(t_dist, p_dist, samples);  
}  
```  
  
Первый запуск:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .25  
Enter an integer value for a sample count: 100  
 
p == 0.25  
t == 22  
Histogram for 100 samples:  
    1 :  
    2 ::  
    3 :::::::::::::  
    4 ::::::::::::::  
    5 :::::::::::::::::::::::::  
    6 ::::::::::::::::::  
    7 :::::::::::::  
    8 ::::::  
    9 ::::::  
    11 :  
    12 :  
```  
  
Второй запуск:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .5  
Enter an integer value for a sample count: 100  
 
p == 0.5  
t == 22  
Histogram for 100 samples:  
    6 :  
    7 ::  
    8 :::::::::  
    9 ::::::::::  
    10 ::::::::::::::::  
    11 :::::::::::::::::::  
    12 :::::::::::  
    13 :::::::::::::  
    14 :::::::::::::::  
    15 ::  
    16 ::  
```  
  
Третий запуск:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .75  
Enter an integer value for a sample count: 100  
 
p == 0.75  
t == 22  
Histogram for 100 samples:  
    13 ::::  
    14 :::::::::::  
    15 :::::::::::::::  
    16 :::::::::::::::::::::  
    17 ::::::::::::::  
    18 :::::::::::::::::  
    19 :::::::::::  
    20 ::::::  
    21 :  
```  
  
## <a name="requirements"></a>Требования  
**Заголовок:** \<random>  
  
**Пространство имен:** std  
  
##  <a name="binomial_distribution"></a>  binomial_distribution::binomial_distribution  
Формирует распределение.  
  
```  
explicit binomial_distribution(result_type t = 1, double p = 0.5);
explicit binomial_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Параметры  
*t*  
Параметр распределения `t`.  
  
*p*  
Параметр распределения `p`.  
  
*parm*  
Структура `param_type`, используемая для формирования распределения.  
  
### <a name="remarks"></a>Примечания  
**Предусловие:** `0 ≤ t` и `0.0 ≤ p ≤ 1.0`  
  
Первый конструктор создает объект, хранимое значение `p` которого имеет значение *p*, а хранимое значение `t` — значение *t*.  
  
Второй конструктор создает объект, хранимые параметры которого инициализируются из *parm*. Вы можете получить и задать текущие параметры существующего распределения, вызвав функцию-член `param()`.  
  
##  <a name="param_type"></a>  binomial_distribution::param_type  
Сохраняет все параметры распределения.  
  
```cpp  
struct param_type {  
   typedef binomial_distribution<result_type> distribution_type;  
   param_type(result_type t = 1, double p = 0.5);
   result_type t() const;
   double p() const;
   .....  
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>Параметры  
*t*  
Параметр распределения `t`.  
  
*p*  
Параметр распределения `p`.  
  
*right*  
 Объект `param_type`, который требуется сравнить с данным объектом.  
  
### <a name="remarks"></a>Примечания  
**Предварительные условия:** `0 ≤ t` и `0.0 ≤ p ≤ 1.0`  
  
Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.  
  
## <a name="see-also"></a>См. также  
 [\<random>](../standard-library/random.md)




