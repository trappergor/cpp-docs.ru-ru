---
title: Операторы &lt;valarray&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- valarray/std::operator!=
- valarray/std::operator%
- valarray/std::operator&amp;
- valarray/std::operator&amp;&amp;
- valarray/std::operator&gt;
- valarray/std::operator&gt;&gt;
- valarray/std::operator&gt;=
- valarray/std::operator&lt;
- valarray/std::operator&lt;&lt;
- valarray/std::operator&lt;=
- valarray/std::operator*
- valarray/std::operator+
- valarray/std::operator-
- valarray/std::operator/
- valarray/std::operator==
- valarray/std::operator^
- valarray/std::operator|
- valarray/std::operator||
dev_langs:
- C++
ms.assetid: 8a53562c-90ab-4eb3-85d3-ada5259d90b0
helpviewer_keywords:
- std::operator!= (valarray), std::operator&amp; (valarray)
- std::operator&amp;&amp; (valarray)
- std::operator&gt; (valarray)
- std::operator&gt;&gt; (valarray)
- std::operator&gt;= (valarray)
- std::operator&lt; (valarray)
- std::operator&lt;&lt; (valarray)
- std::operator&lt;= (valarray), std::operator== (valarray)
ms.openlocfilehash: e65d11ef95b5305988fe77ab258bb39c2b80de57
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="ltvalarraygt-operators"></a>Операторы &lt;valarray&gt;

