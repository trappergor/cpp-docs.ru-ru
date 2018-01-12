---
title: "List::sort (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::sort
dev_langs: C++
helpviewer_keywords: sort member [STL/CLR]
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 159391bc7d362c755c194f478692b2a271d779ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listsort-stlclr"></a>list::sort (STL/CLR)
Упорядочивает управляемую последовательность.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Параметры  
 Pred  
 Компаратор для пар элементов.  
  
## <a name="remarks"></a>Примечания  
 Первая функция-член меняет порядок элементов в управляемой последовательности, так что они упорядочиваются по `operator<` --элементов не уменьшаются при прохождении через последовательность. Использовать эту функцию-член для сортировки последовательности в порядке возрастания.  
  
 Вторая функция-член работает так же, как первая, но последовательность, упорядоченную по `pred`  --  `pred(X, Y)` имеет значение false для любого элемента `X` , который следует за элемент `Y` в результирующей последовательности. Используется для сортировки последовательности в порядке их указания функции предиката или делегата.  
  
 Как функции выполнения стабильной сортировки — обращено не пары элементов в исходной последовательности, управляемой в результирующей управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_sort.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)   
 [List::reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)   
 [List::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)   
 [list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)