---
title: "hash_map::hash_delegate (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_map::hash_delegate
dev_langs: C++
helpviewer_keywords: hash_delegate member [STL/CLR]
ms.assetid: ae451fbe-a10c-457f-9b54-94dd9d93e8c4
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1c25f7124425e13d0bba466187cf0062cf516608
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hashmaphashdelegate-stlclr"></a>hash_map::hash_delegate (STL/CLR)
Определяет элемент, соответствующий указанному ключу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
hasher^ hash_delegate();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает делегат, используемый для преобразования значения ключа в целое число. Используется для хэширования ключа.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_map_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    Myhash_map::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 1616896120  
hash(L'b') = 570892832  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::hasher (STL/CLR)](../dotnet/hash-map-hasher-stl-clr.md)