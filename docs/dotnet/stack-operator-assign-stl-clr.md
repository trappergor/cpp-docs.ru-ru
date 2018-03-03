---
title: "STACK::operator = (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::stack::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: 6f23b5fc-667e-4c6c-b43a-88b30da2ecac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 58a73316bf6928ca690fdc01b5211fc55d8cca7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="stackoperator-stlclr"></a>stack::operator= (STL/CLR)
Заменяет управляемую последовательность.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
stack <Value, Container>% operator=(stack <Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Адаптер контейнера для копирования.  
  
## <a name="remarks"></a>Примечания  
 Копирует оператор член `right` объекту, затем возвращает `*this`. Он позволяет заменить управляемую последовательность копией управляемой последовательности в `right`.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_stack_operator_as.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/stack >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)