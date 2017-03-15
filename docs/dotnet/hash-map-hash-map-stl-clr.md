---
title: "hash_map::hash_map (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::hash_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map - элемент [STL/CLR]"
ms.assetid: d65eb3fa-4bf9-4186-95f8-5517c90ef1fa
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# hash_map::hash_map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект контейнера.  
  
## Синтаксис  
  
```  
hash_map();  
explicit hash_map(key_compare^ pred);  
hash_map(key_compare^ pred, hasher^ hashfn);  
hash_map(hash_map<Key, Mapped>% right);  
hash_map(hash_map<Key, Mapped>^ right);  
template<typename InIter>  
    hash_maphash_map(InIter first, InIter last);  
template<typename InIter>  
    hash_map(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_map(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### Параметры  
 first  
 Начало диапазона, который необходимо вставить.  
  
 hashfn  
 Хэш\-функция для сопоставления ключей для блокирования.  
  
 last  
 Элемент диапазона, который необходимо вставить.  
  
 pred  
 Порядок предикат для контролируемой последовательности.  
  
 правый  
 Объект или диапазон для вставки.  
  
## Заметки  
 Конструктор:  
  
 `hash_map();`  
  
 инициализирует контролируемая последовательность без элементов с предикатом `key_compare()` по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы указать пустую последовательность, начальную контролируемую с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `explicit hash_map(key_compare^ pred);`  
  
 инициализирует контролируемая последовательность без элементов, порядок с предикатом `pred` и с хэш\-функции по умолчанию.  Он используется для определения начальную контролируемую пустую последовательность, упорядочение и с заданным предикатом хэш\-функции по умолчанию.  
  
 Конструктор:  
  
 `hash_map(key_compare^ pred, hasher^ hashfn);`  
  
 инициализирует контролируемая последовательность без элементов, порядок с предикатом `pred` и с хэш\-функции `hashfn`.  Он используется для определения начальную контролируемую пустую последовательность, с указанными порядок предикатом и хэш\-функцию.  
  
 Конструктор:  
  
 `hash_map(hash_map<Key, Mapped>% right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``.`[hash\_map::begin](../dotnet/hash-map-begin-stl-clr.md)`(),` `right``.`[hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`())` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` hash\_map с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `hash_map(hash_map<Key, Mapped>^ right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``->`[hash\_map::begin](../dotnet/hash-map-begin-stl-clr.md)`(),` `right``->`[hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`())` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` hash\_map с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `hash_map(InIter first, InIter last);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `hash_map(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`, порядок с предикатом `pred` и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, упорядочение и с заданным предикатом хэш\-функции по умолчанию.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `hash_map(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`, порядок с предикатом `pred` и с хэш\-функции `hashfn`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, с указанными порядок предикатом и хэш\-функцию.  
  
 Конструктор:  
  
 `hash_map(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `hash_map(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`, порядок с предикатом `pred` и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем, с указанными порядок предикатом и хэш\-функции по умолчанию.  
  
 Конструктор:  
  
 `hash_map(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`, порядок с предикатом `pred` и с хэш\-функции `hashfn`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем, с указанными порядок предикатом и хэш\-функцию.  
  
## Пример  
  
```  
// cliext_hash_map_construct.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
// construct an empty container   
    Myhash_map c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_map c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Myhash_map::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_map c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_map::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (Myhash_map::value_type elem in c2h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_map c3(c1.begin(), c1.end());   
    for each (Myhash_map::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_map c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Myhash_map::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_map c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_map::hasher(&myfun));   
    for each (Myhash_map::value_type elem in c4h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_map c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_map::value_type>^)%c3);   
    for each (Myhash_map::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_map c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_map::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Myhash_map::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_map c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_map::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_map::hasher(&myfun));   
    for each (Myhash_map::value_type elem in c6h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_map c7(c4);   
    for each (Myhash_map::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Myhash_map c8(%c3);   
    for each (Myhash_map::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **\[1\] \[2\] \[BC — 3\]**  
**size\(\) \= 0**  
 **\[1\] \[2\] \[BC — 3\]**  
**size\(\) \= 0**  
 **C \[3\] \[2\] \[B1\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **C \[3\] \[2\] \[B1\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **C \[3\] \[2\] \[B1\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **\[1\] \[2\] \[BC — 3\]**   
## Требования  
 **Заголовок:**\<cliext\/hash\_map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::generic\_container](../dotnet/hash-map-generic-container-stl-clr.md)   
 [hash\_map::operator\=](../dotnet/hash-map-operator-assign-stl-clr.md)