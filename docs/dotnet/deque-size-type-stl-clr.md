---
title: deque::size_type (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::size_type
dev_langs:
- C++
helpviewer_keywords:
- size_type member [STL/CLR]
ms.assetid: c598871c-0ce8-4599-ab4c-2d0ea5f3f8e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 13e25b08ac120680ff3022ef685f75df718af55c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106366"
---
# <a name="dequesizetype-stlclr"></a>deque::size_type (STL/CLR)
Тип расстояния со знаком между двумя элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef int size_type;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает элемент неотрицательное число.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_deque_size_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::deque<wchar_t>::size_type diff = c1.end() - c1.begin();   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/deque >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::empty (STL/CLR)](../dotnet/deque-empty-stl-clr.md)