||||
|-|-|-|
|[оператор!=](#op_neq)|[оператор%](#op_mod)|[оператор&amp;](#op_amp)|
|[operator&amp;&amp;](#op_amp_amp)|[оператор&gt;](#op_gt)|[operator&gt;&gt;](#op_gt_gt)|
|[operator&gt;=](#op_gt_eq)|[оператор&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|
|[operator&lt;=](#op_lt_eq)|[оператор*](#op_star)|[operator+](#op_add)|
|[operator-](#operator-)|[оператор/](#op_div)|[оператор==](#op_eq_eq)|
|[оператор^](#op_xor)|[оператор|](#op_or)|[оператор||](#op_lor)|

## <a name="op_neq"></a> operator!=

Проверяет, не равны ли все элементы двух одинаковых по размеру объектов valarray или не равны ли все элементы объекта valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator!=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого должны быть для проверки на неравенство.

`right` Второе из двух valarray, элементы которого должны быть для проверки на неравенство.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если соответствующие элементы не равны;

- **false**, если соответствующие элементы равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает объект класса [valarray\<bool >](../standard-library/valarray-bool-class.md), каждый из которых элементов `I` — `left[I] != right[I]`.

Второй оператор шаблона сохраняет в элемент `I` `left[I] != right`.

Третий оператор шаблона сохраняет в элемент `I` `left != right[I]`.

### <a name="example"></a>Пример

```cpp
// valarray_op_ne.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL != vaR );
   cout << "The element-by-element result of "
        << "the not equal comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the not equal comparison test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="op_mod"></a>  оператор%

Вычисляет остаток от деления соответствующих элементов двух одинаковых по размеру объектов valarray, остаток от деления объекта valarray на указанное значение или остаток от деления указанного значения на объект valarray.

```cpp
template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator%(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Значение или, служащий в качестве делимого в какой другое значение valarray или valarray требуется разделить.

`right` Значение или массив valarray, который выступает в качестве делителя и которая делит другое значение или valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого являются поэлементно остатков из `left` деленная `right`.

### <a name="example"></a>Пример

```cpp
// valarray_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   valarray<int> vaREM ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaREM = ( vaL % vaR );
   cout << "The remainders from the element-by-element "
        << "division is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaREM [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 53 -67 53 -67 53 -67 ).
The initial Right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
 valarray: ( 0 -3 4 -7 1 -3 ).
*\
```

## <a name="op_amp"></a> operator&amp;

Вычисляет результат применения побитовой операции **И** между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента.

```cpp
template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, соответствующие элементы которого сами являются объединяются побитовым **AND** или указанное значение типа элемента для побитового объединения с каждого элемента valarray.

`right` Второе из двух valarray, соответствующие элементы которого сами являются объединяются побитовым **AND** или указанное значение типа элемента для побитового объединения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого представляют собой поэлементную сочетание побитовую операцию и для `left` и `right`.

### <a name="remarks"></a>Примечания

Побитовые операции могут использоваться только с типами данных `char` и `int` и их разновидностями и не могут использоваться с типами **float**, **double**, **longdouble**, `void`, `bool` или другими, более сложными типами данных.

Побитовое **И** имеет ту же таблицу истинности, что и логическое **И** , но применяется к типам данных на уровне отдельных битов. Оператор [operator&&](../standard-library/valarray-operators.md#amp) применяется на уровне элемента, интерпретируя все ненулевые значения как true. Результатом является объект valarray из логических значений. Применение оператора побитового "И" **operator&**, напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaBWA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i+1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaBWA = ( vaL & vaR );
   cout << "The element-by-element result of "
        << "the bitwise operator & is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaBWA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 0 2 0 4 0 6 0 8 0 10 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the bitwise operator & is the
 valarray: ( 0 0 0 0 0 4 0 0 0 8 ).
*\
```

## <a name="op_amp_amp"></a> operator&amp;&amp;

Вычисляет результат применения логической операции **И** между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента valarray.

```cpp
template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator&&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, соответствующие элементы которого сами являются для объединения с логическим **AND** или указанное значение типа элемента для объединения с каждого элемента valarray.

`right` Второе из двух valarray, соответствующие элементы которого сами являются для объединения с логическим **AND** или указанное значение типа элемента для объединения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого имеют тип bool и поэлементно сочетания логического **AND** операции `left` и `right`.

### <a name="remarks"></a>Примечания

Оператор логическое "И" (**operator&&**) применяется на уровне элемента, интерпретируя все ненулевые значения как true. Результатом является объект valarray из логических значений. Применение оператора побитового **И** ([operator&](../standard-library/valarray-operators.md#op_amp)), напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_logand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL && vaR );
   cout << "The element-by-element result of "
        << "the logical AND operator&& is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&& is the
 valarray: ( 0 0 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_gt"></a> operator&gt;

Проверяет, что элементы одного объекта valarray больше чем элементы одинакового по размеру объекта valarray или что все элементы объекта valarray больше или меньше, чем указанное значение.

```cpp
template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

`right` Второе из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если элемент или значение `left` больше соответствующего элемента или значения `right`;

- **true**, если элемент или значение `left` меньше или равен соответствующему элементу или значению `right`.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_gt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL > vaR );
   cout << "The element-by-element result of "
        << "the greater than comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than comparison test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_gt_eq"></a>  оператор&gt;=

Проверяет, больше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

`right` Второе из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если элемент или значение `left` больше или равен соответствующему элементу или значению `right`;

- **false**, если элемент или значение `left` меньше соответствующего элемента или значения `right`.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_ge.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >= vaR );
   cout << "The element-by-element result of "
        << "the greater than or equal test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than or equal test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_gt_gt"></a> operator&gt;&gt;

Сдвигает вправо биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.

```cpp
template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator>>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Значение Сдвиг или valarray, элементы которого являются сдвиг.

`right` Значение, указывающее количество сдвига вправо или valarray, элементы которого указывают поэлементно сдвига вправо.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого были сдвинуты вправо указанное на количество позиций.

### <a name="remarks"></a>Примечания

Для чисел со знаком их знак сохраняется.

### <a name="example"></a>Пример

```cpp
// valarray_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >> vaR );
   cout << "The element-by-element result of "
        << "the right shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
*\
```

## <a name="op_lt"></a> operator&lt;

Проверяет, меньше ли элементы одного valarray, чем элементы одинакового по размеру valarray или больше ли либо меньше ли все элементы valarray, чем указанное значение.

```cpp
template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

`right` Второе из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если элемент или значение `left` меньше соответствующего элемента или значения `right`;

- **false**, если элемент или значение `left` больше или равен соответствующему элементу или значению `right`.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_lt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL < vaR );
   cout << "The element-by-element result of "
        << "the less-than comparson test is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the less-than comparson test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="op_lt_eq"></a> operator&lt;=

Проверяет, меньше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

`right` Второе из двух valarray, элементы которого являются для сравнения или указанное значение для сравнения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если элемент или значение `left` меньше или равен соответствующему элементу или значению `right`;

- **false**, если элемент или значение `left` больше соответствующего элемента или значения `right`.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_le.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL <= vaR );
   cout << "The element-by-element result of "
        << "the less than or equal test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the less than or equal test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="op_lt_lt"></a> operator&lt;&lt;

Сдвигает влево биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.

```cpp
template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator<<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Значение Сдвиг или valarray, элементы которого являются сдвиг.

`right` Значение, указывающее количество сдвига влево или valarray, элементы которого указывают поэлементно сдвига влево.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого были сдвинуты влево указанное на количество позиций.

### <a name="remarks"></a>Примечания

Для чисел со знаком их знак сохраняется.

### <a name="example"></a>Пример

```cpp
// valarray_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL << vaR );
   cout << "The element-by-element result of "
        << "the left shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift is the
 valarray: ( 1 -2 4 -8 16 -32 64 -128 ).
*\
```

## <a name="op_star"></a>  оператор*

Вычисляет результат поэлементного умножения для двух одинаковых по размеру объектов valarray или результат умножения объекта valarray на указанное значение.

```cpp
template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator*(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого являются умножение или указанное значение будет умножено с каждого элемента valarray.

`right` Второе из двух valarray, элементы которого являются умножение или указанное значение будет умножено с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого являются учитывающего элементы произведения из `left` и `right`.

### <a name="example"></a>Пример

```cpp
// valarray_op_eprod.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL * vaR );
   cout << "The element-by-element result of "
        << "the multiplication is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*\
```

## <a name="op_add"></a>  оператор+

Вычисляет поэлементную сумму для двух одинаковых по размеру объектов valarray или результат сложения объекта valarray с указанным значением.

```cpp
template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator+(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого должны быть добавлены или указанное значение дополняется каждого элемента valarray.

`right` Второе из двух valarray, элементы которого должны быть добавлены или указанное значение, добавляемое с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого являются суммой поэлементно из `left` и `right`.

### <a name="example"></a>Пример

```cpp
// valarray_op_esum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL + vaR );
   cout << "The element-by-element result of "
        << "the sum is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
 valarray: ( 2 0 4 2 6 4 8 6 ).
*\
```

## <a name="operator-"></a>  оператор-

Вычисляет поэлементную разность для двух одинаковых по размеру объектов valarray или разность между объектом valarray и указанным значением.

```cpp
template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator-(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Значение или valarray, выступающее в роли, из которой должны вычитается при формировании разница значений или valarrays Уменьшаемое.

`right` Значение или valarray, выступающее в роли, которое вычитается из других значений или valarrays при формировании различие вычитаемое.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого являются результат поэлементного вычитания из `left` и `right`.

### <a name="remarks"></a>Примечания

Арифметическая терминология, используемая в описании вычитания:

разность = уменьшаемое - вычитаемое

### <a name="example"></a>Пример

```cpp
// valarray_op_ediff.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL - vaR );
   cout << "The element-by-element result of "
        << "the difference is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
*\
```

## <a name="op_div"></a>  оператор/

Вычисляет результат поэлементного деления для двух одинаковых по размеру объектов valarray или результат деления объекта valarray на указанное значение.

```cpp
template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator/(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Значение или, служащий в качестве делимого в какой другое значение valarray или valarray — разделить при формировании частное.

`right` Значение или массив valarray, который выступает в качестве делителя и который делит другим значением или valarray при формировании частное.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого являются результат поэлементного деления из `left` деленная `right`.

### <a name="remarks"></a>Примечания

Арифметическая терминология, используемая в описании деления:

частное = делимое / делитель

### <a name="example"></a>Пример

```cpp
// valarray_op_equo.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   valarray<double> vaNE ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL / vaR );
   cout << "The element-by-element result of "
        << "the quotient is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
 valarray: ( inf -50 25 -16.6667 12.5 -10 ).
*\
```

## <a name="op_eq_eq"></a> operator==

Проверяет, равны ли все элементы двух одинаковых по размеру объектов valarray или равны ли все элементы объекта valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator==(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, элементы которого должны проверяться на равенство.

`right` Второе из двух valarray, элементы которого должны проверяться на равенство.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если соответствующие элементы равны.

- **false**, если соответствующие элементы не равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает объект класса [valarray\<bool >](../standard-library/valarray-bool-class.md), каждый из которых элементов `I` — `left[I] == right[I]`. Второй оператор шаблона сохраняет в элемент `I` `left[I] == right`. Третий оператор шаблона сохраняет в элемент `I` `left == right[I]`.

### <a name="example"></a>Пример

```cpp
// valarray_op_eq.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL == vaR );
   cout << "The element-by-element result of "
        << "the equality comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the equality comparison test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_xor"></a>  оператор^

Вычисляет результат применения побитовой операции исключающего `OR` **ИЛИ** между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента.

```cpp
template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator^(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, соответствующие элементы которого сами являются объединяются побитовым **XOR** или указанное значение типа элемента для побитового объединения с каждого элемента valarray.

`right` Второе из двух valarray, соответствующие элементы которого сами являются объединяются побитовым **XOR** или указанное значение типа элемента для побитового объединения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого представляют собой поэлементную сочетание побитового **XOR** операции `left` и `right`.

### <a name="remarks"></a>Примечания

Побитовую операцию может использоваться только для управления bits в `char` и `int` типов данных и их вариантов и не в **float**, **двойные**, `long double`, `void`, `bool` или других, более сложных типов данных.

Побитовое исключающее `OR` ( **ИЛИ**) имеет следующую семантику: если взять биты *b*1 и *b*2, то *b*1 **исключающее ИЛИ** *b*2 имеет значение **true**, если только один из битов имеет значение true, и имеет значение **false**, если оба бита имеют значение false или оба бита имеют значение true.

### <a name="example"></a>Пример

```cpp
// valarray_op_xor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL ^ vaR );
   cout << "The element-by-element result of "
        << "the bitwise XOR operator^ is the\n valarray: ( ";
           for ( i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^ is the
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
*\
```

## <a name="op_or"></a>  оператор|

Получает результат применения побитовой операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.

```cpp
template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator|(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, соответствующие элементы которого сами являются объединяются побитовым `OR` или указанное значение типа элемента для побитового объединения с каждого элемента valarray.

`right` Второе из двух valarray, соответствующие элементы которого сами являются объединяются побитовым `OR` или указанное значение типа элемента для побитового объединения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого представляют собой поэлементную сочетание побитового `OR` операции `left` и `right`.

### <a name="remarks"></a>Примечания

Побитовые операции могут использоваться только с типами данных `char` и `int` и их разновидностями и не могут использоваться с типами **float**, **double**, **longdouble**, `void`, `bool` или другими, более сложными типами данных.

Побитовое "ИЛИ" имеет ту же таблицу истинности, что и логическое `OR` , но применяется к типам данных на уровне отдельных битов. Если взять биты *b*1 и *b*2, то*b*1 `OR` *b*2 имеет значение **true**, если хотя бы один из битов имеет значение true, и имеет значение **false**, если оба бита имеют значение false. Оператор логическое `OR`[(operator||)](../standard-library/valarray-operators.md#op_lor) применяется на уровне элемента, интерпретируя все ненулевые значения как **true**. Результатом является объект valarray из логических значений. Применение оператора побитового "ИЛИ" `operator|`, напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL | vaR );
   cout << "The element-by-element result of "
        << "the bitwise OR operator| is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise OR operator| is the
 valarray: ( 1 0 1 3 3 4 7 6 7 9 ).
*\
```

## <a name="op_lor"></a>  оператор||

Вычисляет результат применения логической операции `OR` между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента valarray.

```cpp
template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator||(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух valarray, соответствующие элементы которого сами являются для объединения с логическим `OR` или указанное значение типа элемента для объединения с каждого элемента valarray.

`right` Второе из двух valarray, соответствующие элементы которого сами являются для объединения с логическим `OR` или указанное значение типа элемента для объединения с каждого элемента valarray.

### <a name="return-value"></a>Возвращаемое значение

Valarray, элементы которого имеют тип `bool` и поэлементно сочетания логическую операцию OR `left` и `right`.

### <a name="remarks"></a>Примечания

Логический `OR` `operator||` применяется на уровне элемента, подсчет нулевых значений как **true**, и это является результатом valarray логических значений. Применение оператора побитового `OR`, [operator|](../standard-library/valarray-operators.md#op_or), напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_logor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLOR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLOR = ( vaL || vaR );
   cout << "The element-by-element result of "
        << "the logical OR operator|| is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaLOR [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 0 0 3 0 0 6 0 0 9 ).
The element-by-element result of the logical OR operator|| is the
 valarray: ( 0 0 0 1 0 1 1 1 0 1 ).
*\
```

## <a name="see-also"></a>См. также

[\<valarray>](../standard-library/valarray.md)<br/>
