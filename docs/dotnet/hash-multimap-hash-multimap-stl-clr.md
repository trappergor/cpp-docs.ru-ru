---
title: "hash_multimap::hash_multimap (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::hash_multimap
dev_langs: C++
helpviewer_keywords: hash_multimap member [STL/CLR]
ms.assetid: a1d576a7-5dc7-4ad9-abef-ee7a13caaec3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cff49bfad9143663e8fe5d895c885918bff4a7a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimaphashmultimap-stlclr"></a>hash_multimap::hash_multimap (STL/CLR)
Создает объект контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
hash_multimap();  
explicit hash_multimap(key_compare^ pred);  
hash_multimap(key_compare^ pred, hasher^ hashfn);  
hash_multimap(hash_multimap<Key, Mapped>% right);  
hash_multimap(hash_multimap<Key, Mapped>^ right);  
template<typename InIter>  
    hash_multimaphash_multimap(InIter first, InIter last);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `hash_multimap();`  
  
 Инициализирует управляемой последовательности без элементов по умолчанию, упорядочение предикат `key_compare()`и хэш-функции по умолчанию. Используется, чтобы указать пустую начальную управляемую последовательность, по умолчанию, упорядочение предиката и хэш-функции.  
  
 Конструктор:  
  
 `explicit hash_multimap(key_compare^ pred);`  
  
 Инициализирует управляемой последовательности без элементов упорядочивания предикатом `pred`и хэш-функции по умолчанию. Используется, чтобы указать пустую начальную управляемую последовательность, с указанным предикатом порядка сортировки и хэш-функцию по умолчанию.  
  
 Конструктор:  
  
 `hash_multimap(key_compare^ pred, hasher^ hashfn);`  
  
 Инициализирует управляемой последовательности без элементов упорядочивания предикатом `pred`и хэш-функции `hashfn`. Используется, чтобы задать пустую начальную управляемую последовательность, с помощью указанного предиката и хэш-функции упорядочения.  
  
 Конструктор:  
  
 `hash_multimap(hash_multimap<Key, Mapped>% right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right.begin()`, `right.end()`), по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Они позволяют указать начальную управляемую последовательность, является копией последовательности, управляемой в объекте hash_multimap `right`с предикатом порядка сортировки по умолчанию и хэш-функции.  
  
 Конструктор:  
  
 `hash_multimap(hash_multimap<Key, Mapped>^ right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right->begin()`, `right->end()`), по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Они позволяют указать начальную управляемую последовательность, является копией последовательности, управляемой в объекте hash_multimap `right`с предикатом порядка сортировки по умолчанию и хэш-функции.  
  
 Конструктор:  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), по умолчанию, упорядочение предиката и хэш-функции по умолчанию. Используется для создания копии другой последовательности, управляемой последовательности по умолчанию, упорядочение предиката и хэш-функции.  
  
 Конструктор:  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), порядка сортировки предикатом `pred`и хэш-функции по умолчанию. Используется для создания копии другой последовательности с указанным предикатом порядка сортировки и хэш-функцию по умолчанию для управляемой последовательности.  
  
 Конструктор:  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), порядка сортировки предикатом `pred`и хэш-функции `hashfn`. Используется для создания копии другой последовательности с указанной упорядочивания предиката и хэш-функцией для управляемой последовательности.  
  
 Конструктор:  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, упорядочения предикат по умолчанию и по умолчанию хэш-функции. Используется для создания копии другой последовательности, описанные при помощи перечислителя по умолчанию, упорядочение предиката и хэш-функции для управляемой последовательности.  
  
 Конструктор:  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, порядка сортировки предикатом `pred`и хэш-функции по умолчанию. Используется для создания копии другой последовательности, описываемого перечислитель заданного порядка сортировки по умолчанию и предикат хэш-функции для управляемой последовательности.  
  
 Конструктор:  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, порядка сортировки предикатом `pred`и хэш-функции `hashfn`. Используется для создания копии другой последовательности, описываемого перечислитель, с помощью указанного предиката и хэш-функции упорядочения управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_multimap_construct.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
// construct an empty container   
    Myhash_multimap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multimap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multimap c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multimap c3(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multimap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multimap c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c4h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multimap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3);   
    for each (Myhash_multimap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multimap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multimap c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c6h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multimap c7(c4);   
    for each (Myhash_multimap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Myhash_multimap c8(%c3);   
    for each (Myhash_multimap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::generic_container (STL/CLR)](../dotnet/hash-multimap-generic-container-stl-clr.md)   
 [hash_multimap::operator= (STL/CLR)](../dotnet/hash-multimap-operator-assign-stl-clr.md)