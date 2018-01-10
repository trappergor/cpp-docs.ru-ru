---
title: "MAP::Insert (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::map::insert
dev_langs: C++
helpviewer_keywords: insert member [STL/CLR]
ms.assetid: 599c702e-7db0-45b8-8247-4ff041a3639c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 495a3e80e28ea70f1784f12ee9750050847e6e2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mapinsert-stlclr"></a>map::insert (STL/CLR)
Добавляет элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Начало диапазона для вставки.  
  
 last  
 Конец диапазона для вставки.  
  
 right  
 Перечисление для вставки.  
  
 функция Val  
 Значение ключа для вставки.  
  
 где  
 Место в контейнере для вставки (указание).  
  
## <a name="remarks"></a>Примечания  
 Каждая из функций-членов вставляет последовательности, указанной оставшимися операндами.  
  
 Первая функция-член написана для вставки элементов со значением `val`и возвращает пару значений `X`. Если `X.second` имеет значение true, `X.first` обозначает вставленный элемент; в противном случае `X.first` выделяет элемент, эквивалентный упорядочение, уже существует и вставляется новый элемент. Используется для вставки одного элемента.  
  
 Вторая функция-член вставляет элемент со значением `val`, с использованием `where` как подсказка (для повышения производительности) и возвращает итератор, указывающий на вставленный элемент. Используется для вставки один элемент, который может быть смежными элементу известно.  
  
 Третья функция-член вставляет последовательность [`first`, `last`). Используется для вставки ноль или более элементов, копируемых из другой последовательности.  
  
 Четвертая функция-член вставляет последовательность, назначенному с помощью `right`. Используется для вставки последовательности, описываемого перечислителя.  
  
 Каждый элемент вставки время пропорционально логарифму числа элементов в управляемой последовательности. Вставка может быть выполнена в константном времени амортизацию, тем не менее, учитывая подсказку, которая выделяет элемент курсор рядом.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_map_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef Mymap::pair_iter_bool Pairib;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
// insert a single value, success and failure   
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Mymap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Mymap::iterator it =   
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymap::value_type>^)%c1);   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
insert([L'x' 24]) = [[x 24] True]  
insert([L'b' 2]) = [[b 2] False]  
 [a 1] [b 2] [c 3] [x 24]  
insert(begin(), [L'y' 25]) = [y 25]  
 [a 1] [b 2] [c 3] [x 24] [y 25]  
 [a 1] [b 2] [c 3] [x 24]  
 [a 1] [b 2] [c 3] [x 24] [y 25]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)