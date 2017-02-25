---
title: "Класс binder2nd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.binder2nd"
  - "binder2nd"
  - "xfunctional/std::binder2nd"
  - "std::binder2nd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder2nd - класс"
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс binder2nd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблонный класс, предоставляющий данный конструктор, который выполняет преобразование бинарный объект функции в унарный объект функции путем связывания второй аргумент функции бинарной указанное значение.  
  
## Синтаксис  
  
```  
template<class Operation>  
   class binder2nd  
      : public unary_function <  
         typename Operation::first_argument_type,  
         typename Operation::result_type>   
   {  
   public:  
   typedef typename Operation::argument_type argument_type;  
   typedef typename Operation::result_type result_type;  
   binder2nd(  
      const Operation& _Func,  
      const typename Operation::second_argument_type& _Right  
   );  
   result_type operator()(  
      const argument_type& _Left  
   ) const;  
   result_type operator()(  
      argument_type& _Left  
   ) const;  
   protected:  
   Operation op;  
   typename Operation::second_argument_type value;  
   };  
```  
  
#### Параметры  
 `_Func`  
 Бинарный объект функции, в который выполняется преобразование унарному объект функции.  
  
 `_Right`  
 Значение, второй аргумент бинарного объекта функции быть привязанным.  
  
 `_Left`  
 Значение аргумента, приспособленный бинарный сравнивает объект к фиксированному значению второго аргумента.  
  
## Возвращаемое значение  
 Унарный объект функции, результаты из привязки второй аргумент бинарного объекта функции значение `_Right.`  
  
## Заметки  
 Класс шаблона сохранить копию бинарного \_Func объекта функции в **op**, и копия `_Right` в **value**.  Он определяет свою функцию\-член `operator()` как возвращающий **op**\(`_Left`, **value**\).  
  
 Если `_Func` объект типа **Операция** и C — константа, [bind2nd](../Topic/bind2nd%20Function.md) \( `_Func`, `c` \) аналогичен конструктору `binder2nd`\<**Операция**\> класса `binder2nd` \( `_Func`, `c` \) и удобное.  
  
## Пример  
  
```  
// functional_binder2nd.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int>::iterator Iter;  
  
    int i;  
    for (i = 0; i <= 5; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    // Count the number of integers > 10 in the vector  
    vector<int>::iterator::difference_type result1;  
    result1 = count_if(v1.begin(), v1.end(),  
        binder2nd<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare using binder1st fixing 1st argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder1st<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 less than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **Вектор v1 \= \(0 5 10 15 20 25\)**  
**Количество элементов в v1 большего, чем 10 выглядит следующим образом: 3.**  
**Количество элементов в v1 меньше 10 выглядит следующим образом: 2.**   
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)