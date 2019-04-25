---
title: Операторы &lt;unordered_map&gt;
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: a27ef8e320f59464f15603c330346db86bc30aac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158451"
---
# <a name="ltunorderedmapgt-operators"></a>Операторы &lt;unordered_map&gt;

|||||
|-|-|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_multimap)|[operator==](#op_eq_eq_multimap)|

## <a name="op_neq"></a> operator!=

Проверяет, не равен ли объект [unordered_map](../standard-library/unordered-map-class.md) в левой части объекту unordered_map в правой части.

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `unordered_map`.

*right*<br/>
Объект типа `unordered_map`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты unordered_map не равны; **false** если они равны.

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

## <a name="op_eq_eq"></a> operator==

Проверяет, равен ли объект [unordered_map](../standard-library/unordered-map-class.md) в левой части объекту unordered_map в правой части.

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `unordered_map`.

*right*<br/>
Объект типа `unordered_map`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты unordered_map равны; **false** если они не равны.

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

## <a name="op_neq_multimap"></a> operator!=

Проверяет, не равен ли объект [unordered_multimap](../standard-library/unordered-multimap-class.md) в левой части объекту unordered_multimap в правой части.

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `unordered_multimap`.

*right*<br/>
Объект типа `unordered_multimap`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты unordered_multimap не равны; **false** если они равны.

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

## <a name="op_eq_eq_multimap"></a> operator==

Проверяет, равен ли объект [unordered_multimap](../standard-library/unordered-multimap-class.md) в левой части объекту unordered_multimap в правой части.

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `unordered_multimap`.

*right*<br/>
Объект типа `unordered_multimap`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты unordered_multimap равны; **false** если они не равны.

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

[<unordered_map>](../standard-library/unordered-map.md)<br/>
