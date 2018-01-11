---
title: "Vector::Vector (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::vector
dev_langs: C++
helpviewer_keywords: vector member [STL/CLR]
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a321e18c9fc921e1d88961b4f282c29917fa7962
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vectorvector-stlclr"></a>vector::vector (STL/CLR)
Создает объект контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 count  
 Число элементов для вставки.  
  
 first  
 Начало диапазона для вставки.  
  
 last  
 Конец диапазона для вставки.  
  
 right  
 Объект или диапазон для вставки.  
  
 функция Val  
 Значение элемента, который требуется вставить.  
  
## <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `vector();`  
  
 Инициализирует управляемой последовательности без элементов. Используется, чтобы указать пустую начальную управляемую последовательность.  
  
 Конструктор:  
  
 `vector(vector<Value>% right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right.begin()`, `right.end()`). Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объекте vector `right`.  
  
 Конструктор:  
  
 `vector(vector<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right->begin()`, `right->end()`). Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект vector, дескриптор которого `right`.  
  
 Конструктор:  
  
 `explicit vector(size_type count);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `value_type()`. Используется для заполнения контейнера с элементами, каждый из которых по умолчанию.  
  
 Конструктор:  
  
 `vector(size_type count, value_type val);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `val`. Используется для заполнения элементов контейнера всех, имеющих то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`). Используется для создания копии другой последовательности управляемой последовательности.  
  
 Конструктор:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`. Используется для создания копии другой последовательности, описываемого перечислитель управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/vector >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)   
 [Vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)