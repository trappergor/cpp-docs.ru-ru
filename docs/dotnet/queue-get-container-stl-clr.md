---
title: "Queue::get_container (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::get_container
dev_langs: C++
helpviewer_keywords: get_container member [STL/CLR]
ms.assetid: d87e7433-a352-4bea-8041-1ffc03287436
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1badd817ab433a8bf6ca24d488a7ee8823005c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="queuegetcontainer-stlclr"></a>queue::get_container (STL/CLR)
Обращается к базового контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
container_type^ get_container();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает базового контейнера. Используется для обхода ограничений, накладываемых на оболочку контейнера.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_queue_get_container.cpp   
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
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::container_type (STL/CLR)](../dotnet/queue-container-type-stl-clr.md)