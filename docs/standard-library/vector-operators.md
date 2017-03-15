---
title: "Операторы &lt;vector&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 14308c0789851af423fd687f88acfe9177d89aff
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-operators"></a>Операторы &lt;vector&gt;
||||  
|-|-|-|  
|[оператор!=](#operator_neq)|[оператор&gt;](#operator_gt_)|[оператор&gt;=](#operator_gt__eq)|  
|[оператор&lt;](#operator_lt_)|[оператор&lt;=](#operator_lt__eq)|[оператор==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  оператор!=  
 Проверяет неравенство объекта слева от оператора объекту справа от оператора.  
  
```  
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` left`  
 Объект типа **vector**.  
  
 ` right`  
 Объект типа **vector**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объекты vector не равны; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Два объекта vector равны, если они содержат одинаковое количество элементов и соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_op_ne.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
     v2.push_back( 2 );  
  
   if ( v1 != v2 )  
      cout << "Vectors not equal." << endl;  
   else  
      cout << "Vectors equal." << endl;  
}  
```  
  
```Output  
Vectors not equal.  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  оператор&lt;  
 Проверяет, что объект слева от оператора меньше, чем объект справа от оператора.  
  
```  
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` left`  
 Объект типа **vector**.  
  
 ` right`  
 Объект типа **vector**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект vector слева от оператора строго меньше объекта vector справа от оператора; в противном случае **false**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_op_lt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 < v2 )  
      cout << "Vector v1 is less than vector v2." << endl;  
   else  
      cout << "Vector v1 is not less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than vector v2.  
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  оператор&lt;=  
 Проверяет, что объект слева от оператора меньше или равен объекту справа от оператора.  
  
```  
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` left`  
 Объект типа **vector**.  
  
 ` right`  
 Объект типа **vector**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект vector слева от оператора меньше или равен объекту vector справа от оператора; в противном случае **false**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_op_le.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 <= v2 )  
      cout << "Vector v1 is less than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than or equal to vector v2.  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  оператор==  
 Проверяет равенство объекта слева от оператора объекту справа от оператора.  
  
```  
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` left`  
 Объект типа **vector**.  
  
 ` right`  
 Объект типа **vector**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект vector слева от оператора равен объекту vector справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Два объекта vector равны, если они содержат одинаковое количество элементов и соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_op_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v2.push_back( 1 );  
  
   if ( v1 == v2 )  
      cout << "Vectors equal." << endl;  
   else  
      cout << "Vectors not equal." << endl;  
}  
```  
  
```Output  
Vectors equal.  
```  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  оператор&gt;  
 Проверяет, что объект слева от оператора больше, чем объект справа от оператора.  
  
```  
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` left`  
 Объект типа **vector**.  
  
 ` right`  
 Объект типа **vector**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект vector слева от оператора больше объекта vector справа от оператора; в противном случае **false**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_op_gt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
   v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 > v2 )  
      cout << "Vector v1 is greater than vector v2." << endl;  
   else  
      cout << "Vector v1 is not greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than vector v2.  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  оператор&gt;=  
 Проверяет, что объект слева от оператора больше или равен объекту справа от оператора.  
  
```  
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` left`  
 Объект типа **vector**.  
  
 ` right`  
 Объект типа **vector**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект vector слева от оператора больше или равен объекту vector справа от оператора; в противном случае **false**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_op_ge.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
     v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 >= v2 )  
      cout << "Vector v1 is greater than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than or equal to vector v2.  
```  
  
## <a name="see-also"></a>См. также  
 [\<vector>](../standard-library/vector.md)


