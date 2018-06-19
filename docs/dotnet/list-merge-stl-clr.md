---
title: List::Merge (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::merge
dev_langs:
- C++
helpviewer_keywords:
- merge member [STL/CLR]
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ff5ba18dea3b33d1cf3a50dedfc5e90055e69c3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133406"
---
# <a name="listmerge-stlclr"></a>list::merge (STL/CLR)
Объединяет две упорядоченные управляемые последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### <a name="parameters"></a>Параметры  
 Pred  
 Компаратор для пар элементов.  
  
 right  
 Контейнер для слияния в.  
  
## <a name="remarks"></a>Примечания  
 Первая функция-член удаляет все элементы из последовательности, контролируемой `right` и вставлять их в управляемой последовательности. Обе последовательности должны быть ранее упорядочены по `operator<` --элементы не должны уменьшаться в значении при прохождении через любой последовательности. Результирующая последовательность также упорядочивается по `operator<`. Используйте эту функцию-член для объединения двух последовательностей, увеличение значения в последовательность, в которой также возрастает значение.  
  
 Вторая функция-член работает так же, как первая, за исключением последовательности в порядке `pred`  --  `pred(X, Y)` должен иметь значение false для любого элемента `X` , который следует за элемент `Y` в последовательности. Используется для объединения двух последовательностей, упорядоченных по функции предиката или делегат, который можно указать.  
  
 Как функции выполняют стабильный слияния — ни в одной паре элементов из исходного управляемой последовательности изменяется в результирующей управляемой последовательности. Кроме того Если пара элементов `X` и `Y` в результирующей последовательности управляемой имеет соответствующий порядок-- `!(X < Y) && !(X < Y)` --отображения элементов из исходного управляемой последовательности перед элементом из последовательности, контролируемой `right`.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a c e  
 b d f  
 a b c d e f  
c2.size() = 0  
 e c a  
 f e d c b a  
 f e e d c c b a a  
c1.size() = 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)   
 [list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)