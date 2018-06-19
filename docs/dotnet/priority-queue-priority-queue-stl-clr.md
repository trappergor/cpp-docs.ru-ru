---
title: priority_queue::priority_queue (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue member [STL/CLR]
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8cb50eed9dbfcbe9480a6588ff10f966f1888205
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163397"
---
# <a name="priorityqueuepriorityqueue-stlclr"></a>priority_queue::priority_queue (STL/CLR)
Создает объект контейнера адаптера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### <a name="parameters"></a>Параметры  
 Продолжение  
 Контейнер для копирования.  
  
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
  
 `priority_queue();`  
  
 Создает пустой контейнер оболочку по умолчанию, упорядочение предикат. Используется, чтобы указать пустую начальную управляемую последовательность, по умолчанию, упорядочение предикат.  
  
 Конструктор:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 Создает оболочку контейнер, который является копией `right.get_container()`, порядка сортировки предикатом `right.value_comp()`. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект очереди `right`, же упорядочивания предикатом.  
  
 Конструктор:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 Создает оболочку контейнер, который является копией `right->get_container()`, порядка сортировки предикатом `right->value_comp()`. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект очереди `*right`, же упорядочивания предикатом.  
  
 Конструктор:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 Создает пустой контейнер упакованного упорядочивания предикатом `pred`. Используется, чтобы указать пустую начальную управляемую последовательность, с указанным предикатом порядка сортировки.  
  
 Конструктор:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 Создает пустой контейнер упакованного упорядочивания предикатом `pred`, помещает все элементы `cont` используется для указания начальную управляемую последовательность из существующего контейнера, с указанным предикатом порядка сортировки.  
  
 Конструктор:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last);`  
  
 Создает пустой контейнер оболочку с предикатом порядка сортировки по умолчанию, а затем помещает последовательности [`first`, `last`). Используется, чтобы указать начальную управляемую последовательность из указанного eqeuence, с указанным предикатом порядка сортировки.  
  
 Конструктор:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`  
  
 Создает пустой контейнер упакованного упорядочивания предикатом `pred`, помещает последовательности [`first`, `last`). Используется, чтобы указать начальную управляемую последовательность из указанного seqeuence, с указанным предикатом порядка сортировки.  
  
 Конструктор:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`  
  
 Создает пустой контейнер упакованного упорядочивания предикатом `pred`, помещает все элементы `cont` плюс последовательности [`first`, `last`). Используется, чтобы указать начальную управляемую последовательность из существующего контейнера и указанного seqeuence, с указанным предикатом порядка сортировки.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 c a b  
size() = 0  
 a c b  
 a c b  
 c a b  
 a c b  
 a a b c c b  
 c a b  
 c a b  
 a c b  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::Assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)