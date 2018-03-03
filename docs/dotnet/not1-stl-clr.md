---
title: "not1 (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::not1
dev_langs:
- C++
helpviewer_keywords:
- not1 function [STL/CLR]
ms.assetid: a50cd819-10de-4d81-84da-8a34c5414a43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c159c0667cf09d466a50487a0369a724a538676d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="not1-stlclr"></a>not1 (STL/CLR)
Приводит к возникновению ошибки `unary_negate` для функтором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Fun>  
    unary_negate<Fun> not1(Fun% functor);  
```  
  
## <a name="template-parameters"></a>Параметры шаблона  
 Fun  
 Тип функтора.  
  
## <a name="function-parameters"></a>Параметры функции  
 функтор  
 Функтор программы-оболочки.  
  
## <a name="remarks"></a>Примечания  
 Функция шаблона возвращает [unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)`<Fun>(functor)`. Используется в качестве удобный способ в функтор, который доставляет его логическое не вокруг функтор один аргумент.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_not1.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::logical_not<int> not_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::unary_negate<cliext::logical_not<int> >(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::not1(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 0  
1 0  
1 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)