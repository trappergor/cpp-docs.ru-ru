---
title: "List::Assign (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::assign
dev_langs: C++
helpviewer_keywords: assign member [STL/CLR]
ms.assetid: c5f2b131-d0e1-4188-9d4b-d617280e4032
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e4c5e670b4fca5998a21b8ae3554f31697cb3fac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listassign-stlclr"></a>list::assign (STL/CLR)
Заменяет все элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 count  
 Число элементов для вставки.  
  
 first  
 Начало диапазона для вставки.  
  
 last  
 Конец диапазона для вставки.  
  
 right  
 Перечисление для вставки.  
  
 функция Val  
 Значение элемента, который требуется вставить.  
  
## <a name="remarks"></a>Примечания  
 Первая функция-член заменяет управляемую последовательность Повтор `count` элементов со значением `val`. Используется для заполнения элементов контейнера всех, имеющих то же значение.  
  
 Если `InIt` имеет целочисленный тип, вторая функция-член работает так же, как `assign((size_type)first, (value_type)last)`. В противном случае заменяет управляемую последовательность последовательностью [`first`, `last`). Используется для управляемой последовательности копии сделать другую последовательность.  
  
 Третья функция-член заменяет управляемую последовательность последовательности, указанной с помощью перечислителя `right`. Используется, чтобы сделать копию последовательности, описываемого перечислитель управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_assign.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    cliext::list<wchar_t>::iterator it = c1.end();   
    c2.assign(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)