---
title: "hash_map::size_type (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_map::size_type
dev_langs: C++
helpviewer_keywords: size_type member [STL/CLR]
ms.assetid: 062901e1-b52b-41e4-81be-b6646879e22a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8659a30ef17811c84984c2e61866e3a879ad3a6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="hashmapsizetype-stlclr"></a>hash_map::size_type (STL/CLR)
Тип расстояния со знаком между двумя элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef int size_type;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает элемент неотрицательное число.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_map_size_type.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Myhash_map::size_type diff = 0;   
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
end()-begin() = 3  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::empty (STL/CLR)](../dotnet/hash-map-empty-stl-clr.md)