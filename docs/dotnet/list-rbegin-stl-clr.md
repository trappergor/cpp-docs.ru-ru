---
title: "List::rbegin (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: 99637376-8ac3-4e39-844a-b4f324a7c6ba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 320880a6a216cd3a494dcf28a25e9b733797846c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listrbegin-stlclr"></a>list::rbegin (STL/CLR)
Задает начало обратной управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает Обратный итератор, который задает последний элемент управляемой последовательности или начало пустую последовательность. Таким образом, он обозначает `beginning` обратной последовательности. Используется для получения итератора, который обозначает `current` начало управляемой последовательности, отображаемой в обратном порядке, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
 a y x  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)   
 [List::End (STL/CLR)](../dotnet/list-end-stl-clr.md)   
 [list::rend (STL/CLR)](../dotnet/list-rend-stl-clr.md)