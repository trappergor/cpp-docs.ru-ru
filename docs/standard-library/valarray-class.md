---
title: Класс valarray
ms.date: 03/27/2019
f1_keywords:
- valarray/std::valarray
- valarray/std::valarray::value_type
- valarray/std::valarray::apply
- valarray/std::valarray::cshift
- valarray/std::valarray::free
- valarray/std::valarray::max
- valarray/std::valarray::min
- valarray/std::valarray::resize
- valarray/std::valarray::shift
- valarray/std::valarray::size
- valarray/std::valarray::sum
- valarray/std::valarray::swap
helpviewer_keywords:
- std::valarray [C++]
- std::valarray [C++], value_type
- std::valarray [C++], apply
- std::valarray [C++], cshift
- std::valarray [C++], free
- std::valarray [C++], max
- std::valarray [C++], min
- std::valarray [C++], resize
- std::valarray [C++], shift
- std::valarray [C++], size
- std::valarray [C++], sum
- std::valarray [C++], swap
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
ms.openlocfilehash: 60e18ec68ebdd03a97933b222de00e20cd57f20f
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246147"
---
# <a name="valarray-class"></a>Класс valarray

Класс шаблона описывает объект, управляющий последовательностью элементов типа `Type` , хранятся в виде массива, предназначены для быстрого выполнения математических операций и оптимизированы для повышения производительности вычислений.

## <a name="remarks"></a>Примечания

Класс является представлением математического понятия упорядоченного набора значений, а для элементов применяется последовательная нумерация, начиная с нуля. Класс описывается почти как контейнер, так как он поддерживает некоторые, хотя и не все, возможности, поддерживаемые контейнерами последовательности первого класса, такими как [vector](../standard-library/vector-class.md). Он имеет два важных отличия от класса шаблона vector:

- Он определяет множество арифметических операций между соответствующими элементами `valarray<Type>` объектов одного типа и длины, такие как *xarr* = cos ( *yarr*) + sin ( *zarr*).

