---
title: "hash_multiset::hash_multiset (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::hash_multiset
dev_langs:
- C++
helpviewer_keywords:
- hash_multiset member [STL/CLR]
ms.assetid: 1b224c60-b714-4ed5-9234-79b61b92a953
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b78ca2a1ecf6d2cab4639b2e7184e3fc0b6b315f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisethashmultiset-stlclr"></a>hash_multiset::hash_multiset (STL/CLR)
Создает объект контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
hash_multiset();  
explicit hash_multiset(key_compare^ pred);  
hash_multiset(key_compare^ pred, hasher^ hashfn);  
hash_multiset(hash_multiset<Key>% right);  
hash_multiset(hash_multiset<Key>^ right);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Начало диапазона для вставки.  
  
 hashfn  
 Хэш-функции для сопоставления ключей к количеству сегментов.  
  
 last  
 Конец диапазона для вставки.  
  
 Pred  
 Упорядочение предикат для управляемой последовательности.  
  
 right  
 Объект или диапазон для вставки.  
  
## <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `hash_multiset();`  
  
 Инициализирует управляемой последовательности без элементов по умолчанию, упорядочение предикат `key_compare()`и хэш-функции по умолчанию. Используется, чтобы указать пустую начальную управляемую последовательность, по умолчанию, упорядочение предиката и хэш-функции.  
  
 Конструктор:  
  
 `explicit hash_multiset(key_compare^ pred);`  
  
 Инициализирует управляемой последовательности без элементов упорядочивания предикатом `pred`и хэш-функции по умолчанию. Используется, чтобы указать пустую начальную управляемую последовательность, с указанным предикатом порядка сортировки и хэш-функцию по умолчанию.  
  
 Конструктор:  
  
 `hash_multiset(key_compare^ pred, hasher^ hashfn);`  
  
 Инициализирует управляемой последовательности без элементов упорядочивания предикатом `pred`и хэш-функции `hashfn`. Используется, чтобы задать пустую начальную управляемую последовательность, с помощью указанного предиката и хэш-функции упорядочения.  
  
 Конструктор:  
  
 `hash_multiset(hash_multiset<Key>% right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right.begin()`, `right.end()`), по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Они позволяют указать начальную управляемую последовательность, является копией последовательности, управляемой в объекте hash_multiset `right`с предикатом порядка сортировки по умолчанию и хэш-функции.  
  
 Конструктор:  
  
 `hash_multiset(hash_multiset<Key>^ right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right->begin()`, `right->end()`), по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Они позволяют указать начальную управляемую последовательность, является копией последовательности, управляемой в объекте hash_multiset `right`с предикатом порядка сортировки по умолчанию и хэш-функции.  
  
 Конструктор:  
  
 `template<typename InIter> hash_multiset(InIter first, InIter last);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Используется для создания копии другой последовательности, управляемой последовательности по умолчанию, упорядочение предиката и хэш-функции.  
  
 Конструктор:  
  
 `template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), порядка сортировки предикатом `pred`и хэш-функции по умолчанию. Используется для создания копии другой последовательности с указанным предикатом порядка сортировки и хэш-функцию по умолчанию для управляемой последовательности.  
  
 Конструктор:  
  
 `template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), порядка сортировки предикатом `pred`и хэш-функции `hashfn`. Используется для создания копии другой последовательности с указанной упорядочивания предиката и хэш-функцией для управляемой последовательности.  
  
 Конструктор:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, упорядочения предикат по умолчанию и по умолчанию хэш-функции. Используется для создания копии другой последовательности, описанные при помощи перечислителя по умолчанию, упорядочение предиката и хэш-функции для управляемой последовательности.  
  
 Конструктор:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, порядка сортировки предикатом `pred`и хэш-функции по умолчанию. Используется для создания копии другой последовательности, описываемого перечислитель заданного порядка сортировки по умолчанию и предикат хэш-функции для управляемой последовательности.  
  
 Конструктор:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, порядка сортировки предикатом `pred`и хэш-функции `hashfn`. Используется для создания копии другой последовательности, описываемого перечислитель, с помощью указанного предиката и хэш-функции упорядочения управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cliext_hash_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
// construct an empty container   
    Myhash_multiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multiset c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multiset c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multiset c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_multiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 a b c  
size() = 0  
 a b c  
size() = 0  
 c b a  
  
 a b c  
 a b c  
 c b a  
  
 a b c  
 a b c  
 c b a  
  
 a b c  
 a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::generic_container (STL/CLR)](../dotnet/hash-multiset-generic-container-stl-clr.md)   
 [hash_multiset::operator= (STL/CLR)](../dotnet/hash-multiset-operator-assign-stl-clr.md)