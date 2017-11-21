---
title: "Операторы &lt;list&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- list/std::operator!=
- list/std::operator&gt;
- list/std::operator&gt;=
- list/std::operator&lt;
- list/std::operator&lt;=
- list/std::operator==
dev_langs: C++
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
caps.latest.revision: "7"
manager: ghogen
helpviewer_keywords:
- std::operator!= (list)
- std::operator&gt; (list)
- std::operator&gt;= (list)
- std::operator&lt; (list)
- std::operator&lt;= (list)
- std::operator== (list)
ms.openlocfilehash: f3834fcb728d8faf0a2148a5a0c9449fef7e41c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltlistgt-operators"></a>Операторы &lt;list&gt;
||||  
|-|-|-|  
|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|[оператор&gt;=](#op_gt_eq)|  
|[оператор&lt;](#op_lt)|[оператор&lt;=](#op_lt_eq)|[оператор==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  оператор!=  
 Проверяет неравенство объекта-списка слева от оператора объекту-списку справа от оператора.  
  
```
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **list**.  
  
 `right`  
 Объект типа **list**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если списки не равны; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Два списка равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// list_op_ne.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
list <int> c1, c2;  
c1.push_back( 1 );  
c2.push_back( 2 );  
  
if ( c1 != c2 )  
cout << "Lists not equal." << endl;  
else  
cout << "Lists equal." << endl;  
}  
\* Output:  
Lists not equal.  
*\  
```  
  
##  <a name="op_lt"></a>  оператор&lt;  
 Проверяет, меньше ли объект-список слева от оператора, чем объект-список справа от оператора.  
  
```
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **list**.  
  
 `right`  
 Объект типа **list**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если список слева от оператора меньше, чем список справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «меньше» между двумя объектами основывается на сравнении первой пары неравных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// list_op_lt.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 < c2 )  
      cout << "List c1 is less than list c2." << endl;  
   else  
      cout << "List c1 is not less than list c2." << endl;  
}  
\* Output:   
List c1 is less than list c2.  
*\   
```  
  
##  <a name="op_lt_eq"></a>  оператор&lt;=  
 Проверяет, что объект-список слева от оператора меньше или равен объекту-списку справа от оператора.  
  
```
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **list**.  
  
 `right`  
 Объект типа **list**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если список в левой части оператора меньше или равен списку в правой части оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «меньше или равно» между двумя объектами основывается на сравнении первой пары неравных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// list_op_le.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 <= c2 )  
      cout << "List c1 is less than or equal to list c2." << endl;  
   else  
      cout << "List c1 is greater than list c2." << endl;  
}  
\* Output:   
List c1 is less than or equal to list c2.  
*\  
```  
  
##  <a name="op_eq_eq"></a>  оператор==  
 Проверяет, равен ли объект-список слева от оператора объекту-списку справа от оператора.  
  
```
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **list**.  
  
 `right`  
 Объект типа **list**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если список слева от оператора равен списку справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Два списка равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// list_op_eq.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
int main( )   
{  
   using namespace std;   
  
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c2.push_back( 1 );  
  
   if ( c1 == c2 )  
      cout << "The lists are equal." << endl;  
   else  
      cout << "The lists are not equal." << endl;  
}  
\* Output:   
The lists are equal.  
*\  
```  
  
##  <a name="op_gt"></a>  оператор&gt;  
 Проверяет, больше ли объект-список слева от оператора, чем объект-список справа от оператора.  
  
```
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **list**.  
  
 `right`  
 Объект типа **list**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если список слева от оператора больше списка справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «больше» между двумя объектами основывается на сравнении первой пары неравных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// list_op_gt.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 > c2 )  
      cout << "List c1 is greater than list c2." << endl;  
   else  
      cout << "List c1 is not greater than list c2." << endl;  
}  
\* Output:   
List c1 is greater than list c2.  
*\  
```  
  
##  <a name="op_gt_eq"></a>  оператор&gt;=  
 Проверяет, что объект-список слева от оператора больше или равен объекту-списку справа от оператора.  
  
```
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа **list**.  
  
 `right`  
 Объект типа **list**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если список слева от оператора больше или равен списку справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «больше или равно» между двумя объектами основывается на сравнении первой пары неравных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// list_op_ge.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 >= c2 )  
      cout << "List c1 is greater than or equal to list c2." << endl;  
   else  
      cout << "List c1 is less than list c2." << endl;  
}  
\* Output:   
List c1 is greater than or equal to list c2.  
*\  
```  
  
## <a name="see-also"></a>См. также  
 [\<list>](../standard-library/list.md)



