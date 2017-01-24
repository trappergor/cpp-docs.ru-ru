---
title: "hash_set::hash_set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set - элемент [STL/CLR]"
ms.assetid: 006414ed-db5a-4c08-ac81-4a8ae57d0aad
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::hash_set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект контейнера.  
  
## Синтаксис  
  
```  
hash_set();  
explicit hash_set(key_compare^ pred);  
hash_set(key_compare^ pred, hasher^ hashfn);  
hash_set(hash_set<Key>% right);  
hash_set(hash_set<Key>^ right);  
template<typename InIter>  
    hash_sethash_set(InIter first, InIter last);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `hash_set();`  
  
 инициализирует контролируемая последовательность без элементов с предикатом `key_compare()` по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы указать пустую последовательность, начальную контролируемую с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `explicit hash_set(key_compare^ pred);`  
  
 инициализирует контролируемая последовательность без элементов, порядок с предикатом `pred` и с хэш\-функции по умолчанию.  Он используется для определения начальную контролируемую пустую последовательность, упорядочение и с заданным предикатом хэш\-функции по умолчанию.  
  
 Конструктор:  
  
 `hash_set(key_compare^ pred, hasher^ hashfn);`  
  
 инициализирует контролируемая последовательность без элементов, порядок с предикатом `pred` и с хэш\-функции `hashfn`.  Он используется для определения начальную контролируемую пустую последовательность, с указанными порядок предикатом и хэш\-функцию.  
  
 Конструктор:  
  
 `hash_set(hash_set<Key>% right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``.`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),` `right``.`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` hash\_set с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `hash_set(hash_set<Key>^ right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``->`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),` `right``->`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` hash\_set с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`, порядок с предикатом `pred` и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, упорядочение и с заданным предикатом хэш\-функции по умолчанию.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`, порядок с предикатом `pred` и с хэш\-функции `hashfn`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, с указанными порядок предикатом и хэш\-функцию.  
  
 Конструктор:  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right` с предикатом по умолчанию порядок и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем с предикатом и хэш\-функции по умолчанию порядок.  
  
 Конструктор:  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`, порядок с предикатом `pred` и с хэш\-функции по умолчанию.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем, с указанными порядок предикатом и хэш\-функции по умолчанию.  
  
 Конструктор:  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`, порядок с предикатом `pred` и с хэш\-функции `hashfn`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем, с указанными порядок предикатом и хэш\-функцию.  
  
## Пример  
  
```  
// cliext_hash_set_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
// construct an empty container   
    Myhash_set c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_set c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_set c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_set c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_set c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_set c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_set c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_set c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_set c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_set c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **a B C.**  
 **a b c**  
 **a b c**  
 **a B C.**  
 **a b c**  
 **a b c**  
 **a B C.**  
 **a b c**  
 **a b c**   
## Требования  
 **Заголовок:**\<cliext\/hash\_set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::generic\_container](../Topic/hash_set::generic_container%20\(STL-CLR\).md)   
 [hash\_set::operator\=](../dotnet/hash-set-operator-assign-stl-clr.md)