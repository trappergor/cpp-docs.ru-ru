---
title: операторы &lt;memory&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
ms.openlocfilehash: 0b5589db7f38a53c4f7112dc5d3254f56e5fbb47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473350"
---
# <a name="ltmemorygt-operators"></a>операторы &lt;memory&gt;

||||
|-|-|-|
|[operator!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[оператор&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Проверяет неравенство между объектами.

```cpp
template <class Type, class Other>
bool operator!=(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>
bool operator!=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator!=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Один из объектов для проверки на неравенство.

*right*<br/>
Один из объектов для проверки на неравенство.

*Ty1*<br/>
Тип, управляемый левым общим указателем.

*Ty2*<br/>
Тип, управляемый правым общим указателем.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты не равны, значение **false**, если объекты равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает значение false. (Все распределители по умолчанию равны.)

Второй и третий операторы шаблона возвращают `!(left == right)`.

### <a name="example"></a>Пример

```cpp
// memory_op_me.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<double> Alloc;
   vector <char>:: allocator_type v1Alloc;

   if ( Alloc != v1Alloc )
      cout << "The allocator objects Alloc & v1Alloc not are equal."
           << endl;
   else
      cout << "The allocator objects Alloc & v1Alloc are equal."
           << endl;
}
```

```Output
The allocator objects Alloc & v1Alloc are equal.
```

### <a name="example"></a>Пример

```cpp
// std__memory__operator_ne.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 != sp0 == " << std::boolalpha
        << (sp0 != sp0) << std::endl;
    std::cout << "sp0 != sp1 == " << std::boolalpha
        << (sp0 != sp1) << std::endl;

    return (0);
    }

```

```Output
sp0 != sp0 == false
sp0 != sp1 == true
```

## <a name="op_eq_eq"></a>  оператор==

Проверяет равенство между объектами.

```cpp
template <class Type, class Other>
bool operator==(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>
bool operator==(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>
bool operator==(
    const shared_ptr<Ty1>& left;,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Один из объектов для проверки на равенство.

*right*<br/>
Один из объектов для проверки на равенство.

*Ty1*<br/>
Тип, управляемый левым общим указателем.

*Ty2*<br/>
Тип, управляемый правым общим указателем.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты равны, **false** Если объекты не равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает значение true. (Все распределители по умолчанию равны.)

Второй и третий операторы шаблона возвращают `left.get() ==  right.get()`.

### <a name="example"></a>Пример

```cpp
// memory_op_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<char> Alloc;
   vector <int>:: allocator_type v1Alloc;

   allocator<char> cAlloc(Alloc);
   allocator<int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

### <a name="example"></a>Пример

```cpp
// std__memory__operator_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 == sp0 == " << std::boolalpha
        << (sp0 == sp0) << std::endl;
    std::cout << "sp0 == sp1 == " << std::boolalpha
        << (sp0 == sp1) << std::endl;

    return (0);
    }

```

```Output
sp0 == sp0 == true
sp0 == sp1 == false
```

## <a name="op_gt_eq"></a> operator&gt;=

Проверяет, больше или равен один объект второму объекту.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator>=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>
bool operator>=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Один из сравниваемых объектов.

*right*<br/>
Один из сравниваемых объектов.

*Ty1*<br/>
Тип, управляемый левым общим указателем.

*Ty2*<br/>
Тип, управляемый правым общим указателем.

### <a name="remarks"></a>Примечания

Операторы шаблона возвращают `left.get() >= right.get()`.

## <a name="op_lt"></a> operator&lt;

Проверяет, меньше ли один объект второго объекта.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Один из сравниваемых объектов.

*right*<br/>
Один из сравниваемых объектов.

*Ty1*<br/>
Тип, управляемый левым указателем.

*Ty2*<br/>
Тип, управляемый правым указателем.

## <a name="op_lt_eq"></a> operator&lt;=

Проверяет, меньше или равен один объект второму объекту.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Один из сравниваемых объектов.

*right*<br/>
Один из сравниваемых объектов.

*Ty1*<br/>
Тип, управляемый левым общим указателем.

*Ty2*<br/>
Тип, управляемый правым общим указателем.

### <a name="remarks"></a>Примечания

Операторы шаблона возвращают `left.get() <= right.get()`

## <a name="op_gt"></a> operator&gt;

Проверяет, больше ли один объект второго объекта.

```cpp
template <class Ty1, class Del1, class Ty2, class Del2>
bool operator>(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>
bool operator>(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Один из сравниваемых объектов.

*right*<br/>
Один из сравниваемых объектов.

*Ty1*<br/>
Тип, управляемый левым общим указателем.

*Ty2*<br/>
Тип, управляемый правым общим указателем.

## <a name="op_lt_lt"></a> operator&lt;&lt;

Записывает в поток общий указатель.

```cpp
template <class Elem, class Tr, class Ty>
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,
    shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Параметры

*Elem*<br/>
Тип элемента потока.

*Tr*<br/>
Тип признаков элемента потока.

*Ty*<br/>
Тип, управляемый общим указателем.

*out*<br/>
Выходной поток.

*SP*<br/>
Общий указатель.

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `out << sp.get()`.

### <a name="example"></a>Пример

```cpp
// std__memory__operator_sl.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;

    return (0);
    }

```

```Output
sp0 == 3f3040 (varies)
```

## <a name="see-also"></a>См. также

[\<memory>](../standard-library/memory.md)<br/>
