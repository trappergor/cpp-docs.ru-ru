---
title: "Класс binder1st | Microsoft Docs"
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
  - "xfunctional/std::binder1st"
  - "std::binder1st"
  - "binder1st"
  - "std.binder1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder1st - класс"
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
caps.latest.revision: 22
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс binder1st
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблонный класс, предоставляющий данный конструктор, который выполняет преобразование бинарный объект функции в унарный объект функции путем связывания первый аргумент бинарной функции указанное значение.  
  
## Синтаксис  
  
```  
template<class Operation>  
class binder1st  
   : public unary_function <  
      typename Operation::second_argument_type,  
      typename Operation::result_type>   
  {  
   public:  
   typedef typename Operation::argument_type argument_type;  
   typedef typename Operation::result_type result_type;  
   binder1st(  
      const Operation & _Func,  
      const typename Operation::first_argument_type& _Left  
   );  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   protected:  
   Operation op;  
   typename Operation::first_argument_type value;  
   };  
```  
  
#### Параметры  
 `_Func`  
 Бинарный объект функции, в который выполняется преобразование унарному объект функции.  
  
 `_Left`  
 Значение, первый аргумент бинарного объекта функции быть привязанным.  
  
 `_Right`  
 Значение аргумента, приспособленный бинарный сравнивает объект к фиксированному значению второго аргумента.  
  
## Возвращаемое значение  
 Унарный объект функции, результаты из привязки первый аргумент бинарного объекта функции значение `_Left.`  
  
## Заметки  
 Класс шаблона сохранить копию объекта функции `_Func` бинарный в **op**, и копия `_Left` в **value**.  Он определяет свою функцию\-член `operator()` как возвращающий **op**\(**value**, `_Right`\).  
  
 Если `_Func` объект типа **Операция** и `c` константа, [bind1st](../Topic/bind1st%20Function.md) \( `_Func`, `c` \) аналогичен конструктору `binder1st`\<**Операция**\> класса `binder1st` \( `_Func`, `c` \) и удобное.  
  
## Пример  
  
```  
// functional_binder1st.cpp  
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
        binder1st<less<int> >(less<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare use of binder2nd fixing 2nd argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder2nd<less<int> >(less<int>(), 10));  
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