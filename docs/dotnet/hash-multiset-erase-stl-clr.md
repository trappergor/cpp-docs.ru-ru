---
title: "hash_multiset::Erase (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::erase
dev_langs: C++
helpviewer_keywords: erase member [STL/CLR]
ms.assetid: bddd329d-aece-4b93-8355-005351c3aa45
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9e2e35eeecab632371922705cc95848e84a46d1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultiseterase-stlclr"></a>hash_multiset::erase (STL/CLR)
Удаляет элементы в указанных позициях.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Начало диапазона для удаления.  
  
 клавиша  
 Значение ключа для удаления.  
  
 last  
 Конец диапазона для удаления.  
  
 где  
 Подлежащий удалению элемент.  
  
## <a name="remarks"></a>Примечания  
 Первая функция-член удаляет элемент управляемой последовательности, на который указывает `where`и возвращает итератор, указывающий на первый элемент, оставшийся после удаления элемента или [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md) `()` Если такого элемента не существует. Используется для удаления одного элемента.  
  
 Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`) и возвращает итератор, указывающий на первый элемент, находящийся за всеми удаленными элементами, или `end()` Если ни одного такого элемента существует... Используется для удаления ноль или более последовательных элементов.  
  
 Третья функция-член удаляет любой элемент управляемой последовательности, ключ которого имеет соответствующий порядок для `key`и возвращает число удаленных элементов. Используется для удаления и количество всех элементов, соответствующих заданному ключу.  
  
 Каждый элемент стирания время пропорционально логарифму числа элементов в управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_multiset_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Myhash_multiset::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::clear (STL/CLR)](../dotnet/hash-multiset-clear-stl-clr.md)