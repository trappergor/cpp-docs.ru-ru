---
title: Операторы &lt;map&gt;
ms.date: 03/27/2019
f1_keywords:
- map/std::operator!=
- map/std::operator&gt;
- map/std::operator&gt;=
- map/std::operator&lt;
- map/std::operator&lt;=
- map/std::operator==
ms.assetid: 7df02b9f-701c-44ed-834a-a819badc5bd0
helpviewer_keywords:
- std::operator!= (map)
- std::operator&gt; (map)
- std::operator&gt;= (map)
- std::operator&lt; (map)
- std::operator&lt;= (map)
- std::operator== (map)
ms.openlocfilehash: deb442d0ba1fbd180fdb41b66de73df92bee7fc9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425523"
---
# <a name="ltmapgt-operators"></a>Операторы &lt;map&gt;

## <a name="op_neq"></a>  operator!=

Проверяет неравенство объекта map слева от оператора объекту map справа от оператора.

```cpp
bool operator!=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `map`.

*справа*\
Объект типа `map`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объекты map равны; **false**, если объекты map не равны.

### <a name="remarks"></a>Remarks

Сравнение между объектами map основывается на попарном сравнении их элементов. Два объекта map равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// map_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The maps m1 and m2 are not equal." << endl;
   else
      cout << "The maps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The maps m1 and m3 are not equal." << endl;
   else
      cout << "The maps m1 and m3 are equal." << endl;
}
```

```Output
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
```

## <a name="op_lt">Оператор </a>&lt;

Проверяет, меньше ли объект map слева от оператора, чем объект map справа от оператора.

```cpp
bool operator<(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `map`.

*справа*\
Объект типа `map`.

### <a name="return-value"></a>Возвращаемое значение

**true** если объект map слева от оператора строго меньше объекта map справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами map основывается на попарном сравнении их элементов. Отношение «меньше» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// map_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The map m1 is less than the map m2." << endl;
   else
      cout << "The map m1 is not less than the map m2." << endl;

   if ( m1 < m3 )
      cout << "The map m1 is less than the map m3." << endl;
   else
      cout << "The map m1 is not less than the map m3." << endl;
}
```

```Output
The map m1 is less than the map m2.
The map m1 is not less than the map m3.
```

## <a name="op_lt_eq"></a>&lt;оператора =

Проверяет, что объект map слева от оператора меньше или равен объекту map справа от оператора.

```cpp
bool operator<=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `map`.

*справа*\
Объект типа `map`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект map слева от оператора меньше или равен объекту map справа от оператора; в противном случае **false**.

### <a name="example"></a>Пример

```cpp
// map_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "The map m1 is less than or equal to the map m2." << endl;
   else
      cout << "The map m1 is greater than the map m2." << endl;

   if ( m1 <= m3 )
      cout << "The map m1 is less than or equal to the map m3." << endl;
   else
      cout << "The map m1 is greater than the map m3." << endl;

   if ( m1 <= m4 )
      cout << "The map m1 is less than or equal to the map m4." << endl;
   else
      cout << "The map m1 is greater than the map m4." << endl;
}
```

```Output
The map m1 is less than or equal to the map m2.
The map m1 is greater than the map m3.
The map m1 is less than or equal to the map m4.
```

## <a name="op_eq_eq"></a>Оператор = =

Проверяет равенство объекта map слева от оператора объекту map справа от оператора.

```cpp
bool operator==(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `map`.

*справа*\
Объект типа `map`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект map слева от оператора равен объекту map справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами map основывается на попарном сравнении их элементов. Два объекта map равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// map_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 == m2 )
      cout << "The maps m1 and m2 are equal." << endl;
   else
      cout << "The maps m1 and m2 are not equal." << endl;

   if ( m1 == m3 )
      cout << "The maps m1 and m3 are equal." << endl;
   else
      cout << "The maps m1 and m3 are not equal." << endl;
}
```

```Output
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
```

## <a name="op_gt">Оператор </a>&gt;

Проверяет, что объект map слева от оператора больше объекта map справа от оператора.

```cpp
bool operator>(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `map`.

*справа*\
Объект типа `map`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект map слева от оператора больше объекта map справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами map основывается на попарном сравнении их элементов. Отношение «больше» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// map_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The map m1 is greater than the map m2." << endl;
   else
      cout << "The map m1 is not greater than the map m2." << endl;

   if ( m1 > m3 )
      cout << "The map m1 is greater than the map m3." << endl;
   else
      cout << "The map m1 is not greater than the map m3." << endl;
}
/* Output:
The map m1 is not greater than the map m2.
The map m1 is greater than the map m3.
*/
```

## <a name="op_gt_eq"></a>  operator&gt;=

Проверяет, что объект map слева от оператора больше или равен объекту map справа от оператора.

```cpp
bool operator>=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `map`.

*справа*\
Объект типа `map`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект map слева от оператора больше объекта map справа от оператора или равен ему; в противном случае **false**.

### <a name="example"></a>Пример

```cpp
// map_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "Map m1 is greater than or equal to map m2." << endl;
   else
      cout << "The map m1 is less than the map m2." << endl;

   if ( m1 >= m3 )
      cout << "Map m1 is greater than or equal to map m3." << endl;
   else
      cout << "The map m1 is less than the map m3." << endl;

   if ( m1 >= m4 )
      cout << "Map m1 is greater than or equal to map m4." << endl;
   else
      cout << "The map m1 is less than the map m4." << endl;
}
```

