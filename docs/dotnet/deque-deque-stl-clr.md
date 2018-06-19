---
title: deque::deque (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::deque
dev_langs:
- C++
helpviewer_keywords:
- deque member [STL/CLR]
ms.assetid: e5bc9511-619e-469c-b50a-e06858e7fce7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 433b6ff053db0c642c2a81a5765755c9f42e1a0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112125"
---
# <a name="dequedeque-stlclr"></a>deque::deque (STL/CLR)
Создает объект контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 `deque();`  
  
 Инициализирует управляемой последовательности без элементов. Используется, чтобы указать пустую начальную управляемую последовательность.  
  
 Конструктор:  
  
 `deque(deque<Value>% right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right.begin()`, `right.end()`). Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объекта deque `right`. Дополнительные сведения об итераторах см. в разделе [deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md) и [deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md).  
  
 Конструктор:  
  
 `deque(deque<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right->begin()`, `right->end()`). Используется для указания начальной управляемой последовательности, который представляет собой копию последовательности, управляемой с дескриптором объекта deque `right`.  
  
 Конструктор:  
  
 `explicit deque(size_type count);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `value_type()`. Используется для заполнения контейнера с элементами, каждый из которых по умолчанию.  
  
 Конструктор:  
  
 `deque(size_type count, value_type val);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `val`. Используется для заполнения элементов контейнера всех, имеющих то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`). Используется для создания копии другой последовательности управляемой последовательности.  
  
 Конструктор:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`. Используется для создания копии другой последовательности, описываемого перечислитель управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
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
 **Заголовок:** \<cliext/deque >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::Assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)   
 [deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)   
 [operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)