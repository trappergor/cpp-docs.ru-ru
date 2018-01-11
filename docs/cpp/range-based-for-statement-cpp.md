---
title: "На основе диапазона для инструкции (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43ded324227878b44f997e6539e060145ad0fb66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="range-based-for-statement-c"></a>Основанное на диапазоне выражение for (C++)
Циклически и последовательно выполняет оператор (`statement`) каждого элемента в выражении (`expression`).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      for ( for-range-declaration : expression )  
   statement   
```  
  
## <a name="remarks"></a>Примечания  
 Использовать на основе диапазонов `for` инструкции для создания циклов, которые должны выполняться по «диапазон», которая определяется как все, что можно пройти по — например, `std::vector`, или любая другая последовательность стандартной библиотеки C++, чей диапазон определяется `begin()` и `end()`. Имя, объявленном в части `for-range-declaration`, является локальным для оператора `for` и не может быть объявлено в выражении (`expression`) или операторе (`statement`). Обратите внимание, что [автоматически](../cpp/auto-cpp.md) ключевое слово является предпочтительным в `for-range-declaration` инструкции. 

 **Новые возможности Visual Studio 2017 г.:** на основе диапазонов для циклов больше не требуется, чтобы функции begin() и end() возвращают объекты того же типа. Это позволяет функции end() возвращать объект sentinel, используемый, например, диапазонами, как определено в предложении Ranges-V3. Дополнительные сведения см. в разделе [Обобщение цикла For на основе диапазона](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) и в документе о [библиотеке range-v3 на сайте GitHub](https://github.com/ericniebler/range-v3).
  
 Этот код показан способ использования на основе диапазонов `for` для перебора массива и вектора:  
  
```cpp  
// range-based-for.cpp  
// compile by using: cl /EHsc /nologo /W4  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
    // Basic 10-element integer array.  
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
  
    // Range-based for loop to iterate through the array.  
    for( int y : x ) { // Access by value using a copy declared as a specific type.   
                       // Not preferred.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    // The auto keyword causes type inference to be used. Preferred.  
  
    for( auto y : x ) { // Copy of 'x', almost always undesirable  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( auto &y : x ) { // Type inference by reference.  
        // Observes and/or modifies in-place. Preferred when modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( const auto &y : x ) { // Type inference by const reference.  
        // Observes in-place. Preferred when no modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
    cout << "end of integer array test" << endl;  
    cout << endl;  
  
    // Create a vector object that contains 10 elements.  
    vector<double> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(i + 0.14159);  
    }  
  
    // Range-based for loop to iterate through the vector, observing in-place.  
    for( const auto &j : v ) {  
        cout << j << " ";  
    }  
    cout << endl;  
    cout << "end of vector test" << endl;  
}  
  
```  
  
 Выходные данные этого кода:  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
  
 На основе диапазона `for` цикл завершается, когда один из следующих `statement` выполняется: [разрыв](../cpp/break-statement-cpp.md), [возвращают](../cpp/return-statement-cpp.md), или [goto](../cpp/goto-statement-cpp.md) к оператору с меткой за пределами на основе диапазонов **для** цикла. Объект [Продолжить](../cpp/continue-statement-cpp.md) инструкции в основанном на диапазоне `for` цикла завершает только текущую итерацию.  
  
 При работе с циклами `for`, основанными на диапазонах, рекомендуется учитывать следующие факты.  
  
-   Такие циклы автоматически распознают массивы.  
  
-   Такие циклы автоматически распознают контейнеры с методами `.begin()` и `.end()`.  
  
-   Для всех остальных итераторов в них используются поиск, зависящий от аргументов (`begin()` и `end()`).  
  
## <a name="see-also"></a>См. также  
 [Авто](../cpp/auto-cpp.md)   
 [Операторы итерации](../cpp/iteration-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор while (C++)](../cpp/while-statement-cpp.md)   
 [Оператор do-while (C++)](../cpp/do-while-statement-cpp.md)   
 [Оператор for (C++)](../cpp/for-statement-cpp.md)