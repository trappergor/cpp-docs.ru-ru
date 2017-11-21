---
title: "hash_multiset::upper_bound (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::upper_bound
dev_langs: C++
helpviewer_keywords: upper_bound member [STL/CLR]
ms.assetid: d5be0d79-ae60-42bb-8a53-051bc374407d
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b549538c1147f3d9574c018f7e15c4066dbbb245
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultisetupperbound-stlclr"></a>hash_multiset::upper_bound (STL/CLR)
Конец находит диапазон, соответствующий указанному ключу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 клавиша  
 Искомое значение ключа.  
  
## <a name="remarks"></a>Примечания  
 Функция-член определяет последний элемент `X` в управляемой последовательности, которая хэширует с одним контейнером, как `key` и соответствующим образом для `key`. Если такого элемента не существует или `X` является последним элементом в управляемой последовательности, она возвращает [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`; в противном случае он возвращает итератор, указывающий на первый элемент за пределами `X`. Используется для поиска конца последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_multiset_upper_bound.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = b  
*upper_bound(L'b') = c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::Count (STL/CLR)](../dotnet/hash-multiset-count-stl-clr.md)   
 [hash_multiset::equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)   
 [hash_multiset::Find (STL/CLR)](../dotnet/hash-multiset-find-stl-clr.md)   
 [hash_multiset::lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)