---
title: List::rend (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::rend
dev_langs:
- C++
helpviewer_keywords:
- rend member [STL/CLR]
ms.assetid: b51030ad-1bca-42b0-b890-db47111d2921
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 19b3a1f7b6483bcf8fa839c8b20d1f261f096c2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="listrend-stlclr"></a>list::rend (STL/CLR)
Задает конец обратной управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор, указывающий начало управляемой последовательности. Таким образом, он обозначает `end` обратной последовательности. Используется для получения итератора, который обозначает `current` конец управляемой последовательности, отображаемой в обратном порядке, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_rend.cpp   
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
  
// inspect first two items   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
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
*-- --rend() = b  
*--rend() = a  
 y x c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)   
 [List::End (STL/CLR)](../dotnet/list-end-stl-clr.md)   
 [list::rbegin (STL/CLR)](../dotnet/list-rbegin-stl-clr.md)