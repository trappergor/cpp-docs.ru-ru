---
title: "List::UNIQUE (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::unique
dev_langs: C++
helpviewer_keywords: unique member [STL/CLR]
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 056f15dc0e7808a7f0ada7267a60e13d4c75d83b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listunique-stlclr"></a>list::unique (STL/CLR)
Удаляет смежные элементы, которые прошли заданный тест.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Параметры  
 Pred  
 Компаратор для пар элементов.  
  
## <a name="remarks"></a>Примечания  
 Первая функция-член удаляет из управляемой последовательности (стираниям) равным предшествующим элементом — каждый элемент, если элемент `X` предшествующий элемент `Y` и `X == Y`, функция-член удаляет `Y`. Используется для удаления только один копия каждой подпоследовательности соседние элементы, сравнение равенства. Обратите внимание, что если управляемой последовательности упорядочен, например путем вызова [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`, функция-член оставляет только элементы с уникальными значениями. (Поэтому они так и называются.)  
  
 Вторая функция-член работает так же, как первая, за исключением удаляет каждый элемент `Y` следующий элемент `X` которого `pred(X, Y)`. Используется для удаления копии каждой подпоследовательности соседние элементы, удовлетворяющие функции предиката или делегат, который можно указать только один. Обратите внимание, что если управляемой последовательности упорядочен, например путем вызова `sort(pred)`, функция-член оставляет только элементы, которые имеют эквивалентное упорядочение с любых других элементов.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a a b c  
a b c  
a a  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [List::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)