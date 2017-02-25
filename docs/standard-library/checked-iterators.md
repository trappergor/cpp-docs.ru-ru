---
title: "Проверяемые итераторы | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SECURE_SCL"
  - "_SECURE_SCL_THROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проверяемые итераторы"
  - "итераторы, checked"
  - "безопасные библиотеки"
  - "безопасные библиотеки, Стандартная библиотека C++"
  - "безопасная стандартная библиотека C++"
ms.assetid: cfc87df8-e3d9-403b-ab78-e9483247d940
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# Проверяемые итераторы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверенные итераторы гарантируют отсутствие перезаписи границ контейнера.  
  
 Проверенные итераторы применяются к сборкам выпуска и отладки.  Дополнительные сведения о использовании итераторов при компиляции в режиме отладки см. в разделе [Поддержка отладки итераторов](../standard-library/debug-iterator-support.md).  
  
## Заметки  
 Дополнительные сведения об отключении предупреждений, генерируемых проверенными итераторами, см. в разделе [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
 Можно использовать следующий символ с функцией проверенного итератора.  
  
 `_SECURE_SCL`  
 Если `_SECURE_SCL` определен как 1, небезопасное использование итераторов вызовет ошибку во время выполнения, и программа будет завершена.  Если задано значение 0, проверенные итераторы блокируются.  По умолчанию для `_SECURE_SCL` в сборках выпуска используется значение 0, а в сборках отладки — значение 1.  
  
> [!IMPORTANT]
>  Используйте элемент `_ITERATOR_DEBUG_LEVEL` для управления [\_SECURE\_SCL](../standard-library/secure-scl.md).  Дополнительные сведения см. в разделе [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
 Если элемент `_SECURE_SCL` определен как 1, выполняются следующие виды проверки SCL:  
  
-   Проверяются все стандартные итераторы \(например, [vector::iterator](../Topic/vector::iterator.md)\).  
  
-   Если итератор вывода является проверенным итератором, то при обращении к стандартной функции будет продемонстрировано поведение проверенного элемента \(например, [std::copy](../Topic/copy.md)\).  
  
-   Если итератор вывода является непроверенным итератором, при обращении к стандартной функции будут отображаться предупреждения компилятора.  
  
-   Следующие функции вызовут ошибку во время выполнения при попытке получения доступа к элементу, расположенному за границами контейнера:  
  
|||||  
|-|-|-|-|  
|[basic\_string::operator](../Topic/basic_string::operator.md)|[bitset::operator](../Topic/bitset::operator.md)|[deque::back](../Topic/deque::back.md)|[deque::front](../Topic/deque::front.md)|  
|[deque::operator](../Topic/deque::operator.md)|[list::back](../Topic/list::back.md)|[list::front](../Topic/list::front.md)|[queue::back](../Topic/queue::back.md)|  
|[queue::front](../Topic/queue::front.md)|[vector::operator](../Topic/vector::operator.md)|[vector::back](../Topic/vector::back.md)|[vector::front](../Topic/vector::front.md)|  
  
 Если для `_SECURE_SCL` задано значение 0:  
  
-   Все стандартные итераторы являются непроверенными \(итераторы могут перемещаться за пределы контейнера, что вызывает неопределенное поведение\).  
  
-   Если итератор вывода является проверенным итератором, то при обращении к стандартной функции будет продемонстрировано поведение проверенного элемента \(например, `std::copy`\).  
  
-   Если итератор вывода является непроверенным итератором, то при обращении к стандартной функции будет продемонстрировано поведение непроверенного элемента \(например, `std::copy`\).  
  
 Проверяемый итератор ссылается на итератор, который обращается к `invalid_parameter_handler` при попытке перемещения за границы контейнера.  Дополнительные сведения о `invalid_parameter_handler` см. в разделе [Проверка параметров](../c-runtime-library/parameter-validation.md).  
  
 [Класс checked\_array\_iterator](../standard-library/checked-array-iterator-class.md) и [Класс unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md) являются адаптерами итератора, которые поддерживают проверенные итераторы.  
  
## Пример  
 При компиляции с помощью `_SECURE_SCL 1` ошибка во время выполнения происходит в случае попытки обращения к элементу, который находится за границами контейнера, при помощи оператора индексации определенных классов.  
  
```cpp  
// checked_iterators_1.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
    v.push_back(67);  
  
    int i = v[0];  
    cout << i << endl;  
  
    i = v[1]; // triggers invalid parameter handler  
};  
  
```  
  
 Данная программа распечатает значение "67", а затем отобразит диалоговое окно "Сбой утверждения" с дополнительной информацией о сбое.  
  
## Пример  
 Аналогичным образом, при компиляции с помощью `_SECURE_SCL 1` ошибка во время выполнения возникает в случае попытки обращения к элементу при помощи переднего или заднего плана определенных классов, если контейнер пуст.  
  
```cpp  
// checked_iterators_2.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
  
    int& i = v.front(); // triggers invalid parameter handler  
};  
  
```  
  
 Данная программа отобразит диалоговое окно "Сбой утверждения" с дополнительной информацией о сбое.  
  
 Следующий код демонстрирует различные сценарии использования итератора с комментариями о каждом.  
  
```cpp  
// cl.exe /MTd /EHsc /W4  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to STL algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## Выходные данные  
 При компиляции кода, представленного в предыдущем разделе с `cl.exe /EHsc /W4 /MTd`, отобразится следующее предупреждение компилятора; тем не менее, компиляция будет выполнена без ошибок, в результате чего будет создан исполняемый файл:  
  
```  
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters that may be unsafe - this call rel  
ies on the caller to check that the passed values are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation on how to use Visual C++ 'Checked Iterators'  
```  
  
 Выполнение исполнимого файла консольного приложения приведет к следующему результату:  
  
```  
v: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15  
v2: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30  
v3: 0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45  
a4: 0 4 8 12 16 20 24 28 32 36 40 44 48 52 56 60  
a5: 0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75  
a6: 0 6 12 18 24 30 36 42 48 54 60 66 72 78 84 90  
a7: 0 7 14 21 28 35 42 49 56 63 70 77 84 91 98 105  
a8: 0 8 16 24 32 40 48 56 64 72 80 88 96 104 112 120  
```  
  
## См. также  
 [Обзор STL](../standard-library/cpp-standard-library-overview.md)   
 [Поддержка отладки итераторов](../standard-library/debug-iterator-support.md)