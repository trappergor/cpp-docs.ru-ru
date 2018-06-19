---
title: not2 (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::not2
dev_langs:
- C++
helpviewer_keywords:
- not2 function [STL/CLR]
ms.assetid: f8aedcca-e4d1-4430-93b4-83dd55579d04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf496bd4b16ad78fa9a85eb6e9b9b9935ef380cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133393"
---
# <a name="not2-stlclr"></a>not2 (STL/CLR)
Приводит к возникновению ошибки `binary_negate` для функтором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Fun>  
    binary_negate<Fun> not2(Fun% functor);  
```  
  
## <a name="template-parameters"></a>Параметры шаблона  
 Fun  
 Тип функтора.  
  
## <a name="function-parameters"></a>Параметры функции  
 функтор  
 Функтор программы-оболочки.  
  
## <a name="remarks"></a>Примечания  
 Функция шаблона возвращает [binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)`<Fun>(functor)`. Используется в качестве удобный способ в функтор, который доставляет его логическое не вокруг функтор двумя аргументами.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_not2.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
1 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)