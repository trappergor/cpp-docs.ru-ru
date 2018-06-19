---
title: set::iterator (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator member [STL/CLR]
ms.assetid: 7e54276b-4cb3-4bff-a3a6-23ae328aa369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 28340c07ce60f509cd52b776d8d8eac3367d7a87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33162387"
---
# <a name="setiterator-stlclr"></a>set::iterator (STL/CLR)
Тип итератора для управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T1` , можно использовать в качестве двунаправленного итератора для управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_set_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Myset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [набор (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::const_iterator (STL/CLR)](../dotnet/set-const-iterator-stl-clr.md)