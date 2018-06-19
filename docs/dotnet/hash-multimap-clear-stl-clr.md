---
title: hash_multimap::Clear (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 8ad99f08-93b3-42b7-be07-f9a8ec556554
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d0ff52608c63b23f72f2966bf7466c219405355b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109347"
---
# <a name="hashmultimapclear-stlclr"></a>hash_multimap::clear (STL/CLR)
Удаляет все элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член вызывает [hash_multimap::erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md) `(` [hash_multimap::begin (STL/CLR)](../dotnet/hash-multimap-begin-stl-clr.md) `(),` [hash_multimap::end (STL/CLR) ](../dotnet/hash-multimap-end-stl-clr.md)`())`. Используется, чтобы обеспечить пустой управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_multimap_clear.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
  
// display contents " [a 1] [b 2]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2]  
size() = 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md)