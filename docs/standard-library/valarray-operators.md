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
ms.openlocfilehash: 0c297ddf24c1ed357a0756c5e0e5631e7b3d1c02
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964838"
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

*left*  
 Первый из двух объектов valarray, элементы которых проверяются на неравенство.

*right*  
 Второй из двух объектов valarray, элементы которых проверяются на неравенство.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если соответствующие элементы не равны;

- **false**, если соответствующие элементы равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает объект класса [valarray\<bool >](../standard-library/valarray-bool-class.md), каждый из элементов которого `I` является `left[I] != right[I]`.

Второй оператор шаблона сохраняет элемент `I` `left[I] != right`.

Третий оператор шаблона сохраняет элемент `I` `left != right[I]`.

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

*left*  
 Значение или объект valarray, который служит в качестве делимого, которое делится на другое значение или на объект valarray.

*right*  
 Значение или объект valarray, который выступает в качестве делителя, на который делится другое значение или объект valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой остаток от *левой* деления на *правой*.

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

*left*  
 Первый из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

*right*  
 Второй из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой сочетание побитовой операции и из *левой* и *правой*.

### <a name="remarks"></a>Примечания

Операцию побитового может использоваться только для управления bits в **char** и **int** типы данных и их разновидностями и не на **float**, **двойные**, **longdouble**, **void**, **bool** или другими, более сложными типами данных.

Побитовое `AND` имеет ту же таблицу истинности, что и логическое `AND`, но применяется к типам данных на уровне отдельных битов. Оператор [operator&&](../standard-library/valarray-operators.md#amp) применяется на уровне элемента, интерпретируя все ненулевые значения как true. Результатом является объект valarray из логических значений. Применение оператора побитового "И" **operator&**, напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

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

*left*  
 Первый из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

*right*  
 Второй из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого имеет логический тип и представляют собой представляет собой сочетание логического `AND` работы *левой* и *правой*.

### <a name="remarks"></a>Примечания

Логический `ANDoperator&&` применяется на уровне элемента, интерпретируя все ненулевые значения как true и результатом является объект valarray из логических значений. Побитового `AND`, [оператор &,](../standard-library/valarray-operators.md#op_amp), напротив, может привести в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

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

*left*  
 Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*  
 Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **значение true,** Если *левой* элемента или значения больше, чем соответствующий *правой* элемента или значения.

- **false** Если *левой* элемент или значение не превышает соответствующий *правой* элемента или значения.

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

*left*  
 Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*  
 Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **значение true,** Если *левой* больше или равен соответствующему элементу или значению *правой* элемента или значения.

- **false** Если *левой* элемента или значения меньше, чем соответствующий *правой* элемента или значения.

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

*left*  
 Значение для сдвига или объект valarray, элементы которого будут сдвигаться.

*right*  
 Значение, которое указывает количество позиций для сдвига вправо, или объект valarray, элементы которого указывают поэлементное количество позиций для сдвига вправо.

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

*left*  
 Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*  
 Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **значение true,** Если *левой* элемента или значения меньше, чем соответствующий *правой* элемента или значения.

- **false** Если *левой* элемент или значение не меньше, чем соответствующие *правой* элемента или значения.

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

*left*  
 Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*  
 Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **значение true,** Если *левой* элемент или значение меньше или равен соответствующему *правой* элемента или значения.

- **false** Если *левой* элемента или значения больше, чем соответствующий *правой* элемента или значения.

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

*left*  
 Значение для сдвига или объект valarray, элементы которого будут сдвигаться.

*right*  
 Значение, которое указывает количество позиций для сдвига влево, или объект valarray, элементы которого указывают поэлементное количество позиций для сдвига влево.

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

*left*  
 Первый из двух объектов valarray, элементы которого будут участвовать в умножении, или указанное значение, которое будет умножаться на каждый элемент valarray.

*right*  
 Второй из двух объектов valarray, элементы которого будут участвовать в умножении, или указанное значение, которое будет умножаться на каждый элемент valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого поэлементного умножения из *левой* и *правой*.

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

*left*  
 Первый из двух объектов valarray, элементы которого будут участвовать в сложении, или указанное значение, которое будет складываться с каждым элементом valarray.

*right*  
 Второй из двух объектов valarray, элементы которого будут участвовать в сложении, или указанное значение, которое будет складываться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой сумму из *левой* и *правой*.

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

*left*  
 Значение или объект valarray, который выступает в качестве уменьшаемого, из которого вычитаются другие значения или объекты valarray.

*right*  
 Значение или объект valarray, который выступает в качестве вычитаемого и вычитается из других значений или объектов valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой разность из *левой* и *правой*.

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

*left*  
 Значение или объект valarray, который служит в качестве делимого, которое делится на другое значение или на объект valarray для формирования частного.

*right*  
 Значение или объект valarray, который выступает в качестве делителя, на который делится другое значение или объект valarray для формирования частного.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой частное от *левой* деления на *правой*.

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

*left*  
 Первый из двух объектов valarray, элементы которых проверяются на равенство.

*right*  
 Второй из двух объектов valarray, элементы которых проверяются на равенство.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **true**, если соответствующие элементы равны.

- **false**, если соответствующие элементы не равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает объект класса [valarray\<bool >](../standard-library/valarray-bool-class.md), каждый из элементов которого `I` является `left[I] == right[I]`. Второй оператор шаблона сохраняет элемент `I` `left[I] == right`. Третий оператор шаблона сохраняет элемент `I` `left == right[I]`.

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

*left*  
 Первый из двух объектов valarray, элементы которого объединяются с помощью операции "исключающее **ИЛИ**", или указанное значение типа элемента, которое объединяется с помощью операции "исключающее ИЛИ" с каждым элементом объекта valarray.

*right*  
 Второй из двух объектов valarray, элементы которого объединяются с помощью операции "исключающее **ИЛИ**", или указанное значение типа элемента, которое объединяется с помощью операции "исключающее ИЛИ" с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой сочетание побитового **XOR** работы *левой* и *правой*.

### <a name="remarks"></a>Примечания

Операцию побитового может использоваться только для управления bits в **char** и **int** типы данных и их разновидностями и не на **float**, **двойные**, **long double**, **void**, **bool** или другими, более сложными типами данных.

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

*left*  
 Первый из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

*right*  
 Второй из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой сочетание побитового `OR` работы *левой* и *правой*.

### <a name="remarks"></a>Примечания

Операцию побитового может использоваться только для управления bits в **char** и **int** типы данных и их разновидностями и не на **float**, **двойные**, **longdouble**, **void**, **bool** или другими, более сложными типами данных.

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

*left*  
 Первый из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

*right*  
 Второй из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого имеют тип **bool** и представляют собой представляет собой сочетание логическую операцию OR *левой* и *правой*.

### <a name="remarks"></a>Примечания

Логический `OR` `operator||` применяется на уровне элемента, интерпретируя все ненулевые значения как **true**, а результатом является объект valarray из логических значений. Применение оператора побитового `OR`, [operator|](../standard-library/valarray-operators.md#op_or), напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

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