```Output
The map m1 is less than the map m2.
Map m1 is greater than or equal to map m3.
Map m1 is greater than or equal to map m4.
```

## <a name="op_neq_multimap"></a>operator! = (multimap)

Проверяет неравенство объекта multimap слева от оператора объекту multimap справа от оператора.

```cpp
bool operator!=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `multimap`.

*справа*\
Объект типа `multimap`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объекты multimap равны; **false**, если они не равны.

### <a name="remarks"></a>Remarks

Сравнение между объектами multimap основывается на попарном сравнении их элементов. Два объекта multimap равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// multimap_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The multimaps m1 and m2 are not equal." << endl;
   else
      cout << "The multimaps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The multimaps m1 and m3 are not equal." << endl;
   else
      cout << "The multimaps m1 and m3 are equal." << endl;
}
```

```Output
The multimaps m1 and m2 are not equal.
The multimaps m1 and m3 are equal.
```

## <a name="op_lt_multimap">Оператор </a>&lt;

Проверяет, меньше ли объект multimap слева от оператора объекта multimap справа от оператора.

```cpp
bool operator<(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `multimap`.

*справа*\
Объект типа `multimap`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект multimap слева от оператора строго меньше объекта multimap справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами multimap основывается на попарном сравнении их элементов. Отношение «меньше» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// multimap_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The multimap m1 is less than the multimap m2." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m2." << endl;

   if ( m1 < m3 )
      cout << "The multimap m1 is less than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m3." << endl;
}
```

```Output
The multimap m1 is less than the multimap m2.
The multimap m1 is not less than the multimap m3.
```

## <a name="op_lt_eq_multimap"></a>  operator&lt;=

Проверяет, что объект multimap слева от оператора меньше объекта multimap справа от оператора или равен ему.

```cpp
bool operator<=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `multimap`.

*справа*\
Объект типа `multimap`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект multimap слева от оператора меньше объекта multimap справа от оператора или равен ему; в противном случае **false**.

### <a name="example"></a>Пример

```cpp
// multimap_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "m1 is less than or equal to m2" << endl;
   else
      cout << "m1 is greater than m2" << endl;

   if ( m1 <= m3 )
      cout << "m1 is less than or equal to m3" << endl;
   else
      cout << "m1 is greater than m3" << endl;

   if ( m1 <= m4 )
      cout << "m1 is less than or equal to m4" << endl;
   else
      cout << "m1 is greater than m4" << endl;
}
```

```Output
m1 is less than or equal to m2
m1 is greater than m3
m1 is less than or equal to m4
```

## <a name="op_eq_eq_multimap"></a>Оператор = =

Проверяет равенство объекта multimap слева от оператора объекту multimap справа от оператора.

```cpp
bool operator==(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `multimap`.

*справа*\
Объект типа `multimap`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект multimap слева от оператора равен объекту multimap справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами multimap основывается на попарном сравнении их элементов. Два объекта multimap равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// multimap_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      m1.insert(Int_Pair(i, i));
      m2.insert(Int_Pair(i, i*i));
      m3.insert(Int_Pair(i, i));
   }

   if ( m1 == m2 )
      cout << "m1 and m2 are equal" << endl;
   else
      cout << "m1 and m2 are not equal" << endl;

   if ( m1 == m3 )
      cout << "m1 and m3 are equal" << endl;
   else
      cout << "m1 and m3 are not equal" << endl;
}
```

```Output
m1 and m2 are not equal
m1 and m3 are equal
```

## <a name="op_gt_multimap">Оператор </a>&gt;

Проверяет, что объект multimap слева от оператора больше объекта multimap справа от оператора.

```cpp
bool operator>(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `multimap`.

*справа*\
Объект типа `multimap`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект multimap слева от оператора больше объекта multimap справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами multimap основывается на попарном сравнении их элементов. Отношение «больше» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// multimap_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The multimap m1 is greater than the multimap m2." << endl;
   else
      cout << "Multimap m1 is not greater than multimap m2." << endl;

   if ( m1 > m3 )
      cout << "The multimap m1 is greater than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not greater than the multimap m3." << endl;
}
```

```Output
Multimap m1 is not greater than multimap m2.
The multimap m1 is greater than the multimap m3.
```

## <a name="op_gt_eq_multimap"></a>&gt;оператора =

Проверяет, что объект multimap слева от оператора больше объекта multimap справа от оператора или равен ему.

```cpp
bool operator>=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `multimap`.

*справа*\
Объект типа `multimap`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект multimap слева от оператора больше объекта multimap справа от оператора или равен ему; в противном случае **false**.

### <a name="example"></a>Пример

```cpp
// multimap_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "The multimap m1 is greater than or equal to the multimap m2." << endl;
   else
      cout << "The multimap m1 is less than the multimap m2." << endl;

   if ( m1 >= m3 )
      cout << "The multimap m1 is greater than or equal to the multimap m3." << endl;
   else
      cout << "The multimap m1 is less than the multimap m3." << endl;

   if ( m1 >= m4 )
      cout << "The multimap m1 is greater than or equal to the multimap m4." << endl;
   else
      cout << "The multimap m1 is less than the multimap m4." << endl;
}
```

```Output
The multimap m1 is less than the multimap m2.
The multimap m1 is greater than or equal to the multimap m3.
The multimap m1 is greater than or equal to the multimap m4.
```
