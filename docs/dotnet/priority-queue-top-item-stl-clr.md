---
title: "priority_queue::top_item (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::priority_queue::top_item
dev_langs:
- C++
helpviewer_keywords:
- top_item member [STL/CLR]
ms.assetid: d497403b-6b1d-4c6e-a0f4-c744cc5fad75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9cc5dc2656a1083b4aaa2b6cadc731a6010968e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuetopitem-stlclr"></a>priority_queue::top_item (STL/CLR)
Обращается к элементу наивысший приоритет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
property value_type back_item;  
```  
  
## <a name="remarks"></a>Примечания  
 Свойство обращается к верхний (высший приоритет) элемент управляемой последовательности, который должен быть пустым. Используется для чтения или записи элемента наивысший приоритет, если известно, что он существует.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_priority_queue_top_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
top_item = c  
 x a b  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::top (STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)