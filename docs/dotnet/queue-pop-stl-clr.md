---
title: Queue::POP (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::pop
dev_langs:
- C++
helpviewer_keywords:
- pop member [STL/CLR]
ms.assetid: 38f6c03b-e8f8-4663-b3d6-18314cdc8e7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0d3ab61f5108db8fc8c0d05262be4800c1329224
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="queuepop-stlclr"></a>queue::pop (STL/CLR)
Удаляет последний элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void pop();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член Удаляет последний элемент управляемой последовательности, который должен быть пустым. Используется для сокращения очереди на один элемент в обратной.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_queue_pop.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop();   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::push (STL/CLR)](../dotnet/queue-push-stl-clr.md)