- Он определяет ряд интересных способов назначения индекса `valarray<Type>` объекта путем перегрузки [оператор&#91;&#93;](#op_at).

Объект класса `Type`:

- Имеет открытый конструктор по умолчанию, деструктор, конструктор копии и оператор присваивания, работающие обычным образом.

- При необходимости определяет арифметические операторы и математические функции, определенные для типов с плавающей запятой и работающие обычным образом.

В частности, между конструкцией копирования и конструкцией по умолчанию, за которыми следует присваивание, не может существовать даже малейших отличий. Ни одна из операций с объектами класса `Type` может вызывать исключения.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[valarray](#valarray)|Создает `valarray` определенного размера или с элементами, имеющими указанное значение, либо в качестве копии другого `valarray` или подмножества другого `valarray`.|

### <a name="typedefs"></a>Определения типов

|||
|-|-|
|[value_type](#value_type)|Тип, представляющий тип элемента, хранящегося в `valarray`.|

### <a name="functions"></a>Функции

|||
|-|-|
|[apply](#apply)|Применяет заданную функцию для каждого элемента объекта `valarray`.|
|[cshift](#cshift)|Циклически смещает все элементы в `valarray` на заданное число позиций.|
|[free](#free)|Освобождает память, используемую `valarray`.|
|[max](#max)|Находит наибольший элемент в `valarray`.|
|[min](#min)|Находит наименьший элемент в `valarray`.|
|[resize](#resize)|Изменяет количество элементов в `valarray` на заданное число, при необходимости добавляя или удаляя элементы.|
|[shift](#shift)|Смещает все элементы в `valarray` на заданное число позиций.|
|[size](#size)|Находит количество элементов в `valarray`.|
|[sum](#sum)|Определяет сумму всех элементов в `valarray` с ненулевой длиной.|
|[swap](#swap)||

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор!](#op_not)|Унарный оператор, который получает логические значения `NOT` каждого элемента в `valarray`.|
|[оператор%=](#op_mod_eq)|Получает остаток от поэлементного деления элементов массива на указанный `valarray` или на значение типа элемента.|
|[оператор&=](#op_and_eq)|Получает битовый `AND` элементов в массиве при помощи соответствующих элементов в указанном `valarray` или при помощи значения типа элемента.|
|[оператор>>=](#op_gt_gt_eq)|Сдвигает вправо биты для каждого элемента операнда `valarray` на указанное число позиций или на поэлементную сумму, указанную вторым `valarray`.|
|[оператор<<=](#op_lt_lt_eq)|Сдвигает влево биты для каждого элемента операнда `valarray` на указанное число позиций или на поэлементную сумму, указанную вторым `valarray`.|
|[оператор*=](#op_star_eq)|Поэлементно умножает элементы указанного `valarray` или значение типа элемента на операнд `valarray`.|
|[operator+](#op_add)|Унарный оператор, который прибавляет единицу к каждому элементу в `valarray`.|
|[оператор+=](#op_add_eq)|Поэлементно прибавляет элементы указанного `valarray` или значение типа элемента к операнду `valarray`.|
|[operator-](#operator-)|Унарный оператор, который отнимает единицу от каждого элемента в `valarray`.|
|[оператор-=](#operator-_eq)|Поэлементно вычитает элементы указанного `valarray` или значение типа элемента из операнда `valarray`.|
|[оператор/=](#op_div_eq)|Поэлементно делит операнд `valarray` на элементы указанного `valarray` или значение типа элемента.|
|[оператор=](#op_eq)|Назначает элементы для `valarray`, значения которых задаются либо непосредственно или как часть другого `valarray`, либо с помощью `slice_array`, `gslice_array`, `mask_array` или `indirect_array`.|
|[operator&#91;&#93;](#op_at)|Возвращает ссылку на элемент или его значение по указанному индексу или для определенного подмножества.|
|[оператор^=](#op_xor_eq)|Получает поэлементное исключающее логическое "ИЛИ" или применяет оператор (`XOR`) для массива с указанным valarray или с указанным значением типа элемента.|
|[оператор&#124;=](#op_or_eq)|Получает битовый `OR` элементов в массиве при помощи соответствующих элементов в указанном `valarray` или при помощи значения типа элемента.|
|[оператор~](#op_dtor)|Унарный оператор, который получает битовые значения `NOT` каждого элемента в `valarray`.|

## <a name="apply"></a> применить

Применяет заданную функцию для каждого элемента объекта valarray.

```cpp
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```

### <a name="parameters"></a>Параметры

*_Func(Type)* \
Объект функции, который будет применен к каждому элементу операнда valarray.

*_Func(const Type&)* \
Объект функции для константы, который будет применен к каждому элементу операнда valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, к элементам которого была применена функция `_Func`.

### <a name="remarks"></a>Примечания

Функция-член возвращает объект класса [valarray](../standard-library/valarray-class.md) **\<тип >** , длины [размер](#size), каждый из элементов которого *я*является `_Func((*this)[I])`.

### <a name="example"></a>Пример

```cpp
// valarray_apply.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

using namespace std;

int __cdecl MyApplyFunc( int n )
{
   return n*2;
}

int main( int argc, char* argv[] )
{
   valarray<int> vaR(10), vaApplied(10);
   int i;

   for ( i = 0; i < 10; i += 3 )
      vaR[i] = i;

   for ( i = 1; i < 10; i += 3 )
      vaR[i] = 0;

   for ( i = 2; i < 10; i += 3 )
      vaR[i] = -i;

   cout << "The initial Right valarray is: (";
   for   ( i=0; i < 10; ++i )
      cout << " " << vaR[i];
   cout << " )" << endl;

   vaApplied = vaR.apply( MyApplyFunc );

   cout << "The element-by-element result of "
       << "applying MyApplyFunc to vaR is the\nvalarray: ( ";
   for ( i = 0; i < 10; ++i )
      cout << " " << vaApplied[i];
   cout << " )" << endl;
}
```

```Output
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )
The element-by-element result of applying MyApplyFunc to vaR is the
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )
```

## <a name="cshift"></a> cshift

Циклически смещает все элементы в valarray на заданное число позиций.

```cpp
valarray<Type> cshift(int count) const;
```

### <a name="parameters"></a>Параметры

*число*\
Количество позиций, на которые элементы будут сдвинуты вперед.

### <a name="return-value"></a>Возвращаемое значение

Новый объект valarray, в которой все элементы которого были перемещены *число* позиций циклически к началу valarray, влево по отношению к их положения в операнде valarray.

### <a name="remarks"></a>Примечания

Положительное значение *число* перемещает элементы циклически смещаются влево *число* помещает.

Отрицательное значение *число* перемещает элементы циклически смещаются вправо *число* помещает.

### <a name="example"></a>Пример

```cpp
// valarray_cshift.cpp
// compile with: /EHsc

#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    valarray<int> va1(10), va2(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;
    for (i = 0; i < 10; i+=1)
        va2[i] = 10 - i;

    cout << "The operand valarray va1 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    // A positive parameter shifts elements right
    va1 = va1.cshift(4);
    cout << "The cyclically shifted valarray va1 is:\nva1.cshift (4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    cout << "The operand valarray va2 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;

    // A negative parameter shifts elements left
    va2 = va2.cshift(-4);
    cout << "The cyclically shifted valarray va2 is:\nva2.shift (-4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;
}
```

```Output
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)
The cyclically shifted valarray va1 is:
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)
The cyclically shifted valarray va2 is:
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)
```

## <a name="free"></a> бесплатно

Освобождает память, используемую объектом valarray.

```cpp
void free();
```

### <a name="remarks"></a>Примечания

Эта нестандартная функция эквивалентна присваиванию пустого объекта valarray. Например:

```cpp
valarray<T> v;
v = valarray<T>();

// equivalent to v.free()
```

## <a name="max"></a> max

Находит наибольший элемент объекта valarray.

```cpp
Type max() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное значение элемента в операнде valarray.

### <a name="remarks"></a>Примечания

Функция-член сравнивает значения, применяя **оператор\<**  или **оператор >** между парами элементов класса `Type`, операторы, должно быть указано для элемента `Type`.

### <a name="example"></a>Пример

```cpp
// valarray_max.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MaxValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i - 1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  10 - i;

   cout << "The operand valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MaxValue = vaR.max (  );
   cout << "The largest element in the valarray is: "
        << MaxValue  << "." << endl;
}
```

```Output
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).
The largest element in the valarray is: 13.
```

## <a name="min"></a> мин.

Находит наименьший элемент объекта valarray.

```cpp
Type min() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное значение элемента в операнде valarray.

### <a name="remarks"></a>Примечания

Функция-член сравнивает значения, применяя **оператор\<**  или **оператор >** между парами элементов класса `Type`, операторы, должно быть указано для элемента `Type`.

### <a name="example"></a>Пример

```cpp
// valarray_min.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MinValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  5 - i;

   cout << "The operand valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MinValue = vaR.min ( );
   cout << "The smallest element in the valarray is: "
        << MinValue  << "." << endl;
}
/* Output:
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).
The smallest element in the valarray is: -9.
*/
```

## <a name="op_not"></a> оператор!

Унарный оператор, который получает логическое **НЕ** для каждого элемента valarray.

```cpp
valarray<bool> operator!() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, каждый из элементов которого представляет собой логическое отрицание для соответствующего элемента операнда valarray.

### <a name="remarks"></a>Примечания

Логическая операция **НЕ** инвертирует элементы, то есть, она преобразует все нулевые элементы в единицу, а все ненулевые элементы считает равными единице и поэтому преобразует их в нули. Возвращаемый объект valarray состоит из логических значений и имеет тот же размер, что и operand valarray.

Имеется также битовую **не**[valarray::operator ~](#op_dtor) , который выполняет отрицание на уровне отдельных битов в двоичное представление **char** и **int**  элементы объекта valarray.

### <a name="example"></a>Пример

```cpp
// valarray_op_lognot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<bool> vaNOT ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaNOT = !vaL;
   cout << "The element-by-element result of "
        << "the logical NOT operator! is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The element-by-element result of the logical NOT operator! is the
valarray: ( 1 1 1 0 1 0 1 0 1 0 ).
```

## <a name="op_mod_eq"></a> оператор % =

Получает остаток от поэлементного деления элементов массива на указанный объект valarray или на значение типа элемента.

```cpp
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, на которое будет поэлементно делиться операнд valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, остаток от поэлементного деления операнда valarray с *вправо*

### <a name="example"></a>Пример

```cpp
// valarray_class_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL %= vaR;
   cout << "The remainders from the element-by-element "
        << "division is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 53 -67 53 -67 53 -67 ).
The initial  right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
valarray: ( 0 -3 4 -7 1 -3 ).
```

## <a name="op_and_eq"></a> Оператор&amp;=

Получает побитовое **И** для элементов в массиве и соответствующих элементов в указанном объекте valarray или значений типа элемента.

```cpp
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, для которого будет выполняться, представляет собой результат логического `AND` с операндом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой результат логического `AND` операнда valarray с *вправо*

### <a name="remarks"></a>Примечания

Операцию побитового может использоваться только для управления bits в **char** и **int** типы данных и их разновидностями и не на **float**, **двойные**, **longdouble**, **void**, **bool**, или другими, более сложными типами данных.

Побитовое и имеет ту же таблицу истинности, что и логическое `AND` , но применяется к типам данных на уровне отдельных битов. Взять биты *b*1 и *b*2, *b*1 `AND` *b*2 — **true** Если оба бита имеют значение true. **false** Если по крайней мере один имеет значение false.

### <a name="example"></a>Пример

```cpp
// valarray_class_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL &= vaR;
   cout << "The element-by-element result of "
        << "the logical AND operator&= is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&= is the
valarray: ( 0 0 0 2 0 4 0 6 0 8 ).
```

## <a name="op_gt_gt_eq"></a> Оператор&gt;&gt;=

Сдвигает вправо биты для каждого элемента valarray на указанное число позиций или на поэлементное количество позиций, определяемое вторым объектом valarray.

```cpp
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Значение, которое указывает количество позиций для сдвига вправо, или объект valarray, элементы которого указывают поэлементное количество позиций для сдвига вправо.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого были сдвинуты вправо сумму, указанную в *правой*.

### <a name="remarks"></a>Примечания

Для чисел со знаком их знак сохраняется.

### <a name="example"></a>Пример

```cpp
// valarray_class_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL >>= vaR;
   cout << "The element-by-element result of "
        << "the right shift is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
```

## <a name="op_lt_lt_eq"></a> Оператор&lt;&lt;=

Сдвигает влево биты для каждого элемента valarray на указанное число позиций или на поэлементное количество позиций, определяемое вторым объектом valarray.

```cpp
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Значение, которое указывает количество позиций для сдвига влево, или объект valarray, элементы которого указывают поэлементное количество позиций для сдвига влево.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого было сдвинуто влево на количество указанных в *правой*.

### <a name="remarks"></a>Примечания

Для чисел со знаком их знак сохраняется.

### <a name="example"></a>Пример

```cpp
// valarray_class_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL <<= vaR;
   cout << "The element-by-element result of "
        << "the left shift"
        << endl << "on the operand array is the valarray:"
        << endl << "( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift
on the operand array is the valarray:
( 1 -2 4 -8 16 -32 64 -128 ).
```

## <a name="op_star_eq"></a> оператор * =

Поэлементно умножает элементы указанного объекта valarray или значение типа элемента на операнд valarray.

```cpp
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, которое будет поэлементно умножаться на операнд valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой произведение операнда valarray и *правой*.

### <a name="example"></a>Пример

```cpp
// valarray_op_emult.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL *= vaR;
   cout << "The element-by-element result of "
        << "the multiplication is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*/
```

## <a name="op_add"></a> оператор +

Унарный оператор, который прибавляет единицу к каждому элементу объекта valarray.

```cpp
valarray<Type> operator+() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, содержащий элементы операнда valarray после сложения.

### <a name="example"></a>Пример

```cpp
// valarray_op_eplus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaPLUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaPLUS = +vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaPLUS [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
```

## <a name="op_add_eq"></a> оператор +=

Поэлементно складывает элементы указанного объекта valarray или значение типа элемента с операндом valarray.

```cpp
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, которое будет поэлементно складываться с операндом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой сумму операнда valarray и *правой*.

### <a name="example"></a>Пример

```cpp
// valarray_op_eadd.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL += vaR;
   cout << "The element-by-element result of "
        << "the sum is the"
        << endl << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
valarray: ( 2 0 4 2 6 4 8 6 ).
```

## <a name="operator-"></a> оператор-

Унарный оператор, который отнимает единицу от каждого элемента в valarray.

```cpp
valarray<Type> operator-() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, содержащий элементы операнда valarray после вычитания.

### <a name="example"></a>Пример

```cpp
// valarray_op_eminus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaMINUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaMINUS = -vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaMINUS [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).
```

## <a name="operator-_eq"></a> оператор-=

Поэлементно вычитает элементы указанного объекта valarray или значение типа элемента из операнда valarray.

```cpp
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, которое будет поэлементно вычитаться из операнда valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой разность операнда valarray и *правой*.

### <a name="example"></a>Пример

```cpp
// valarray_op_esub.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL -= vaR;
   cout << "The element-by-element result of "
        << "the difference is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
```

## <a name="op_div_eq"></a> оператор / =

Поэлементно делит операнд valarray на элементы указанного объекта valarray или на значение типа элемента.

```cpp
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, на которое будет поэлементно делиться операнд valarray.

### <a name="return-value"></a>Возвращаемое значение

Деления на объект valarray, элементы которого представляет собой частное от операнда valarray *правой*.

### <a name="example"></a>Пример

```cpp
// valarray_op_ediv.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL /= vaR;
   cout << "The element-by-element result of "
        << "the quotient is the"
        << endl << "valarray: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
valarray: ( inf -50 25 -16.6667 12.5 -10 ).
```

## <a name="op_eq"></a> оператор =

Присваивает элементы объекту valarray, значения которого указываются непосредственно, с помощью другого объекта valarray или с помощью функций slice_array, gslice_array, mask_array или indirect_array.

```cpp
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray, который необходимо скопировать в операнд valarray.

*Val*\
Значение, которое будет присвоено элементам операнда valarray.

*_Slicearray*\
Результат функции slice_array, который необходимо скопировать в операнд valarray.

*_Gslicearray*\
Результат функции gslice_array, который необходимо скопировать в операнд valarray.

*_Maskarray*\
Результат функции mask_array, который необходимо скопировать в операнд valarray.

*_Indarray*\
Результат функции indirect_array, который необходимо скопировать в операнд valarray.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор-член заменяет управляемую последовательность копией последовательности, управляемой *правой*.

Второй оператор-член аналогичен первому, но использует [декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

Третий оператор-член заменяет каждый элемент управляемой последовательности с копией *val*.

Остальные операторы-члены заменяют эти элементы контролируемой последовательности на их аргументы, которые создаются только оператором [operator[]](#op_at).

Если значение элемента в новой управляемой последовательности зависит от элемента в начальной управляемой последовательности, результат не определен.

### <a name="remarks"></a>Примечания

При изменении длины управляемой последовательности результат обычно не определен. Однако в этой реализации эффект ограничится только тем, что все указатели или ссылки на элементы в управляемой последовательности станут недействительными.

### <a name="example"></a>Пример

```cpp
// valarray_op_assign.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va [ i ] = i;
   for ( i = 0 ; i < 10 ; i+=1 )
      vaR [ i ] = 10 -  i;

   cout << "The operand valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   cout << "The operand valarray vaR is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << vaR [ i ];
   cout << endl;

   // Assigning vaR to va with the first member functon
   va = vaR;
   cout << "The reassigned valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   // Assigning elements of value 10 to va
   // with the second member functon
   va = 10;
   cout << "The reassigned valarray va is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << va [ i ];
   cout << endl;
}
```

```Output
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10

```

## <a name="op_at"></a> оператор]

Возвращает ссылку на элемент или его значение по указанному индексу или для определенного подмножества.

```cpp
Type& operator[](size_t _Off);

slice_array<Type> operator[](slice _Slicearray);

gslice_array<Type> operator[](const gslice& _Gslicearray);

mask_array<Type> operator[](const valarray<bool>& _Boolarray);

indirect_array<Type> operator[](const valarray<size_t>& _Indarray);

Type operator[](size_t _Off) const;

valarray<Type> operator[](slice _Slice) const;

valarray<Type> operator[](const gslice& _Gslicearray) const;

valarray<Type> operator[](const valarray<bool>& _Boolarray) const;

valarray<Type> operator[](const valarray<size_t>& _Indarray) const;
```

### <a name="parameters"></a>Параметры

*_Off*\
Индекс элемента, которому будет присвоено значение.

*_Slicearray*\
Результат функции slice_array для объекта valarray, который содержит подмножество, которое будет выбрано или возвращено в новый объект valarray.

*_Gslicearray*\
Результат функции gslice_array для объекта valarray, который содержит подмножество, которое будет выбрано или возвращено в новый объект valarray.

*_Boolarray*\
Результат функции bool_array для объекта valarray, который содержит подмножество, которое будет выбрано или возвращено в новый объект valarray.

*_Indarray*\
Результат функции indirect_array для объекта valarray, который содержит подмножество, которое будет выбрано или возвращено в новый объект valarray.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент или его значение для указанного индекса или подмножества.

### <a name="remarks"></a>Примечания

Оператор-член перегружен, чтобы предоставить несколько способов выбора последовательности элементов из тех, которые управляются  <strong>\*это</strong>. Первая группа из пяти операторов-членов совместно с различными перегрузками [operator=](#op_eq) (и другими операторами присваивания) позволяют осуществить выборочную замену (фрагментирование) в управляемой последовательности. Выбранные элементы должны существовать.

При компиляции с флагом [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу за пределами объекта valarray.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

См. примеры объявления и использования оператора в разделах [slice::slice](../standard-library/slice-class.md#slice) и [gslice::gslice](../standard-library/gslice-class.md#gslice).

## <a name="op_xor_eq"></a> оператор ^ =

Вычисляет поэлементное исключающее **ИЛИ** для массива с указанным valarray или для значения типа элемента.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, для которого будет выполняться операция логического исключающего **ИЛИ** с операндом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой, исключающее логическое **XOR** операнда valarray и *правой*.

### <a name="remarks"></a>Примечания

Исключающего логического или, называемая также **XOR**, имеет следующую семантику: Имея элемента *e*1 и *e*2, *e*1 **XOR** *e*2 — **true** Если только один из элементов имеет значение true; **false** Если оба элемента имеют значение false, или если выполняются оба элемента.

### <a name="example"></a>Пример

```cpp
// valarray_op_exor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;

    valarray<int> vaL ( 10 ), vaR ( 10 );
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

    cout << "The initial operand valarray is:  ( ";
        for (i = 0 ; i < 10 ; i++ )
            cout << vaL [ i ] << " ";
    cout << ")." << endl;

    cout << "The  right valarray is: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaR [ i ] << " ";
    cout << ")." << endl;

    vaL ^= vaR;
    cout << "The element-by-element result of "
        << "the bitwise XOR operator^= is the"
        << endl << "valarray: ( ";
        for (i = 0 ; i < 10 ; i++ )
            cout << vaL [ i ] << " ";
    cout << ")." << endl;
}
```

```Output
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^= is the
valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
```

## <a name="op_or_eq"></a> оператор&#124;=

Вычисляет побитовое `OR` между элементами массива и соответствующими элементами указанного объекта valarray или значением типа элемента.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект valarray или значение типа элемента, для которого будет выполняться операция побитового `OR` с операндом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляет собой побитовое `OR` операнда valarray с *правой*.

### <a name="remarks"></a>Примечания

Операцию побитового может использоваться только для управления bits в **char** и **int** типы данных и их разновидностями и не на **float**, **двойные**, **longdouble**, **void**, **bool**, или другими, более сложными типами данных.

Побитовое `OR` имеет ту же таблицу истинности, что и логическое `OR`, но применяется к типам данных на уровне отдельных битов. Если взять биты *b*1 и *b*2, то*b*1 `OR` *b*2 имеет значение **true**, если хотя бы один из битов имеет значение true, и имеет значение **false**, если оба бита имеют значение false.

### <a name="example"></a>Пример

```cpp
// valarray_class_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
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

   cout << "The initial operand valarray is:"
        << endl << "( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is:"
        << endl << "( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL |= vaR;
   cout << "The element-by-element result of "
        << "the logical OR"
        << endl << "operator|= is the valarray:"
        << endl << "( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial operand valarray is:
( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is:
( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the logical OR
operator|= is the valarray:
( 1 0 1 3 3 4 7 6 7 9 ).
```

## <a name="op_dtor"></a> оператор ~

Унарный оператор, который получает побитовое `NOT` для каждого элемента в объекте valarray.

```cpp
valarray<Type> operator~() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект valarray из логических значений, которые являются побитового `NOT` соответствующего элемента операнда valarray.

### <a name="remarks"></a>Примечания

Операцию побитового может использоваться только для управления bits в **char** и **int** типы данных и их разновидностями и не на **float**, **двойные**, **longdouble**, **void**, **bool** или другими, более сложными типами данных.

Побитовое `NOT` имеет ту же таблицу истинности, что и логическое `NOT`, но применяется к типам данных на уровне отдельных битов. Если взять бит *b*, то ~*b* имеет значение true если бит *b* имеет значение false, и имеет значение false, если бит *b* имеет значение true. Логический оператор **НЕ** [operator!](#op_not) применяется на уровне элемента, интерпретируя все ненулевые значения как **true**. Результатом является объект valarray из логических значений. Побитовое `NOToperator~`, напротив, может привести в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_bitnot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;

    valarray<unsigned short int> vaL1 ( 10 );
    valarray<unsigned short int> vaNOT1 ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        vaL1 [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        vaL1 [ i ] =  5*i;

    cout << "The initial valarray <unsigned short int> is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaL1 [ i ] << " ";
    cout << ")." << endl;

    vaNOT1 = ~vaL1;
    cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT1 [ i ] << " ";
    cout << ")." << endl << endl;

    valarray<int> vaL2 ( 10 );
    valarray<int> vaNOT2 ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        vaL2 [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        vaL2 [ i ] =  -2 * i;

    cout << "The initial valarray <int> is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaL2 [ i ] << " ";
    cout << ")." << endl;

    vaNOT2 = ~vaL2;
    cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT2 [ i ] << " ";
    cout << ")." << endl;

    // The negative numbers are represented using
    // the two's complement approach, so adding one
    // to the flipped bits returns the negative elements
    vaNOT2 = vaNOT2 + 1;
    cout << "The element-by-element result of "
        << "adding one"
        << endl << "is the negative of the "
        << "original elements the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT2 [ i ] << " ";
    cout << ")." << endl;
}
```

```Output
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).

The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).
The element-by-element result of adding one
is the negative of the original elements the
valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).
```

## <a name="resize"></a> Изменение размера

Изменяет число элементов в объекте valarray на заданное.

```cpp
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,
    const Type val);
```

### <a name="parameters"></a>Параметры

*_Newsize*\
Число элементов в объекте valarray с измененным размером.

*Val*\
Значение, присваиваемое элементам объекта valarray с измененным размером.

### <a name="remarks"></a>Примечания

Первая функция-член инициализирует элементы с помощью их конструктора по умолчанию.

Все указатели и ссылки на элементы в управляемой последовательности становятся недействительными.

### <a name="example"></a>Пример

В следующем примере иллюстрируется использование функции-члена valarray::resize.

```cpp
// valarray_resize.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, sizeNew;

    valarray<int> va1(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;

    cout << "The valarray contains ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray is: "
         << size1  << "." <<endl << endl;

    va1.resize(15, 10);

    cout << "The valarray contains ( ";
        for (i = 0; i < 15; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;
    sizeNew = va1.size();
    cout << "The number of elements in the resized valarray is: "
         << sizeNew  << "." <<endl << endl;
}
```

```Output
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray is: 10.

The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).
The number of elements in the resized valarray is: 15.
```

## <a name="shift"></a> SHIFT

Смещает все элементы в valarray на заданное число позиций.

```cpp
valarray<Type> shift(int count) const;
```

### <a name="parameters"></a>Параметры

*число*\
Количество позиций, на которые элементы будут сдвинуты вперед.

### <a name="return-value"></a>Возвращаемое значение

Новый объект valarray, в которой все элементы которого были перемещены *число* позиций к началу valarray, влево по отношению к их положения в операнде valarray.

### <a name="remarks"></a>Примечания

Положительное значение *число* перемещает элементы слева *число* позиций с заполнением ноль.

Отрицательное значение *число* сдвигает вправо элементы *число* позиций с заполнением ноль.

### <a name="example"></a>Пример

```cpp
// valarray_shift.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va1 ( 10 ), va2 ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va1 [ i ] =  i;
   for ( i = 0 ; i < 10 ; i += 1 )
      va2 [ i ] = 10 -  i;

   cout << "The operand valarray va1(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   // A positive parameter shifts elements left
   va1 = va1.shift ( 4 );
   cout << "The shifted valarray va1 is: va1.shift (4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   cout << "The operand valarray va2(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;

   // A negative parameter shifts elements right
   va2 = va2.shift ( - 4 );
   cout << "The shifted valarray va2 is: va2.shift (-4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).
```

## <a name="size"></a> Размер

Определяет число элементов в объекте valarray.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в операнде valarray.

### <a name="example"></a>Пример

В следующем примере иллюстрируется использование функции-члена valarray::size.

```cpp
// valarray_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, size2;

    valarray<int> va1(10), va2(12);
    for (i = 0; i < 10; i += 1)
        va1[i] =  i;
    for (i = 0; i < 10; i += 1)
        va2[i] =  i;

    cout << "The operand valarray va1(10) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray va1 is: va1.size = "
         << size1  << "." <<endl << endl;

    cout << "The operand valarray va2(12) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;

    size2 = va2.size();
    cout << "The number of elements in the valarray va2 is: va2.size = "
         << size2  << "." << endl << endl;

    // Initializing two more elements to va2
    va2[10] = 10;
    va2[11] = 11;
    cout << "After initializing two more elements,\n"
         << "the operand valarray va2(12) is now: ( ";
        for (i = 0; i < 12; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;
    cout << "The number of elements in the valarray va2 is still: "
         << size2  << "." << endl;
}
```

```Output
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va1 is: va1.size = 10.

The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va2 is: va2.size = 12.

After initializing two more elements,
the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).
The number of elements in the valarray va2 is still: 12.
```

## <a name="sum"></a> Сумма

Определяет сумму всех элементов в объекте valarray с ненулевой длиной.

```cpp
Type sum() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сумма элементов для операнда valarray.

### <a name="remarks"></a>Примечания

Если длина больше единицы, функция-член добавляет значения к сумме, применяя `operator+=` между парами элементов класса `Type`, какой оператор, следовательно, необходимо предоставить для элементов типа `Type`.

### <a name="example"></a>Пример

```cpp
// valarray_sum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    int sumva = 0;

    valarray<int> va ( 10 );
    for ( i = 0 ; i < 10 ; i+=1 )
        va [ i ] =  i;

    cout << "The operand valarray va (10) is: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;

    sumva = va.sum ( );
    cout << "The sum of elements in the valarray is: "
        << sumva  << "." <<endl;
}
```

```Output
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The sum of elements in the valarray is: 45.
```

## <a name="swap"></a> Swap

Выполняет обмен элементами между двумя объектами `valarray`.

```cpp
void swap(valarray& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект `valarray`, предоставляющий элементы, которые следует поменять местами.

### <a name="remarks"></a>Примечания

Функция-член меняет местами управляемые последовательности между `*this` и *правой*. Она делает это в константном времени, не создает исключения и не делает недействительными ссылки, указатели или итераторы, которые указывают элементы в двух управляемых последовательностях.

## <a name="valarray"></a> valarray

Создает объект valarray указанного размера или с элементами, имеющими указанное значение, либо в качестве копии другого объекта valarray или подмножества другого объекта valarray.

```cpp
valarray();

explicit valarray(
    size_t Count);

valarray(
    const Type& Val,
    size_t Count);

valarray(
    const Type* Ptr,
    size_t Count);

valarray(
    const valarray<Type>& Right);

valarray(
    const slice_array<Type>& SliceArray);

valarray(
    const gslice_array<Type>& GsliceArray);

valarray(
    const mask_array<Type>& MaskArray);

valarray(
    const indirect_array<Type>& IndArray);

valarray(
    valarray<Type>&& Right);

valarray(
    initializer_list<Type> IList);
```

### <a name="parameters"></a>Параметры

*число*\
Число элементов в объекте valarray.

*Val*\
Значение, которое будет использоваться при инициализации элементов в объекте valarray.

*PTR*\
Указатель на значения, которые будут использоваться при инициализации элементов в объекте valarray.

*Правильно*\
Существующий объект valarray для инициализации нового объекта valarray.

*SliceArray*\
Функция slice_array, значения элементов которой будут использоваться при инициализации создаваемого объекта valarray.

*GsliceArray*\
Функция gslice_array, значения элементов которой будут использоваться при инициализации создаваемого объекта valarray.

*MaskArray*\
Функция mask_array, значения элементов которой будут использоваться при инициализации создаваемого объекта valarray.

*IndArray*\
Функция indirect_array, значения элементов которой будут использоваться при инициализации создаваемого объекта valarray.

*IList*\
Объект initializer_list, содержащий копируемые элементы.

### <a name="remarks"></a>Примечания

Первый конструктор (конструктор по умолчанию) инициализирует объект, записывая в него пустой массив. Следующие три конструктора каждой инициализации объекта в массив *число* элементы следующим образом:

- Для явного `valarray(size_t Count)` каждый элемент инициализируется с помощью конструктора по умолчанию.

- Для `valarray(const Type& Val, Count)`, каждый элемент инициализируется с *Val*.

- Для `valarray(const Type* Ptr, Count)` элемент в позиции `I` инициализируется значением `Ptr`[ `I`].

Каждый из оставшихся конструкторов инициализирует объект, записывая в него объект valarray\<Type>, определяемый подмножеством, указанным в аргументе.

Последний конструктор аналогичен предпоследнему, но использует [декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Пример

```cpp
// valarray_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    // The second member function
    valarray<int> va(10);
    for (auto i : va){
        va[i] = 2 * (i + 1);
    }

    cout << "The operand valarray va is:\n(";
    for (auto i : va) {
        cout << " " << va[i];
    }
    cout << " )" << endl;

    slice Slice(2, 4, 3);

    // The fifth member function
    valarray<int> vaSlice = va[Slice];

    cout << "The new valarray initialized from the slice is vaSlice =\n"
        << "va[slice( 2, 4, 3)] = (";
    for (int i = 0; i < 3; i++) {
        cout << " " << vaSlice[i];
    }
    cout << " )" << endl;

    valarray<int> va2{{ 1, 2, 3, 4 }};
    for (auto& v : va2) {
        cout << v << " ";
    }
    cout << endl;
}
```

```Output
The operand valarray va is:
( 0 2 2 2 2 2 2 2 2 2 )
The new valarray initialized from the slice is vaSlice =
va[slice( 2, 4, 3)] = ( 0 0 0 )
1 2 3 4
```

## <a name="value_type"></a> value_type

Тип, который представляет тип элемента, хранящегося в объекте valarray.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Type`.

### <a name="example"></a>Пример

```cpp
// valarray_value_type.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    valarray<int> va ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        va [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        va [ i ] =  -1;

    cout << "The initial operand valarray is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;

    // value_type declaration and initialization:
    valarray<int>::value_type Right = 10;

    cout << "The decalared value_type Right is: "
            << Right << endl;
    va *= Right;
    cout << "The resulting valarray is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;
}
```

```Output
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).
The decalared value_type Right is: 10
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).
```

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
