---
title: "Операторы &lt;unordered_map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: c78d1dda2a61a85bde238167b75eace09af598b6
ms.lasthandoff: 02/24/2017

---
# <a name="ltunorderedmapgt-operators"></a>Операторы &lt;unordered_map&gt;
|||||  
|-|-|-|-|  
|[оператор!=](#operator_neq)|[оператор==](#operator_eq_eq)|[оператор!=](#operator_neq_multimap)|[оператор==](#operator_eq_eq_multimap)|  
  
##  <a name="operator_neq"></a>  оператор!=  
 Проверяет, не равен ли объект [unordered_map](../standard-library/unordered-map-class.md) в левой части объекту unordered_map в правой части.  
  
```
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_map`.  
  
 `right`  
 Объект типа `unordered_map`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_map не равны; `false`, если они равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_map. Два объекта unordered_map равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_map_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Выходные данные:**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="operator_eq_eq"></a>  оператор==  
 Проверяет, равен ли объект [unordered_map](../standard-library/unordered-map-class.md) в левой части объекту unordered_map в правой части.  
  
```
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_map`.  
  
 `right`  
 Объект типа `unordered_map`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_map равны; `false`, если они не равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_map. Два объекта unordered_map равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_map_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Выходные данные:**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
##  <a name="operator_neq_multimap"></a>  оператор!=  
 Проверяет, не равен ли объект [unordered_multimap](../standard-library/unordered-multimap-class.md) в левой части объекту unordered_multimap в правой части.  
  
```
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_multimap`.  
  
 `right`  
 Объект типа `unordered_multimap`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_multimap не равны; `false`, если они равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_multimap. Два объекта unordered_multimap равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_multimap_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Выходные данные:**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="operator_eq_eq_multimap"></a>  оператор==  
 Проверяет, равен ли объект [unordered_multimap](../standard-library/unordered-multimap-class.md) в левой части объекту unordered_multimap в правой части.  
  
```
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `unordered_multimap`.  
  
 `right`  
 Объект типа `unordered_multimap`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если объекты unordered_multimap равны; `false`, если они не равны.  
  
### <a name="remarks"></a>Примечания  
 Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_multimap. Два объекта unordered_multimap равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// unordered_multimap_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd  
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Выходные данные:**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
## <a name="see-also"></a>См. также  
 [<unordered_map>](../standard-library/unordered-map.md)




