---
title: "Операторы &lt;unordered_set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
caps.latest.revision: 7
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 5fbd22c2f21eaa36e75afd051ab3fbaa5858e5a2
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltunorderedsetgt-operators"></a>Операторы &lt;unordered_set&gt;
|||||  
|-|-|-|-|  
|[оператор!=](#op_neq)|[оператор==](#op_eq_eq)|[оператор!=](#op_neq_unordered_multiset)|[оператор==](#op_eq_eq_unordered_multiset)|  
  
##  <a name="op_neq"></a>  оператор!=  
 Проверяет, не равен ли объект [unordered_set](../standard-library/unordered-set-class.md) в левой части объекту unordered_set в правой части.  
  
```
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_set`.  
  
 `right`  
 Объект типа `unordered_set`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_set не равны; `false`, если они равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_set. Два объекта unordered_set равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_set_ne.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_set<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 != c2: " << (c1 != c2) << endl;   
   cout << "c1 != c3: " << (c1 != c3) << endl;   
   cout << "c2 != c3: " << (c2 != c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Выходные данные:**  
  
 `c1 != c2: true`  
  
 `c1 != c3: false`  
  
 `c2 != c3: true`  
  
##  <a name="op_eq_eq"></a>  оператор==  
 Проверяет, равен ли объект [unordered_set](../standard-library/unordered-set-class.md) в левой части объекту unordered_set в правой части.  
  
```
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_set`.  
  
 `right`  
 Объект типа `unordered_set`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_set равны; `false`, если они не равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_set. Два объекта unordered_set равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_set_eq.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_set<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 == c2: " << (c1 == c2) << endl;   
   cout << "c1 == c3: " << (c1 == c3) << endl;   
   cout << "c2 == c3: " << (c2 == c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Выходные данные:**  
  
 `c1 == c2: false`  
  
 `c1 == c3: true`  
  
 `c2 == c3: false`  
  
##  <a name="op_neq_unordered_multiset"></a>  оператор!=  
 Проверяет, не равен ли объект [unordered_multiset](../standard-library/unordered-multiset-class.md) в левой части объекту unordered_multiset в правой части.  
  
```
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_multiset`.  
  
 `right`  
 Объект типа `unordered_multiset`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_multiset не равны; `false`, если они равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_multiset. Два объекта unordered_multiset равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_multiset_ne.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_multiset<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 != c2: " << (c1 != c2) << endl;   
   cout << "c1 != c3: " << (c1 != c3) << endl;   
   cout << "c2 != c3: " << (c2 != c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Выходные данные:**  
  
 `c1 != c2: true`  
  
 `c1 != c3: false`  
  
 `c2 != c3: true`  
  
##  <a name="op_eq_eq_unordered_multiset"></a>  оператор==  
 Проверяет, равен ли объект [unordered_multiset](../standard-library/unordered-multiset-class.md) в левой части объекту unordered_multiset в правой части.  
  
```
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_multiset`.  
  
 `right`  
 Объект типа `unordered_multiset`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_multiset равны; `false`, если они не равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_multiset. Два объекта unordered_multiset равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_multiset_eq.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_multiset<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 == c2: " << (c1 == c2) << endl;   
   cout << "c1 == c3: " << (c1 == c3) << endl;   
   cout << "c2 == c3: " << (c2 == c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Выходные данные:**  
  
 `c1 == c2: false`  
  
 `c1 == c3: true`  
  
 `c2 == c3: false`  
  
## <a name="see-also"></a>См. также  
 [<unordered_set>](../standard-library/unordered-set.md)




