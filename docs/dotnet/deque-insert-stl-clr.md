---
title: "deque::Insert (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::insert
dev_langs: C++
helpviewer_keywords: insert member [STL/CLR]
ms.assetid: a3b86c46-e6a8-42d0-b642-5a8f05ddd68c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 79e03fe5db67162134f5267fc54fab74e4e6b20f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dequeinsert-stlclr"></a>deque::insert (STL/CLR)
Добавляет элементы в заданной позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 `count`  
 Число элементов для вставки.  
  
 `first`  
 Начало диапазона для вставки.  
  
 `last`  
 Конец диапазона для вставки.  
  
 `right`  
 Перечисление для вставки.  
  
 `val`  
 Значение элемента, который требуется вставить.  
  
 `where`  
 Место в контейнере, чтобы вставить перед.  
  
## <a name="remarks"></a>Примечания  
 Каждый член функции вставки перед элементом, на который указывает `where` в управляемой последовательности, последовательность указанный оставшимися операндами.  
  
 Первая функция-член вставляет элемент со значением `val` и возвращает итератор, указывающий на вставленный элемент. Используется для вставки одного элемента перед импортом, назначенному с помощью итератора.  
  
 Вторая функция-член вставляет повторение `count` элементов со значением `val`. Используется для вставки ноль или более смежных элементов, которые являются все копии и то же значение.  
  
 Если `InIt` имеет целочисленный тип, первая функция-член ведет себя так же, как `insert(where, (size_type)first, (value_type)last)`. В противном случае он вставляет последовательность [`first`, `last`). Используется для вставки ноль или более смежных элементов, копируемых из другой последовательности.  
  
 Четвертая функция-член вставляет последовательность, назначенному с помощью `right`. Используется для вставки последовательности, описываемого перечислителя.  
  
 При вставке один элемент, количество копий элемента линейно количество элементов между курсор и дальнюю конец последовательности. (При вставке один или несколько элементов на любом конце последовательности, выполнено ни одной копии элемента.) Если `InIt` является итератором ввода третья функция-член выполняет один вставки для каждого элемента в последовательности. В противном случае — при вставке `N` элементов, количество копий элемента линейно `N` плюс количество элементов между курсор и дальнюю конец последовательности.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_insert.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/deque >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)