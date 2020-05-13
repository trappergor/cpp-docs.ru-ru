---
title: Операторы &lt;hash_set&gt;
ms.date: 03/27/2019
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
ms.openlocfilehash: 5830c9e459c0d778e85c5ab5900d39c3190df178
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368573"
---
# <a name="lthash_setgt-operators"></a>Операторы &lt;hash_set&gt;

||||
|-|-|-|
|[оператора!](#op_neq)|[operator!= (hash_multiset)](#op_neq_hash_multiset)|[оператора](#op_eq_eq)|
|[оператор (hash_multiset)](#op_eq_eq_hash_multiset)|

## <a name="operator"></a><a name="op_neq"></a>оператора!

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет неравенство объекта hash_set слева от оператора и объекта hash_set справа от оператора.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа `hash_set`.

*Правильно*\
Объект типа `hash_set`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объекты hash_set не равны; **false**, если объекты hash_set равны.

### <a name="remarks"></a>Remarks

Сравнение между объектами hash_set основывается на попарном сравнении их элементов. Два объекта hash_set равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

Члены [<hash_map>](../standard-library/hash-map.md) и [файлы заголовка<hash_set>](../standard-library/hash-set.md) находятся в [stdext Namespace.](../standard-library/stdext-namespace.md)

### <a name="example"></a>Пример

```cpp
// hash_set_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_sets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_sets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_sets hs1 and hs2 are not equal.
The hash_sets hs1 and hs3 are equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a>оператора

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет равенство объекта hash_set слева от оператора и объекта hash_set справа от оператора.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа `hash_set`.

*Правильно*\
Объект типа `hash_set`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект hash_set слева от оператора равен объекту hash_set справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами hash_set основывается на попарном сравнении их элементов. Два объекта hash_set равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// hash_set_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_sets s1 and s2 are equal." << endl;
   else
      cout << "The hash_sets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_sets s1 and s3 are equal." << endl;
   else
      cout << "The hash_sets s1 and s3 are not equal." << endl;
}
```

```Output
The hash_sets s1 and s2 are not equal.
The hash_sets s1 and s3 are equal.
```

## <a name="operator-hash_multiset"></a><a name="op_neq_hash_multiset"></a>оператор! ( hash_multiset)

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет неравенство объекта hash_multiset слева от оператора и объекта hash_multiset справа от оператора.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа `hash_multiset`.

*Правильно*\
Объект типа `hash_multiset`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объекты hash_multiset не равны; **false**, если они равны.

### <a name="remarks"></a>Remarks

Сравнение между объектами hash_multiset основывается на попарном сравнении их элементов. Два объекта hash_multiset равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// hashset_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_multisets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_multisets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_multisets hs1 and hs2 are not equal.
The hash_multisets hs1 and hs3 are equal.
```

## <a name="operator-hash_multiset"></a><a name="op_eq_eq_hash_multiset"></a>оператор (hash_multiset)

> [!NOTE]
> Этот элемент API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет равенство объекта hash_multiset слева от оператора и объекта hash_multiset справа от оператора.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа `hash_multiset`.

*Правильно*\
Объект типа `hash_multiset`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если объект hash_multiset слева от оператора равен объекту hash_multiset справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами hash_multiset основывается на попарном сравнении их элементов. Два объекта hash_multiset равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// hash_multiset_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;
}
```

```Output
The hash_multisets s1 and s2 are not equal.
The hash_multisets s1 and s2 are equal.
```

## <a name="see-also"></a>См. также раздел

[<hash_set>](../standard-library/hash-set.md)
