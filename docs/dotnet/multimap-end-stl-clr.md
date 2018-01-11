---
title: "multimap::End (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::end
dev_langs: C++
helpviewer_keywords: end member [STL/CLR]
ms.assetid: 8d3f9347-794d-4bd3-9bd1-50534fcf4ffe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c86d899c3eee1a6238963bcc8b8f3c4855030a32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multimapend-stlclr"></a>multimap::end (STL/CLR)
Задает конец управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает двунаправленный итератор, указывающий на место сразу за конец управляемой последовательности. Используется для получения итератора, который задает конец управляемой последовательности; его состояние не изменяется при изменении длины управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_multimap_end.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Mymultimap::iterator it = c1.end();   
    --it;   
    --it;   
    System::Console::WriteLine("*-- --end() = [{0} {1}]",   
        it->first, it->second);   
    ++it;   
    System::Console::WriteLine("*--end() = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*-- --end() = [b 2]  
*--end() = [c 3]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [несколько карт (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::begin (STL/CLR)](../dotnet/multimap-begin-stl-clr.md)