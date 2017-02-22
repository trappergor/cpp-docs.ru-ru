---
title: "Класс seed_seq | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::seed_seq"
  - "std::tr1::seed_seq"
  - "tr1.seed_seq"
  - "seed_seq"
  - "std.tr1.seed_seq"
  - "random/std::tr1::seed_seq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "seed_seq - класс"
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс seed_seq
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Хранит вектор беззнаковых целых значений, которые можно использовать как начальное значения для механизма получения случайных чисел.  
  
## Синтаксис  
  
```  
class seed_seq  
{  
public:  
    // types  
    typedef unsigned int result_type;  
  
    // constructors  
    seed_seq();  
  
    template<class T>  
    seed_seq(initializer_list<T> initlist);  
  
    template<class InputIterator>  
    seed_seq(InputIterator begin, InputIterator end);  
  
    // generating functions  
    template<class RandomAccessIterator>  
    void generate(RandomAccessIterator begin, RandomAccessIterator end);  
  
    // property functions  
    size_t size() const;  
  
    template<class OutputIterator>  
    void param(OutputIterator dest) const;  
  
    // no copy functions  
    seed_seq(const seed_seq&) = delete;  
    void operator=(const seed_seq&) = delete;  
};  
```  
  
## Типы  
 `typedef unsigned int result_type;`   
Тип элементов последовательности начальное значение. Тип 32\-разрядное целое число без знака.  
  
## Конструкторы  
 `seed_seq();`   
По умолчанию конструктор инициализирует для пустой внутренней последовательностью.  
  
 `template<class T>`   
 `seed_seq(initializer_list<T> initlist);`   
Использует `initlist` для установки внутренней последовательности.  
`T` должен быть целочисленным типом.  
  
 `template<class InputIterator>`   
 `seed_seq(InputIterator begin, InputIterator end);`   
Инициализирует внутреннюю последовательность, используя все элементы в заданном диапазоне итератора.  
`iterator_traits<InputIterator>::value_type` должен быть целочисленным типом.  
  
## Члены  
  
### Генерирующие функции  
 `template<class RandomAccessIterator> void generate(RandomAccessIterator begin, RandomAccessIterator end);`   
Заполняет элементы предоставленной последовательности, используя внутренний алгоритм. Этот алгоритм влияет внутренняя последовательность, с которым `seed_seq` была инициализирована.  
Не выполняет никаких действий при `begin == end`.  
  
### Функции свойств  
 `size_t size() const;`   
Возвращает количество элементов в `seed_seq`.  
  
 `template<class OutputIterator> void param(OutputIterator dest) const;`   
Копирует внутреннюю последовательность в выходной итератор `dest`.  
  
## Пример  
 В следующем примере кода используются три конструктора, а при назначении массиву из полученных экземпляров `seed_seq` создаются выходные данные. Пример, использующий `seed_seq` с помощью генератора случайных чисел, в разделе [\<random\>](../standard-library/random.md).  
  
```cpp  
#include <iostream>  
#include <random>  
#include <string>  
#include <array>  
  
using namespace std;  
  
void test(const seed_seq& sseq) {  
    cout << endl << "seed_seq::size(): " << sseq.size() << endl;  
  
    cout << "seed_seq::param(): ";  
    ostream_iterator<unsigned int> out(cout, " ");  
    sseq.param(out);  
    cout << endl;  
  
    cout << "Generating a sequence of 5 elements into an array: " << endl;  
    array<unsigned int, 5> seq;  
    sseq.generate(seq.begin(), seq.end());  
    for (unsigned x : seq) { cout << x << endl; }  
}  
  
int main()  
{  
    seed_seq seed1;  
    test(seed1);  
  
    seed_seq seed2 = { 1701, 1729, 1791 };  
    test(seed2);  
  
    string sstr = "A B C D"; // seed string  
    seed_seq seed3(sstr.begin(), sstr.end());  
    test(seed3);  
}  
```  
  
## Вывод  
  
```Output  
  
seed_seq::size(): 0 seed_seq::param(): Создание последовательности из 5 элементов в массиве: 505382999 163489202 3932644188 763126080 73937346 seed_seq::size(): 3 seed_seq::param(): 1701 1729 1791 Создание последовательности из 5 элементов в массиве: 1730669648 1954224479 2809786021 1172893117 2393473414 seed_seq::size(): 7 seed_seq::param(): 65 32 66 32 67 32 68 Создание последовательности из 5 элементов в массиве : 3139879222 3775111734 1084804564 2485037668 1985355432  
```  
  
## Заметки  
 Функции\-члены этого класса не вызывают исключений.  
  
## Требования  
 **Заголовок:** \<random\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<random\>](../standard-library/random.md)