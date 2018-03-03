---
title: "hash_multiset::Insert (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: e7254f30-a514-4ddc-bf53-38aafbe9e8eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3e309fa84ad67b7148ae92d95fa083c24173b6c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetinsert-stlclr"></a>hash_multiset::insert (STL/CLR)
Добавляет элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Начало диапазона для вставки.  
  
 last  
 Конец диапазона для вставки.  
  
 right  
 Перечисление для вставки.  
  
 функция Val  
 Значение ключа для вставки.  
  
 где  
 Место в контейнере для вставки (указание).  
  
## <a name="remarks"></a>Примечания  
 Каждая из функций-членов вставляет последовательности, указанной оставшимися операндами.  
  
 Первая функция-член вставляет элемент со значением `val`и возвращает итератор, указывающий на вставленный элемент. Используется для вставки одного элемента.  
  
 Вторая функция-член вставляет элемент со значением `val`, с использованием `where` как подсказка (для повышения производительности) и возвращает итератор, указывающий на вставленный элемент. Используется для вставки один элемент, который может быть смежными элементу известно.  
  
 Третья функция-член вставляет последовательность [`first`, `last`). Используется для вставки ноль или более элементов, копируемых из другой последовательности.  
  
 Четвертая функция-член вставляет последовательность, назначенному с помощью `right`. Используется для вставки последовательности, описываемого перечислителя.  
  
 Каждый элемент вставки время пропорционально логарифму числа элементов в управляемой последовательности. Вставка может быть выполнена в константном времени амортизацию, тем не менее, учитывая подсказку, которая выделяет элемент курсор рядом.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_multiset_insert.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    System::Console::WriteLine("insert(L'x') = {0}",   
        *c1.insert(L'x'));   
  
    System::Console::WriteLine("insert(L'b') = {0}",   
        *c1.insert(L'b'));   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_multiset c2;   
    Myhash_multiset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_multiset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(L'x') = x  
insert(L'b') = b  
 a b b c x  
insert(begin(), L'y') = y  
 a b b c x y  
 a b b c x  
 a b b c x y  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)