---
title: Класс binder1st
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder1st
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
ms.openlocfilehash: f70a1a4a0903b66edf5f42e59788b9a2d97fc967
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006634"
---
# <a name="binder1st-class"></a>Класс binder1st

Класс шаблона, предоставляющий конструктор, который преобразует объект бинарной функции в объект унарной функции, привязывая первый аргумент бинарной функции к указанному значению. Нерекомендуемыми в C ++ 11 для [привязать](functional-functions.md#bind)и удалены в C ++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Operation>
class binder1st
    : public unaryFunction <typename Operation::second_argument_type,
                             typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder1st(
        const Operation& binary_fn,
        const typename Operation::first_argument_type& left);

    result_type operator()(const argument_type& right) const;
    result_type operator()(const argument_type& right) const;

protected:
    Operation op;
    typename Operation::first_argument_type value;
};
```

### <a name="parameters"></a>Параметры

*binary_fn*<br/>
Объект бинарной функции, который необходимо преобразовать в объект унарной функции.

*left*<br/>
Значение, к которому необходимо привязать первый аргумент объекта бинарной функции.

*right*<br/>
Значение аргумента, которое адаптированный объект бинарной функции сравнивает с фиксированным значением второго аргумента.

## <a name="return-value"></a>Возвращаемое значение

Объект унарной функции, полученный в результате привязки первого аргумента объекта бинарной функции к значению *левой*.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет копию объекта бинарной функции *binary_fn* в `op`и копия *левой* в `value`. Он определяет свою функцию-член `operator()` как возвращающий `op( value, right )`.

Если *binary_fn* — это объект типа `Operation` и `c` — константа, то `bind1st( binary_fn, c )` является более удобным эквивалентно `binder1st<Operation>( binary_fn, c )`. Дополнительные сведения см. в разделе [bind1st](../standard-library/functional-functions.md#bind1st).

## <a name="example"></a>Пример

```cpp
// functional_binder1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(),
        binder1st<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare use of binder2nd fixing 2nd argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder2nd<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
*/
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
