---
title: "Класс valarray | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "valarray"
  - "std.valarray"
  - "std::valarray"
  - "valarray/std::valarray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valarray - класс"
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс valarray
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона описывает объект, управляющий последовательностью элементов типа **типа** хранятся в виде массива, предназначены для выполнения математических операций высокоскоростной и оптимизация для производительности вычислений.  
  
## <a name="remarks"></a>Примечания  
 Класс является представлением математического понятия упорядоченного набора значений, а для элементов применяется последовательная нумерация, начиная с нуля. Класс описан как контейнер почти так, как он поддерживает некоторые, но не все возможности, первоклассная контейнеры последовательности, такие как [вектор](vector%20Class.md), поддержки. Он имеет два важных отличия от класса шаблона vector:  
  
-   Он определяет множество арифметические операции между соответствующие элементы **valarray \< тип>** объекты одного типа и длины, таких как *xarr* = cos ( *yarr*) + sin ( *zarr*).  
  
-   Он определяет ряд интересных способов индекс **valarray \< тип>** объекта путем перегрузки [оператор &#91; &#93;](#valarray__operator_at).  
  
 Объект класса **типа**:  
  
-   Имеет открытый конструктор по умолчанию, деструктор, конструктор копии и оператор присваивания, работающие обычным образом.  
  
-   При необходимости определяет арифметические операторы и математические функции, определенные для типов с плавающей запятой и работающие обычным образом.  
  
 В частности, между конструкцией копирования и конструкцией по умолчанию, за которыми следует присваивание, не может существовать даже малейших отличий. Ни одна из операций на объектах класса **тип** могут вызывать исключения.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[valarray](#valarray__valarray)|Создает `valarray` определенного размера или с элементами, имеющими указанное значение, либо в качестве копии другого `valarray` или подмножества другого `valarray`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#valarray__value_type)|Тип, представляющий тип элемента, хранящегося в `valarray`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[Применение](#valarray__apply)|Применяет заданную функцию для каждого элемента объекта `valarray`.|  
|[cshift](#valarray__cshift)|Циклически смещает все элементы в `valarray` на заданное число позиций.|  
|[освободить](#valarray__free)|Освобождает память, используемую `valarray`.|  
|[max](#valarray__max)|Находит наибольший элемент в `valarray`.|  
|[мин.](#valarray__min)|Находит наименьший элемент в `valarray`.|  
|[Изменение размеров](#valarray__resize)|Изменяет количество элементов в `valarray` на заданное число, при необходимости добавляя или удаляя элементы.|  
|[SHIFT](#valarray__shift)|Смещает все элементы в `valarray` на заданное число позиций.|  
|[размер](#valarray__size)|Находит количество элементов в `valarray`.|  
|[Сумма](#valarray__sum)|Определяет сумму всех элементов в `valarray` с ненулевой длиной.|  
|[Переключение](#valarray__swap)||  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор!](#valarray__operator_not)|Унарный оператор, который получает логические значения `NOT` каждого элемента в `valarray`.|  
|[оператор % =](#valarray__operator_mod_eq)|Получает остаток от поэлементного деления элементов массива на указанный `valarray` или на значение типа элемента.|  
|[оператор & =](#valarray__operator_amp__eq)|Получает битовый `AND` элементов в массиве при помощи соответствующих элементов в указанном `valarray` или при помощи значения типа элемента.|  
|[оператор >> =](#valarray__operator_gt__gt__eq)|Сдвигает вправо биты для каждого элемента операнда `valarray` на указанное число позиций или на поэлементную сумму, указанную вторым `valarray`.|  
|[оператор << =](#valarray__operator_lt__lt__eq)|Сдвигает влево биты для каждого элемента операнда `valarray` на указанное число позиций или на поэлементную сумму, указанную вторым `valarray`.|  
|[оператор * =](#valarray__operator_star_eq)|Поэлементно умножает элементы указанного `valarray` или значение типа элемента на операнд `valarray`.|  
|[оператор +](#valarray__operator_add)|Унарный оператор, который прибавляет единицу к каждому элементу в `valarray`.|  
|[оператор +=](#valarray__operator_add_eq)|Поэлементно прибавляет элементы указанного `valarray` или значение типа элемента к операнду `valarray`.|  
|[оператор-](#valarray__operator-)|Унарный оператор, который отнимает единицу от каждого элемента в `valarray`.|  
|[оператор-=](#valarray__operator-_eq)|Поэлементно вычитает элементы указанного `valarray` или значение типа элемента из операнда `valarray`.|  
|[оператор / =](#valarray__operator__eq)|Поэлементно делит операнд `valarray` на элементы указанного `valarray` или значение типа элемента.|  
|[оператор =](#valarray__operator_eq)|Назначает элементы для `valarray`, значения которых задаются либо непосредственно или как часть другого `valarray`, либо с помощью `slice_array`, `gslice_array`, `mask_array` или `indirect_array`.|  
|[оператор &#91; &#93;](#valarray__operator_at)|Возвращает ссылку на элемент или его значение по указанному индексу или для определенного подмножества.|  
|[оператор ^ =](#valarray__operator_xor_eq)|Получает учитывающего элементы исключающего логического или оператор ( `XOR`) массива с указанным valarray или значение типа элемента.|  
|[оператор &#124; =](#valarray__operator_or_eq)|Получает битовый `OR` элементов в массиве при помощи соответствующих элементов в указанном `valarray` или при помощи значения типа элемента.|  
|[оператор ~](#valarray__operator_dtor)|Унарный оператор, который получает битовые значения `NOT` каждого элемента в `valarray`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< valarray>  
  
 **Пространство имен:** std  
  
##  <a name="a-namevalarrayapplya-valarrayapply"></a><a name="valarray__apply"></a>  valarray::Apply  
 Применяет заданную функцию к каждому элементу в объекте valarray.  
  
```  
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```  
  
### <a name="parameters"></a>Параметры  
 *_Func(Type)*  
 Объект функции для применения к каждому элементу операнде valarray.  
  
 *_Func(const Type&)*  
 Объект функции для const для применения к каждому элементу операнде valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого были `_Func` element-wise применяется к элементам операнде valarray.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает объект класса [valarray](../standard-library/valarray-class.md)**\< тип>**, длины [размер](#valarray__size), каждый из которых элементов `I` — **func**(( **\*это**) [ `I`]).  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )  
The element-by-element result of applying MyApplyFunc to vaR is the  
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )  
*\  
```  
  
##  <a name="a-namevalarraycshifta-valarraycshift"></a><a name="valarray__cshift"></a>  valarray::cshift  
 Циклической смещает все элементы в объекте valarray на заданное число позиций.  
  
```  
valarray<Type> cshift(int count) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` count`  
 Количество разрядов элементы должны быть сдвинуты вперед.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый valarray, в которой все элементы будут перемещены ` count` позиций циклической ближе к началу valarray, влево, по отношению к их позиции в операнде valarray.  
  
### <a name="remarks"></a>Примечания  
 Положительное значение ` count` перемещает элементы циклической слева ` count` помещает.  
  
 Отрицательное значение ` count` перемещает элементы циклической правой ` count` помещает.  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)  
The cyclically shifted valarray va1 is:  
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)  
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)  
The cyclically shifted valarray va2 is:  
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)  
*\  
```  
  
##  <a name="a-namevalarrayfreea-valarrayfree"></a><a name="valarray__free"></a>  valarray::Free  
 Освобождает память, занятая valarray.  
  
```  
void free();
```  
  
### <a name="remarks"></a>Примечания  
 Это нестандартное функция эквивалентна назначение пустой valarray. Пример:  
  
```  
valarray<T> v;  
v = valarray<T>();

// equivalent to v.free()  
```  
  
##  <a name="a-namevalarraymaxa-valarraymax"></a><a name="valarray__max"></a>  valarray::max  
 Находит самого большого элемента в объекте valarray.  
  
```  
Type max() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное значение элементов в операнде valarray.  
  
### <a name="remarks"></a>Примечания  
 Функция-член сравнивает значения, применяя **оператор \<** или **оператор >** между парами элементов класса **типа**, необходимо предоставить для какие операторы для элемента **типа**.  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).  
The largest element in the valarray is: 13.  
*\  
```  
  
##  <a name="a-namevalarraymina-valarraymin"></a><a name="valarray__min"></a>  valarray::Min  
 Находит наименьший элемент в объекте valarray.  
  
```  
Type min() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минимальное значение элементов в операнде valarray.  
  
### <a name="remarks"></a>Примечания  
 Функция-член сравнивает значения, применяя **оператор \<** или **оператор >** между парами элементов класса **типа**, необходимо предоставить для какие операторы для элемента **типа**.  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).  
The smallest element in the valarray is: -9.  
*\  
```  
  
##  <a name="a-namevalarrayoperatornota-valarrayoperator"></a><a name="valarray__operator_not"></a>  valarray::operator!  
 Унарный оператор, который получает логический **НЕ** значения каждого элемента в объекте valarray.  
  
```  
valarray<bool> operator!() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray логические значения, которые являются отрицательными значениями элемент значения операнда valarray.  
  
### <a name="remarks"></a>Примечания  
 Логическая операция **НЕ** инвертирует элементы, так как он преобразует все нули в тех и считает все ненулевые значения, как те и преобразует их в нули. Возвращаемый valarray логических значений имеет того же размера, что операнд valarray.  
  
 Существует также битовую **НЕ**[valarray::operator ~](#valarray__operator_dtor) инвертирует на уровне отдельных битов в двоичном представлении `char` и `int` элементы valarray.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the logical NOT operator! is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The element-by-element result of the logical NOT operator! is the  
 valarray: ( 1 1 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatormodeqa-valarrayoperator"></a><a name="valarray__operator_mod_eq"></a>  valarray::operator % =  
 Возвращает остаток от деления element-wise элементы массива, заданного valarray либо значение типа элемента.  
  
```  
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray или значение типа элемента идентична операнде valarray, разделить, element-wise, valarray операнда.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются остаток от деления учитывающего элементы операнд valarray по ` right.`  
  
### <a name="example"></a>Пример  
  
```  
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
        << "division is the\n valarray: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 53 -67 53 -67 53 -67 ).  
The initial  right valarray is: ( 1 4 7 10 13 16 ).  
The remainders from the element-by-element division is the  
 valarray: ( 0 -3 4 -7 1 -3 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorampeqa-valarrayoperatoramp"></a><a name="valarray__operator_amp__eq"></a>  valarray::operator&amp;=  
 Получает побитового **AND** элементов в массиве, с соответствующими элементами указанного valarray или значение типа элемента.  
  
```  
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray или значение типа элемента идентична операнде valarray, которые будут объединены, учитывающего элементы по логическим **и** в операнде valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются учитывающего элементы логического **и** из операнде valarray по ` right.`  
  
### <a name="remarks"></a>Примечания  
 Побитовая операция может использоваться только для управления bits в `char` и `int` типы данных и вариантов и не на **float**, **двойные**, **longdouble**, `void`, `bool`, или других, более сложных типов данных.  
  
 Побитовое и имеет же таблица истинности как логический **и** но относится к типам данных на уровне отдельных битов. Учитывая bits *b*1 и *b*2, *b*1 **и** *b*2 **true** Если оба бита равны true; **false** Если хотя бы одно значение false.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the logical AND operator&= is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the logical AND operator&= is the  
 valarray: ( 0 0 0 2 0 4 0 6 0 8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorgtgteqa-valarrayoperatorgtgt"></a><a name="valarray__operator_gt__gt__eq"></a>  valarray::operator&gt;&gt;=  
 Сдвиг вправо бит для каждого элемента указанного числа позиций, или на сумму учитывающего элементы, заданные второй valarray операнда valarray.  
  
```  
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Значение, указывающее количество сдвига вправо или valarray, элементы которого указывают учитывающего элементы сдвига вправо.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого были сдвигаются вправо на величину, указанную в ` right`.  
  
### <a name="remarks"></a>Примечания  
 Числа со знаком имеют свои символы сохраняются.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the right shift is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the right shift is the  
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorltlteqa-valarrayoperatorltlt"></a><a name="valarray__operator_lt__lt__eq"></a>  valarray::operator&lt;&lt;=  
 Сдвиг влево бит для каждого элемента указанного числа позиций, или на сумму учитывающего элементы, заданные второй valarray операнда valarray.  
  
```  
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Значение, указывающее количество сдвиг влево или valarray, элементы которого указывают учитывающего элементы сдвига влево.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого изменились влево на величину, указанную в ` right`.  
  
### <a name="remarks"></a>Примечания  
 Числа со знаком имеют свои символы сохраняются.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the left shift\n on the operand array is the valarray:\n ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the left shift  
 on the operand array is the valarray:  
 ( 1 -2 4 -8 16 -32 64 -128 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorstareqa-valarrayoperator"></a><a name="valarray__operator_star_eq"></a>  valarray::operator * =  
 Умножает элементы указанного valarray или значение типа элемента, element-wise, чтобы операнд valarray.  
  
```  
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray или значение типа элемента идентичен valarray операнд, который является умножение element-wise, операнд valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются учитывающего элементы произведения операнд valarray и ` right.`  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the multiplication is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the multiplication is the  
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoradda-valarrayoperator"></a><a name="valarray__operator_add"></a>  valarray::operator +  
 Унарный оператор, который применяется к каждому элементу в объекте valarray знак «плюс».  
  
```  
valarray<Type> operator+() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются операнд массива, а также.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaPLUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoraddeqa-valarrayoperator"></a><a name="valarray__operator_add_eq"></a>  valarray::operator +=  
 Добавляет элементы указанной valarray или значение типа элемента, element-wise, valarray операнда.  
  
```  
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray или значение типа элемента идентичен valarray операнд, который должен быть добавлен, element-wise, в операнде valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются сумму учитывающего элементы операнд valarray и ` right.`  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the sum is the\n valarray: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the sum is the  
 valarray: ( 2 0 4 2 6 4 8 6 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperator-a-valarrayoperator-"></a><a name="valarray__operator-"></a>  valarray::operator-  
 Унарный оператор, который применяется к каждому элементу в объекте valarray минус.  
  
```  
valarray<Type> operator-() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются те операнд массива минус.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaMINUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperator-eqa-valarrayoperator-"></a><a name="valarray__operator-_eq"></a>  valarray::operator-=  
 Вычитает элементы указанного valarray или значение типа элемента, element-wise, из операнд valarray.  
  
```  
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray или значение типа элемента идентична операнде valarray, которое, element-wise, вычитается из операнде valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются учитывающего элементы разница в операнде valarray и ` right.`  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the difference is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the difference is the  
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoreqa-valarrayoperator"></a><a name="valarray__operator__eq"></a>  valarray::operator / =  
 Делит операнд valarray element-wise элементы указанного valarray или значение типа элемента.  
  
```  
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray или значение типа элемента идентична операнде valarray, разделить, element-wise, valarray операнда.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются учитывающего элементы частное операнд valarray, разделенное на ` right.`  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the quotient is the\n valarray: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 100 -100 100 -100 100 -100 ).  
The initial Right valarray is: ( 0 2 4 6 8 10 ).  
The element-by-element result of the quotient is the  
 valarray: ( 1.#INF -50 25 -16.6667 12.5 -10 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoreqa-valarrayoperator"></a><a name="valarray__operator_eq"></a>  valarray::operator =  
 Назначает элементы, значения которых указываются непосредственно или в составе некоторых других valarray или slice_array, gslice_array, mask_array или indirect_array valarray.  
  
```  
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray необходимо скопировать в операнде valarray.  
  
 ` val`  
 Значение, присваиваемое элементы операнде valarray.  
  
 `_Slicearray`  
 Slice_array необходимо скопировать в операнде valarray.  
  
 `_Gslicearray`  
 Gslice_array необходимо скопировать в операнде valarray.  
  
 `_Maskarray`  
 Mask_array необходимо скопировать в операнде valarray.  
  
 `_Indarray`  
 Indirect_array необходимо скопировать в операнде valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заменяет первый оператор элемент управляемой последовательности копию последовательности, контролируемой ` right`.  
  
 Второй оператор член является таким же, как первый, но с [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Третий оператор член заменяет каждый элемент управляемой последовательности с копией ` val`.  
  
 Остальные операторы членам заменить эти элементы по их аргументы, которые создаются только в управляемой последовательности [оператор &#91; &#93;](#valarray__operator_at).  
  
 Если значение элемента в последовательности замены управлять зависит от элемента в управляемой последовательности начальной, результат не определен.  
  
### <a name="remarks"></a>Примечания  
 При изменении длины управляемой последовательности, результат обычно не определено. В этой реализации Однако результат является просто сделать недействительными все указатели или ссылки на элементы в управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9  
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10  
*\  
```  
  
##  <a name="a-namevalarrayoperatorata-valarrayoperator"></a><a name="valarray__operator_at"></a>  valarray::operator]  
 Возвращает ссылку на элемент или его значение по указанному индексу или для определенного подмножества.  
  
```  
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
 `_Off`  
 Индекс элемента, который требуется присвоить значение.  
  
 `_Slicearray`  
 Slice_array из valarray, указывающее подмножество был выбран или возвращены новые valarray.  
  
 `_Gslicearray`  
 Gslice_array из valarray, указывающее подмножество был выбран или возвращены новые valarray.  
  
 *_Boolarray*  
 Bool_array из valarray, указывающее подмножество был выбран или возвращены новые valarray.  
  
 `_Indarray`  
 Indirect_array valarray, указывающее подмножество был выбран или возвращены новые valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент или его значение по указанному индексу или определенному подмножеству.  
  
### <a name="remarks"></a>Примечания  
 Оператор член перегружен, чтобы предоставляют несколько способов выбора последовательности элементов из тех, которые управляются *\****это**. Первая группа операторов пять член работают совместно с помощью перегрузок [оператор =](#valarray__operator_eq) (и другие операторы назначения) чтобы разрешить выборочной замены (Фрагментирование) управляемой последовательности. Должен существовать выбранных элементов.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения, при попытке доступа к элементу за пределами valarray.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  Примеры для [slice::slice](../Topic/slice%20Class.md#slice__slice) и [gslice::gslice](../Topic/gslice%20Class.md#gslice__gslice) пример того, как объявить и использовать оператор.  
  
##  <a name="a-namevalarrayoperatorxoreqa-valarrayoperator"></a><a name="valarray__operator_xor_eq"></a>  valarray::operator ^ =  
 Получает учитывающего элементы исключающего логического или оператор ( **XOR**) массива с указанным valarray или значение типа элемента.  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Значение типа элемента идентична операнде valarray, которые будут объединены, учитывающего элементы, логическое исключающее или valarray **XOR** с операнде valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются логической монопольная учитывающего элементы, **XOR** из операнд valarray и ` right.`  
  
### <a name="remarks"></a>Примечания  
 Исключающего логического или, известный как **XOR**, имеет следующую семантику: определенные элементы *e*1 и *e*2, *e*1 **XOR** *e*2 **true** Если только один из элементов имеет значение true; **false** Если оба элемента имеют значение false или если выполняются оба элемента.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the bitwise XOR operator^= is the\n valarray: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the bitwise XOR operator^= is the  
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatororeqa-valarrayoperator124"></a><a name="valarray__operator_or_eq"></a>  valarray::operator &#124; =  
 Получает побитового `OR` элементов в массиве, с соответствующими элементами указанного valarray или значение типа элемента.  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Valarray или значение типа элемента идентична операнде valarray, которые будут объединены, учитывающего элементы с битовой `OR` с операнде valarray.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray, элементы которого являются учитывающего элементы побитового `OR` из операнде valarray по ` right.`  
  
### <a name="remarks"></a>Примечания  
 Побитовая операция может использоваться только для управления bits в `char` и `int` типы данных и вариантов и не на **float**, **двойные**, **longdouble**, `void`, `bool`, или других, более сложных типов данных.  
  
 Битовые `OR` же таблица истинности как логический `OR` но относится к типам данных на уровне отдельных битов. Учитывая bits *b*1 и *b*2, *b*1 `OR` *b*2 **true** Если по крайней мере один из битов равно true; **false** Если оба бита равны false.  
  
### <a name="example"></a>Пример  
  
```  
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
  
   cout << "The initial operand valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL |= vaR;  
   cout << "The element-by-element result of "  
        << "the logical OR\n operator|= is the valarray:\n ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  
 ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is:  
 ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the logical OR  
 operator|= is the valarray:  
 ( 1 0 1 3 3 4 7 6 7 9 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatordtora-valarrayoperator"></a><a name="valarray__operator_dtor"></a>  valarray::operator ~  
 Унарный оператор, который получает побитового **НЕ** значения каждого элемента в объекте valarray.  
  
```  
valarray<Type> operator~() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Valarray логических значений, которые являются битовые **НЕ** элемент значения операнда valarray.  
  
### <a name="remarks"></a>Примечания  
 Побитовая операция может использоваться только для управления bits в `char` и `int` типы данных и вариантов и не на **float**, **двойные**, **longdouble**, `void`, `bool` или других, более сложных типов данных.  
  
 Битовые **НЕ** же таблица истинности как логический **НЕ** но относится к типам данных на уровне отдельных битов. Учитывая бит *b*, ~ *b* имеет значение true, если *b* имеет значение false и значение false, если *b* имеет значение true. Логический **НЕ**[оператор!](#valarray__operator_not) применяется на уровне элемента, подсчет нулевых значений как **true**, и это является результатом valarray логических значений. Битовые **NOToperator ~**, напротив, может привести к valarray значения, отличного от 0 или 1, в зависимости от результата побитовой операции.  
  
### <a name="example"></a>Пример  
  
```  
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
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
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
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
  
   // The negative numbers are represented using  
   // the two's complement approach, so adding one  
   // to the flipped bits returns the negative elements  
   vaNOT2 = vaNOT2 + 1;  
   cout << "The element-by-element result of "  
        << "adding one\n is the negative of the "  
        << "original elements the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).  
  
The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).  
The element-by-element result of adding one  
 is the negative of the original elements the  
 valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).  
*\  
```  
  
##  <a name="a-namevalarrayresizea-valarrayresize"></a><a name="valarray__resize"></a>  valarray::Resize  
 Изменяет число элементов в объекте valarray на заданное.  
  
```  
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,   
    const Type val);
```  
  
### <a name="parameters"></a>Параметры  
 `_Newsize`  
 Число элементов в объекте valarray с измененным размером.  
  
 ` val`  
 Значение, присваиваемое элементам объекта valarray с измененным размером.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член инициализирует элементы с помощью их конструктора по умолчанию.  
  
 Все указатели и ссылки на элементы в управляемой последовательности становятся недействительными.  
  
### <a name="example"></a>Пример  
  В следующем примере иллюстрируется использование функции-члена valarray::resize.  
  
```  
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
\* Output:   
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray is: 10.  
  
The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).  
The number of elements in the resized valarray is: 15.  
*\  
```  
  
##  <a name="a-namevalarrayshifta-valarrayshift"></a><a name="valarray__shift"></a>  valarray::SHIFT  
 Смещает все элементы в объекте valarray указанного количества знаков.  
  
```  
valarray<Type> shift(int count) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` count`  
 Количество разрядов элементы должны быть сдвинуты вперед.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый valarray, в которой все элементы будут перемещены ` count` позиций ближе к началу valarray, влево, по отношению к их позиции в операнде valarray.  
  
### <a name="remarks"></a>Примечания  
 Положительное значение ` count` перемещает элементы слева ` count` помещает ноль заливки.  
  
 Отрицательное значение ` count` сдвигается вправо элементов ` count` помещает ноль заливки.  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).  
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).  
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).  
*\  
```  
  
##  <a name="a-namevalarraysizea-valarraysize"></a><a name="valarray__size"></a>  valarray::size  
 Определяет число элементов в объекте valarray.  
  
```  
size_t size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в операнде valarray.  
  
### <a name="example"></a>Пример  
  В следующем примере иллюстрируется использование функции-члена valarray::size.  
  
```  
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
    cout << "After initializing two more elements,\n "  
         << "the operand valarray va2(12) is now: ( ";  
        for (i = 0; i < 12; i++)  
            cout << va2[i] << " ";  
    cout << ")." << endl;  
    cout << "The number of elements in the valarray va2 is still: "  
         << size2  << "." << endl;  
}  
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va1 is: va1.size = 10.  
  
The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va2 is: va2.size = 12.  
  
After initializing two more elements,  
 the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).  
The number of elements in the valarray va2 is still: 12.  
*\  
```  
  
##  <a name="a-namevalarraysuma-valarraysum"></a><a name="valarray__sum"></a>  valarray::Sum  
 Определяет сумму всех элементов в объекте valarray ненулевую длину.  
  
```  
Type sum() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сумма элементов операнде valarray.  
  
### <a name="remarks"></a>Примечания  
 Если длина больше одного, функция-член добавляет значения суммы, применив `operator+=` между парами элементов класса **типа**, какой оператор таким образом, должен быть предоставлен для элементов типа **типа**.  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The sum of elements in the valarray is: 45.  
*\  
```  
  
##  <a name="a-namevalarrayswapa-valarrayswap"></a><a name="valarray__swap"></a>  valarray::Swap  
 Выполняет обмен элементами между двумя объектами `valarray`.  
  
```  
void swap(valarray& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|` right`|Объект `valarray`, предоставляющий элементы, которые следует поменять местами.|  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности между `*this` и ` right`. Она делает это в константном времени, не создает исключения и не делает недействительными ссылки, указатели или итераторы, которые указывают элементы в двух управляемых последовательностях.  
  
##  <a name="a-namevalarrayvalarraya-valarrayvalarray"></a><a name="valarray__valarray"></a>  valarray::valarray  
 Создает valarray, определенного размера или с элементами определенного значения, или как копию другой valarray или подмножество другой valarray.  
  
```  
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
 `Count`  
 Число элементов в valarray.  
  
 `Val`  
 Значение, которое необходимо использовать при инициализации элементов в объекте valarray.  
  
 `Ptr`  
 Указатель на значения, используемые для инициализации элементов в объекте valarray.  
  
 `Right`  
 Существующие valarray для инициализации нового valarray.  
  
 `SliceArray`  
 Slice_array, должны использоваться при инициализации элементов valarray конструируемого, значения которых элемент.  
  
 `GsliceArray`  
 Gslice_array, должны использоваться при инициализации элементов valarray конструируемого, значения которых элемент.  
  
 `MaskArray`  
 Mask_array, должны использоваться при инициализации элементов valarray конструируемого, значения которых элемент.  
  
 `IndArray`  
 Indirect_array, должны использоваться при инициализации элементов valarray конструируемого, значения которых элемент.  
  
 `IList`  
 Объект initializer_list, содержащий копируемые элементы.  
  
### <a name="remarks"></a>Примечания  
 Первый (по умолчанию) конструктор инициализирует объект пустой массив. Следующие три конструкторы каждой инициализации объекта в массив `Count` элементы следующим образом:  
  
-   Для явного `valarray(size_t Count)`, каждый элемент инициализируется с помощью конструктора по умолчанию.  
  
-   Для `valarray(const Type& Val, Count)`, каждый элемент инициализируется с `Val`.  
  
-   Для `valarray(const Type* Ptr, Count)`, элемент в позиции `I` инициализируется `Ptr`[ `I`].  
  
 Каждый оставшиеся конструктор инициализирует объект в объекте valarray \< тип> объекта определяется подмножество, указанной в аргументе.  
  
 Последний конструктор совпадает с рядом с последним, но с [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
### <a name="example"></a>Пример  
  
```  
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
  
    cout << "The new valarray initialized from the slice is vaSlice ="  
        << "\nva[slice( 2, 4, 3)] = (";  
    for (int i = 0; i < 3; i++) {  
        cout << " " << vaSlice[i];  
    }  
    cout << " )" << endl;  
  
    valarray<int> va2{{ 1, 2, 3, 4 }};  
    for (auto& v : va2){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
The operand valarray va is:( 0 2 2 2 2 2 2 2 2 2 )The new valarray initialized from the slice is vaSlice =va[slice( 2, 4, 3)] = ( 0 0 0 )1 2 3 4  
```  
  
##  <a name="a-namevalarrayvaluetypea-valarrayvaluetype"></a><a name="valarray__value_type"></a>  valarray::value_type  
 Тип, представляющий тип элементов, которые хранятся в объекте valarray.  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **типа**.  
  
### <a name="example"></a>Пример  
  
```  
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
\* Output:   
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).  
The decalared value_type Right is: 10  
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).  
*\  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

