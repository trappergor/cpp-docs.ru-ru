---
title: "List::splice (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::splice
dev_langs: C++
helpviewer_keywords: splice member [STL/CLR]
ms.assetid: ebc424b9-8341-4a88-b101-86d56324f5ac
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ba4513f8ff7e6ce51a50faacbdbe08c6fca34d01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listsplice-stlclr"></a>list::splice (STL/CLR)
Restitch связи между узлами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Начало диапазона для присоединения.  
  
 last  
 Конец диапазона для присоединения.  
  
 right  
 Контейнер необходимо присоединить.  
  
 где  
 Место в контейнере для присоединения перед.  
  
## <a name="remarks"></a>Примечания  
 Первая функция-член вставляет последовательности, контролируемой `right` перед элементом в управляемой последовательности, на который указывает `where`. Она также удаляет все элементы из `right`. (`%right` не должно быть равно `this`.) Используется для присоединения всех одного списка в другой.  
  
 Вторая функция-член удаляет элемент, на который указывает `first` в последовательности, контролируемой `right` и вставляет его перед элементом в управляемой последовательности, на который указывает `where`. (Если `where` `==` `first` `||` `where` `== ++first`, изменения не происходят.) Используется для присоединения один элемент из одного списка в другой.  
  
 Третья функция-член вставляет поддиапазон, обозначенный [`first`, `last`) из последовательности, контролируемой `right` перед элементом в управляемой последовательности, на который указывает `where`. Она также удаляет исходный поддиапазон из последовательности, контролируемой `right`. (Если `right` `==` `this`, диапазона [`first`, `last`) не должен включать элемент, на который указывает `where`.) Используется для присоединения подпоследовательности ноль или более элементов из одного списка в другой.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_splice.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
c1.size() = 0  
 a b c  
 a  
 b c  
 b c a  
c2.size() = 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [List::Insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)   
 [list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)