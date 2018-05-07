---
title: List::List (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::list
dev_langs:
- C++
helpviewer_keywords:
- list member [STL/CLR]
ms.assetid: 51b58f63-c65a-4d54-b746-0c10635b123b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cacfa4bb1d852a62d81d4496f19371072f2615f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="listlist-stlclr"></a>list::list (STL/CLR)
Создает объект контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 `count`  
 Число элементов для вставки.  
  
 `first`  
 Начало диапазона для вставки.  
  
 `last`  
 Конец диапазона для вставки.  
  
 `right`  
 Объект или диапазон для вставки.  
  
 `val`  
 Значение элемента, который требуется вставить.  
  
## <a name="remarks"></a>Примечания  
  
 Конструктор:  
  
 `list();`  
  
 Инициализирует управляемой последовательности без элементов. Используется, чтобы указать пустую начальную управляемую последовательность.  
  
 Конструктор:  
  
 `list(list<Value>% right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right.begin()`, `right.end()`). Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект списка `right`.  
  
 Конструктор:  
  
 `list(list<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right->begin()`, `right->end()`). Они позволяют указать начальную управляемую последовательность, является копией последовательности, управляемой с дескриптором объекта списка `right`.  
  
 Конструктор:  
  
 `explicit list(size_type count);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `value_type()`. Используется для заполнения контейнера с элементами, каждый из которых по умолчанию.  
  
 Конструктор:  
  
 `list(size_type count, value_type val);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `val`. Используется для заполнения элементов контейнера всех, имеющих то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`). Используется для создания копии другой последовательности управляемой последовательности.  
  
 Конструктор:  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`. Используется для создания копии другой последовательности, описываемого перечислитель управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
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
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [List::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)   
 [list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)