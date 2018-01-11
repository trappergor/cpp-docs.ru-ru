---
title: "MULTISET::MULTISET (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::multiset
dev_langs: C++
helpviewer_keywords: multiset member [STL/CLR]
ms.assetid: a6ddb2df-d7cd-4b12-aee7-81da1f67f57f
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9d6698941c0660cb7a2bf72f68621ad049640373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multisetmultiset-stlclr"></a>multiset::multiset (STL/CLR)
Создает объект контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
multiset();  
explicit multiset(key_compare^ pred);  
multiset(multiset<Key>% right);  
multiset(multiset<Key>^ right);  
template<typename InIter>  
    multisetmultiset(InIter first, InIter last);  
template<typename InIter>  
    multiset(InIter first, InIter last,  
        key_compare^ pred);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Начало диапазона для вставки.  
  
 last  
 Конец диапазона для вставки.  
  
 Pred  
 Упорядочение предикат для управляемой последовательности.  
  
 right  
 Объект или диапазон для вставки.  
  
## <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `multiset();`  
  
 Инициализирует управляемой последовательности без элементов по умолчанию, упорядочение предикат `key_compare()`. Используется, чтобы указать пустую начальную управляемую последовательность, по умолчанию, упорядочение предикат.  
  
 Конструктор:  
  
 `explicit multiset(key_compare^ pred);`  
  
 Инициализирует управляемой последовательности без элементов упорядочивания предикатом `pred`. Используется, чтобы указать пустую начальную управляемую последовательность, с указанным предикатом порядка сортировки.  
  
 Конструктор:  
  
 `multiset(multiset<Key>% right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right.begin()`, `right.end()`), по умолчанию, упорядочение предиката. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект мультинабора `right`, по умолчанию, упорядочение предиката.  
  
 Конструктор:  
  
 `multiset(multiset<Key>^ right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right->begin()`, `right->end()`), по умолчанию, упорядочение предиката. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект мультинабора `right`, по умолчанию, упорядочение предиката.  
  
 Конструктор:  
  
 `template<typename InIter> multiset(InIter first, InIter last);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), по умолчанию, упорядочение предиката. Используется для создания копии другой последовательности, управляемой последовательности с упорядочения предикат по умолчанию.  
  
 Конструктор:  
  
 `template<typename InIter> multiset(InIter first, InIter last, key_compare^ pred);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`), порядка сортировки предикатом `pred`. Используется для создания копии другой последовательности с указанным предикатом упорядочения управляемой последовательности.  
  
 Конструктор:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, по умолчанию, упорядочение предиката. Используется для создания копии другой последовательности, описанные при помощи перечислителя по умолчанию, упорядочение предикат управляемой последовательности.  
  
 Конструктор:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`, порядка сортировки предикатом `pred`. Используется для создания копии другой последовательности, описываемого перечислитель с указанным предикатом упорядочения управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
// construct an empty container   
    Mymultiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mymultiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultiset c8(%c3);   
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
 c b a  
 a b c  
 c b a  
 a b c  
 c b a  
 c b a  
 a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [мультинабор (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [MULTISET::generic_container (STL/CLR)](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::operator= (STL/CLR)](../dotnet/multiset-operator-assign-stl-clr.md)