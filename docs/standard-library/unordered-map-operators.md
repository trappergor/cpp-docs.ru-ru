---
title: Операторы &lt;unordered_map&gt;
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: 2c09fa0070151f7cdd502e8f5583645110e91c5b
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741961"
---
# <a name="ltunordered_mapgt-operators"></a>Операторы &lt;unordered_map&gt;

[unordered_map:: operator! =](#op_neq)\
[unordered_map:: operator = =](#op_eq_eq)\
[unordered_multimap:: operator! =](#op_neq_multimap)\
[unordered_multimap:: operator = =](#op_eq_eq_multimap)

## <a name="operator"></a><a name="op_neq"></a> operator! =

Проверяет, не равен ли объект [unordered_map](../standard-library/unordered-map-class.md) в левой части объекту unordered_map в правой части.

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*слева*\
Объект типа `unordered_map`.

*Правильно*\
Объект типа `unordered_map`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если unordered_maps не равны; значение **`false`** , если они равны.

### <a name="remarks"></a>Remarks

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

/* Output:
um1 != um2: true
um1 != um3: false
um2 != um3: true
*/
```

## <a name="operator"></a><a name="op_eq_eq"></a> Оператор = =

Проверяет, равен ли объект [unordered_map](../standard-library/unordered-map-class.md) в левой части объекту unordered_map в правой части.

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*слева*\
Объект типа `unordered_map`.

*Правильно*\
Объект типа `unordered_map`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если unordered_maps равны; **`false`** если они не равны.

### <a name="remarks"></a>Remarks

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

/* Output:
um1 == um2: false
um1 == um3: true
um2 == um3: false
*/
```

## <a name="operator-multimap"></a><a name="op_neq_multimap"></a> operator! = (multimap)

Проверяет, не равен ли объект [unordered_multimap](../standard-library/unordered-multimap-class.md) в левой части объекту unordered_multimap в правой части.

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*слева*\
Объект типа `unordered_multimap`.

*Правильно*\
Объект типа `unordered_multimap`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если unordered_multimaps не равны; значение **`false`** , если они равны.

### <a name="remarks"></a>Remarks

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

/* Output:
um1 != um2: true
um1 != um3: false
um2 != um3: true
*/
```

## <a name="operator-multimap"></a><a name="op_eq_eq_multimap"></a> оператор = = (multimap)

Проверяет, равен ли объект [unordered_multimap](../standard-library/unordered-multimap-class.md) в левой части объекту unordered_multimap в правой части.

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*слева*\
Объект типа `unordered_multimap`.

*Правильно*\
Объект типа `unordered_multimap`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если unordered_multimaps равны; **`false`** если они не равны.

### <a name="remarks"></a>Remarks

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

/* Output:
um1 == um2: false
um1 == um3: true
um2 == um3: false
*/
```

## <a name="see-also"></a>См. также

[<unordered_map>](../standard-library/unordered-map.md)
