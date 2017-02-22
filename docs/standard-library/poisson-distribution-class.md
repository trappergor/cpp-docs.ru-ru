---
title: "Класс poisson_distribution | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "poisson_distribution"
  - "std.tr1.poisson_distribution"
  - "random/std::tr1::poisson_distribution"
  - "std::tr1::poisson_distribution"
  - "tr1.poisson_distribution"
  - "tr1::poisson_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "poisson_distribution - класс"
  - "poisson_distribution - класс [TR1]"
ms.assetid: 09614281-349a-45f7-8e95-c0196be0a937
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс poisson_distribution
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Формирует распределение Пуассона.  
  
## Синтаксис  
  
```  
template<class IntType = int> class poisson_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit poisson_distribution(double mean = 1.0);     explicit poisson_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     double mean() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### Параметры  
 `IntType`  
 По умолчанию целочисленный тип результата имеет тип `int`.  Возможные типы см. в разделе [\<random\>](../standard-library/random.md).  
  
## Заметки  
 Класс шаблона описывает распределение, получающее значения указанного пользователем целочисленного типа с распределением Пуассона.  В следующей таблице представлены ссылки на статьи об отдельных членах.  
  
||||  
|-|-|-|  
|[poisson\_distribution::poisson\_distribution](../Topic/poisson_distribution::poisson_distribution.md)|`poisson_distribution::mean`|`poisson_distribution::param`|  
|`poisson_distribution::operator()`||[poisson\_distribution::param\_type](../Topic/poisson_distribution::param_type.md)|  
  
 Функция свойства `mean()` возвращает значение для хранимого параметра распределения `mean`.  
  
 Дополнительные сведения о классах распределений и их членах см. в разделе [\<random\>](../standard-library/random.md).  
  
 Дополнительные сведения о распределении Пуассона см. в статье [Распределение Пуассона](http://go.microsoft.com/fwlink/?LinkId=401112) на веб\-сайте Wolfram MathWorld.  
  
## Пример  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::poisson_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.mean() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double p_dist = 1.0;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
  
```  
  
## Вывод  
 Первый тест.  
  
  **Для пропуска ввода данных и запуска со значениями по умолчанию нажмите CTRL\-Z.  Введите значение с плавающей запятой для параметра mean \(значение должно быть больше нуля\): 1**  
**Введите целое число точек данных: 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 1,0000000000**  
**Распределение для 100 точек данных:**  
 **0 ::::::::::::::::::::::::::::::**  
 **1 ::::::::::::::::::::::::::::::::::::::**  
 **2 :::::::::::::::::::::::**  
 **3 ::::::::**  
 **5 :**  Второй тест.  
  
  **Для пропуска ввода данных и запуска со значениями по умолчанию нажмите CTRL\-Z.  Введите значение с плавающей запятой для параметра mean \(значение должно быть больше нуля\): 10**  
**Введите целое число точек данных: 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 10,0000000000**  
**Распределение для 100 точек данных:**  
 **3 :**  
 **4 ::**  
 **5 ::**  
 **6 ::::::::**  
 **7 ::::**  
 **8 ::::::::**  
 **9 ::::::::::::::**  
 **10 ::::::::::::**  
 **11 ::::::::::::::::**  
 **12 :::::::::::::::**  
 **13 ::::::::**  
 **14 ::::::**  
 **15 :**  
 **16 ::**  
 **17 :**    
## Требования  
 **Заголовок:** \<random\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<random\>](../standard-library/random.md)