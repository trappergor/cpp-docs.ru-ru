---
title: Класс binder2nd
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: 5f59887e6c9d2965a6c8680f17a40c5bd93869c0
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243358"
---
# <a name="binder2nd-class"></a>Класс binder2nd

Класс шаблона, предоставляющий конструктор, который преобразует объект бинарной функции в объект унарной функции, привязывая второй аргумент бинарной функции к указанному значению. Рекомендуется использовать в C ++ 11, удалено в C ++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;
};
```

### <a name="parameters"></a>Параметры

*Func*\
Объект бинарной функции, который необходимо преобразовать в объект унарной функции.

*Правильно*\
Значение, к которому необходимо привязать второй аргумент объекта бинарной функции.

*Слева*\
Значение аргумента, которое адаптированный объект бинарной функции сравнивает с фиксированным значением второго аргумента.

## <a name="return-value"></a>Возвращаемое значение

Объект унарной функции, полученный в результате привязки второго аргумента объекта бинарной функции к значению *правой*.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет копию объекта бинарной функции _ *Func* в `op`и копия *правой* в `value`. Он определяет свою функцию-член `operator()` как возвращающий **op**(`left`, **значение**).

Если `Func` — это объект типа `Operation` и c — константа, то [bind2nd](../standard-library/functional-functions.md#bind2nd) (`Func`, `c`) эквивалентен `binder2nd` конструктор класса `binder2nd` \<  **Операция**> (`Func`, `c`) и является более удобным.

## <a name="example"></a>Пример

```cpp
// functional_binder2nd.cpp
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
        binder2nd<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare using binder1st fixing 1st argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder1st<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
```
