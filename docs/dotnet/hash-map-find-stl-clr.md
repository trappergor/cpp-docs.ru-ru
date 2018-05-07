---
title: hash_map::Find (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::find
dev_langs:
- C++
helpviewer_keywords:
- find member [STL/CLR]
ms.assetid: 53ff8d57-2ea4-485e-9419-aed5e3f5affb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d6d06c35a4d64791f55a8c1428a6e0e38a111f3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="hashmapfind-stlclr"></a>hash_map::find (STL/CLR)
Определяет элемент, соответствующий указанному ключу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 клавиша  
 Искомое значение ключа.  
  
## <a name="remarks"></a>Примечания  
 Если имеется хотя бы один элемент управляемой последовательности, эквивалентное упорядочение с `key`, функция-член возвращает итератор, назначающий один из этих элементов; в противном случае возвращается [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md) `()`. Используется для поиска элемента в данный момент в управляемой последовательности, соответствующий указанному ключу.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_map_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Myhash_map::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
find A = False  
find b = [b 2]  
find C = False  
```  
  
## <a name="description"></a>Описание  
 Обратите внимание, что `find` не гарантирует того, какое из нескольких элемент, он находит.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::equal_range (STL/CLR)](../dotnet/hash-map-equal-range-stl-clr.md)   
 [hash_map::lower_bound (STL/CLR)](../dotnet/hash-map-lower-bound-stl-clr.md)   
 [hash_map::upper_bound (STL/CLR)](../dotnet/hash-map-upper-bound-stl-clr.md)