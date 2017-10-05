---
title: "Класс uniform_int_distribution | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::uniform_int_distribution
- random/std::uniform_int_distribution::reset
- random/std::uniform_int_distribution::a
- random/std::uniform_int_distribution::b
- random/std::uniform_int_distribution::param
- random/std::uniform_int_distribution::min
- random/std::uniform_int_distribution::max
- random/std::uniform_int_distribution::operator()
- random/std::uniform_int_distribution::param_type
- random/std::uniform_int_distribution::param_type::a
- random/std::uniform_int_distribution::param_type::b
- random/std::uniform_int_distribution::param_type::operator==
- random/std::uniform_int_distribution::param_type::operator!=
- random/std::uniform_int_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- std::uniform_int_distribution [C++]
- std::uniform_int_distribution [C++], reset
- std::uniform_int_distribution [C++], a
- std::uniform_int_distribution [C++], b
- std::uniform_int_distribution [C++], param
- std::uniform_int_distribution [C++], min
- std::uniform_int_distribution [C++], max
- std::uniform_int_distribution [C++], param_type
- std::uniform_int_distribution [C++], param_type
ms.assetid: a1867dcd-3bd9-4787-afe3-4b62692c1d04
caps.latest.revision: 20
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 1b428e560a51c37037244596804f075e42d4c8eb
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="uniformintdistribution-class"></a>Класс uniform_int_distribution
Формирует равномерное (каждое значение одинаково вероятно) распределение целых чисел в выходном инклюзивно-эксклюзивном диапазоне.  
  
## <a name="syntax"></a>Синтаксис  
```  
template<class IntType = int>
   class uniform_int_distribution {
public:    
   // types 
   typedef IntType result_type;    
   struct param_type;    
   
   // constructors and reset functions 
   explicit uniform_int_distribution(
      result_type a = 0, result_type b = numeric_limits<result_type>::max());
   explicit uniform_int_distribution(const param_type& parm);
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
*IntType*  
По умолчанию целочисленный тип результата имеет тип `int`. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Примечания  
Класс шаблона описывает инклюзивно-инклюзивное распределение, которое формирует значения заданного пользователем целочисленного типа, вероятность получения каждого из которых одинакова. В следующей таблице представлены ссылки на статьи об отдельных членах.  
  
||||  
|-|-|-|  
|[uniform_int_distribution](#uniform_int_distribution)|`uniform_int_distribution::a`|`uniform_int_distribution::param`|  
|`uniform_int_distribution::operator()`|`uniform_int_distribution::b`|[param_type](#param_type)|  
  
Член свойства `a()` возвращает текущее хранимое минимальное значение распределения, а `b()` возвращает текущее хранимое максимальное значение. Для класса распределения эти минимальные и максимальные значения совпадают со значениями, которые возвращаются функциями свойств `min()` и `max()`.  
  
Член свойства `param()` устанавливает или возвращает пакет хранимого пакета распределения `param_type`.  

Функции-члены `min()` и `max()` возвращают наименьший и наибольший из возможных результатов соответственно.  
  
Функция-член `reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.  
  
Функции-члены `operator()` возвращают следующее значение, созданное механизмом РГСЧ, из текущего или указанного пакета параметров.
  
Дополнительные сведения о классах распределения и их членах см. в разделе [\<random>](../standard-library/random.md).  
  
## <a name="example"></a>Пример  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const int a, const int b, const int s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::uniform_int_distribution<> distr(a, b);  
  
    std::cout << "lower bound == " << distr.a() << std::endl;  
    std::cout << "upper bound == " << distr.b() << std::endl;  
  
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
    int a_dist = 1;  
    int b_dist = 10;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for the lower bound of the distribution: ";  
    std::cin >> a_dist;  
    std::cout << "Enter an integer value for the upper bound of the distribution: ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the lower bound of the distribution: 0
Enter an integer value for the upper bound of the distribution: 12
Enter an integer value for the sample count: 200
lower bound == 0
upper bound == 12
Distribution for 200 samples:
    0 :::::::::::::::
    1 :::::::::::::::::::::
    2 ::::::::::::::::::
    3 :::::::::::::::
    4 :::::::
    5 :::::::::::::::::::::
    6 :::::::::::::
    7 ::::::::::
    8 :::::::::::::::
    9 :::::::::::::
   10 ::::::::::::::::::::::
   11 :::::::::::::
   12 :::::::::::::::::
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<random>  
  
 **Пространство имен:** std  
  
##  <a name="uniform_int_distribution"></a>  uniform_int_distribution::uniform_int_distribution  
Формирует распределение.  
  
```  
explicit uniform_int_distribution(
   result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
explicit uniform_int_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Параметры  
*a*  
Нижняя граница случайных значений (инклюзивно).  
  
*b*  
Верхняя граница случайных значений (инклюзивно).  
  
*parm*  
Структура `param_type`, используемая для формирования распределения.  
  
### <a name="remarks"></a>Примечания  
**Предусловие:** `a ≤ b`  
  
Первый конструктор создает объект, хранимое значение `a` которого содержит значение *a*, а значение `b` содержит значение *b*.  
  
Второй конструктор создает объект, хранимые параметры которого инициализируются из *parm*. Вы можете получить и задать текущие параметры существующего распределения, вызвав функцию-член `param()`.  
  
##  <a name="param_type"></a>  uniform_int_distribution::param_type  
 Сохраняет параметры распределения.  
```cpp  
struct param_type {  
   typedef uniform_int_distribution<result_type> distribution_type;  
   param_type(
      result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  

### <a name="parameters"></a>Параметры  
*a*  
Нижняя граница случайных значений (инклюзивно).  
  
*b*  
Верхняя граница случайных значений (инклюзивно).  
  
*right*  
Объект `param_type`, который требуется сравнить с данным объектом.  
  
### <a name="remarks"></a>Примечания  
**Предварительные условия:** `a ≤ b`  
  
Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.  
  
## <a name="see-also"></a>См. также  
 [\<random>](../standard-library/random.md)




