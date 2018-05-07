---
title: Queue::Empty (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::empty
dev_langs:
- C++
helpviewer_keywords:
- empty member [STL/CLR]
ms.assetid: 318ccff9-23eb-4045-8c12-d3ea89159e87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8d29d910643f95629ddc2697b4c31a6bebb0fee0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="queueempty-stlclr"></a>queue::empty (STL/CLR)
Проверяет отсутствие элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [queue::size (STL/CLR)](../dotnet/queue-size-stl-clr.md)`() == 0`. Используется для проверки, является ли очередь пуста.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_queue_empty.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::size (STL/CLR)](../dotnet/queue-size-stl-clr.md)