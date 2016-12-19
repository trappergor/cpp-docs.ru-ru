---
title: "Поддержка отладки итераторов | Microsoft Docs"
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
  - "_HAS_ITERATOR_DEBUGGING symbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "поддержка отладки итераторов"
  - "несовместимые итераторы"
  - "итераторы, поддержка отладки итераторов"
  - "итераторы, несовместимые"
  - "безопасные библиотеки"
  - "безопасные библиотеки, Стандартная библиотека C++"
  - "безопасная стандартная библиотека C++"
  - "Стандартная библиотека C++, поддержка отладки итераторов"
ms.assetid: f3f5bd15-4be8-4d64-a4d0-8bc0761c68b6
caps.latest.revision: 22
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Поддержка отладки итераторов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека времени выполнения Visual C\+\+ обнаружено неверное использование итераторов и утверждения и отображает диалоговое окно во время выполнения.  Чтобы включить отладку поддержка итераторов, необходимо использовать версию отладки библиотеки времени выполнения C — A. чтобы компилировать программы.  Для получения дополнительной информации см. [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md).  Дополнительные сведения об использовании итераторы см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).  
  
 Стандарт C\+\+ описание функции\-члены могут вызвать итераторы в контейнер стать недопустимыми.  Пример: 2  
  
-   Физического удаления элемента из контейнера итераторы приводит к элементу стать недопустимым.  
  
-   Увеличение размера [vector](../standard-library/vector.md) \(внедрения или вставка\) вызывает итераторы в `vector` стать недопустимым.  
  
## Пример  
 Если компилировать следующая программа, в режиме отладки, во время выполнения, утверждение и заканчивается.  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
  
```  
  
## Пример  
 Можно использовать символ [\_HAS\_ITERATOR\_DEBUGGING](../Topic/_HAS_ITERATOR_DEBUGGING.md) отключены функции отладки итератора в отладочном построении.  Следующая программа не утверждения, но по\-прежнему триггеры не задан расширения функциональности.  
  
> [!IMPORTANT]
>  Используйте `_ITERATOR_DEBUG_LEVEL` к элементу управления `_HAS_ITERATOR_DEBUGGING`.  Для получения дополнительной информации см. [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
```cpp  
// iterator_debugging.cpp  
// compile with: /EHsc /MDd  
#define _HAS_ITERATOR_DEBUGGING 0  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
```  
  
  **20**  
**\-572662307**   
## Пример  
 Подтверждение также происходит при попытке использования итератор до его инициализации, как показано ниже, выполните следующие действия.  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <string>  
using namespace std;  
int main() {  
   string::iterator i1, i2;  
   if (i1 == i2)  
      ;  
}  
```  
  
## Пример  
 Следующий пример кода вызывает утверждение, поскольку 2 итератора с алгоритмом [for\_each](../Topic/for_each.md) несовместимы.  Алгоритмы проверяют, чтобы определить, ссылаются ли итераторы, предоставляются на них тот же контейнер.  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <algorithm>  
#include <vector>  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int> v2;  
  
    v1.push_back(10);  
    v1.push_back(20);  
  
    v2.push_back(10);  
    v2.push_back(20);  
  
    // The next line will assert because v1 and v2 are  
    // incompatible.  
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );  
}  
```  
  
 Обратите внимание, что в этом примере лямбда\-выражение используется `[] (int& elem) { elem *= 2; }` вместо функтором.  Хотя этот вариант имеет подшипник на функтором сбоя — подтверждение, не приводит к те же сбой\- лямбда\-выражения очень удобный способ выполнения компактные задачи объекта функции.  Дополнительные сведения о лямбда\-выражениях см. в разделе [Лямбда\-выражения](../cpp/lambda-expressions-in-cpp.md).  
  
## Пример  
 Отладка итератор проверки будет переменной итератора, объявляются, что в цикле `for` будет из области видимости, область цикла `for` закончена.  
  
```cpp  
// debug_iterator.cpp  
// compile with: /EHsc /MDd  
#include <vector>  
#include <iostream>  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   for (std::vector<int>::iterator i = v.begin() ; i != v.end(); ++i)  
   ;  
   --i;   // C2065  
}  
```  
  
## Пример  
 Отладка итераторы имеют нетривиальные деструкторы.  Если деструктор не выполняется, что по какой\-либо причине, нарушения прав доступа и повреждение данных могут возникнуть.  Рассмотрим следующий пример.  
  
```cpp  
/* compile with: /EHsc /MDd */  
#include <vector>  
struct base {  
   // FIX: uncomment the next line  
   // virtual ~base() {}  
};  
  
struct derived : base {  
   std::vector<int>::iterator m_iter;  
   derived( std::vector<int>::iterator iter ) : m_iter( iter ) {}  
   ~derived() {}  
};  
  
int main() {  
   std::vector<int> vect( 10 );  
   base * pb = new derived( vect.begin() );  
   delete pb;  // doesn't call ~derived()  
   // access violation  
}  
```  
  
## См. также  
 [Обзор STL](../standard-library/cpp-standard-library-overview.md)