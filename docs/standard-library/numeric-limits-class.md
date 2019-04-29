---
title: Класс numeric_limits
ms.date: 11/04/2016
f1_keywords:
- limits/std::numeric_limits
- limits/std::numeric_limits::denorm_min
- limits/std::numeric_limits::digits
- limits/std::numeric_limits::digits10
- limits/std::numeric_limits::epsilon
- limits/std::numeric_limits::has_denorm
- limits/std::numeric_limits::has_denorm_loss
- limits/std::numeric_limits::has_infinity
- limits/std::numeric_limits::has_quiet_NaN
- limits/std::numeric_limits::has_signaling_NaN
- limits/std::numeric_limits::infinity
- limits/std::numeric_limits::is_bounded
- limits/std::numeric_limits::is_exact
- limits/std::numeric_limits::is_iec559
- limits/std::numeric_limits::is_integer
- limits/std::numeric_limits::is_modulo
- limits/std::numeric_limits::is_signed
- limits/std::numeric_limits::is_specialized
- limits/std::numeric_limits::lowest
- limits/std::numeric_limits::max
- limits/std::numeric_limits::max_digits10
- limits/std::numeric_limits::max_exponent
- limits/std::numeric_limits::max_exponent10
- limits/std::numeric_limits::min
- limits/std::numeric_limits::min_exponent
- limits/std::numeric_limits::min_exponent10
- limits/std::numeric_limits::quiet_NaN
- limits/std::numeric_limits::radix
- limits/std::numeric_limits::round_error
- limits/std::numeric_limits::round_style
- limits/std::numeric_limits::signaling_NaN
- limits/std::numeric_limits::tinyness_before
- limits/std::numeric_limits::traps
helpviewer_keywords:
- std::numeric_limits [C++]
- std::numeric_limits [C++], denorm_min
- std::numeric_limits [C++], digits
- std::numeric_limits [C++], digits10
- std::numeric_limits [C++], epsilon
- std::numeric_limits [C++], has_denorm
- std::numeric_limits [C++], has_denorm_loss
- std::numeric_limits [C++], has_infinity
- std::numeric_limits [C++], has_quiet_NaN
- std::numeric_limits [C++], has_signaling_NaN
- std::numeric_limits [C++], infinity
- std::numeric_limits [C++], is_bounded
- std::numeric_limits [C++], is_exact
- std::numeric_limits [C++], is_iec559
- std::numeric_limits [C++], is_integer
- std::numeric_limits [C++], is_modulo
- std::numeric_limits [C++], is_signed
- std::numeric_limits [C++], is_specialized
- std::numeric_limits [C++], lowest
- std::numeric_limits [C++], max
- std::numeric_limits [C++], max_digits10
- std::numeric_limits [C++], max_exponent
- std::numeric_limits [C++], max_exponent10
- std::numeric_limits [C++], min
- std::numeric_limits [C++], min_exponent
- std::numeric_limits [C++], min_exponent10
- std::numeric_limits [C++], quiet_NaN
- std::numeric_limits [C++], radix
- std::numeric_limits [C++], round_error
- std::numeric_limits [C++], round_style
- std::numeric_limits [C++], signaling_NaN
- std::numeric_limits [C++], tinyness_before
- std::numeric_limits [C++], traps
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
ms.openlocfilehash: 861850f192281d64ef02ec4a241315c05cd3318f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371520"
---
# <a name="numericlimits-class"></a>Класс numeric_limits

Класс шаблона описывает арифметические свойства встроенных числовых типов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class numeric_limits
```

### <a name="parameters"></a>Параметры

*Type*<br/>
Базовый тип данных элемента, свойства которого проверяются, запрашиваются или устанавливаются.

## <a name="remarks"></a>Примечания

Заголовок определяет явные специализации для типов **wchar_t**, **bool**, **char**, **автоматический char**, **без знака char**, **короткие**, **unsigned short**, **int**, **unsigned int**, **долго**, **unsigned long**, **float**, **двойные**, **long double**, **длинное длинное**, **long long без знака**, **char16_t**, и **char32_t**. Для этих явных специализаций член [numeric_limits::is_specialized](#is_specialized) — **true**, а все соответствующие элементы имеют значимые значения. Программа может предоставлять дополнительные явные специализации. Большинство функций-членов класса описывают или проверяют возможные реализации **float**.

Для произвольной специализации у членов нет значимых значений. Объект-член, не имеющее смысл значение, сохраняет ноль (или **false**) и возвращает функция-член, которая не возвращает осмысленное значение `Type(0)`.

### <a name="static-functions-and-constants"></a>Статические функции и константы

|||
|-|-|
|[denorm_min](#denorm_min)|Возвращает наименьшее ненулевое денормализованное значение.|
|[digits](#digits)|Возвращает количество цифр основания системы счисления, которое тип может представлять без потери точности.|
|[digits10](#digits10)|Возвращает количество дробных десятичных цифр, которое тип может представлять без потери точности.|
|[epsilon](#epsilon)|Возвращает разницу между 1 и наименьшим значением больше 1, которое этот тип данных может представлять.|
|[has_denorm](#has_denorm)|Проверяет, допускает ли тип денормализованные значения.|
|[has_denorm_loss](#has_denorm_loss)|Проверяет, обнаружена ли потеря точности как потеря денормализации, а не неточный результат.|
|[has_infinity](#has_infinity)|Проверяет, может ли тип представлять положительную бесконечность.|
|[has_quiet_NaN](#has_quiet_nan)|Проверяет, может ли тип представлять "тихое" нечисло (NAN), которое является несигнализирующим.|
|[has_signaling_NaN](#has_signaling_nan)|Проверяет, может ли тип представлять сообщения об обнаружении нечисла (NAN).|
|[infinity](#infinity)|Представление положительной бесконечности для типа, если доступно.|
|[is_bounded](#is_bounded)|Проверяет, конечен ли набор значений, представляемый типом.|
|[is_exact](#is_exact)|Проверяет, не содержат ли вычисления с типом ошибок округления.|
|[is_iec559](#is_iec559)|Проверяет, соответствует ли тип стандартам IEC 559.|
|[is_integer](#is_integer)|Проверяет, может ли тип представлять целые числа.|
|[is_modulo](#is_modulo)|Проверяет, может ли тип представлять модуль.|
|[is_signed](#is_signed)|Проверяет, может ли тип представлять числа со знаком.|
|[is_specialized](#is_specialized)|Проверяет, задана ли для типа явная специализация в классе шаблона `numeric_limits`.|
|[lowest](#lowest)|Возвращает наибольшее отрицательное конечное значение.|
|[max](#max)|Возвращает максимальное конечное значение типа.|
|[max_digits10](#max_digits10)|Возвращает количество цифр дробной части, необходимых, чтобы у двух различных значений типа были уникальные десятичные представления.|
|[max_exponent](#max_exponent)|Возвращает максимальную положительную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении основания системы счисления в эту степень.|
|[max_exponent10](#max_exponent10)|Возвращает максимальную положительную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении десяти в эту степень.|
|[min](#min)|Возвращает минимальное нормализованное значение для типа.|
|[min_exponent](#min_exponent)|Возвращает максимальную отрицательную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении основания системы счисления в эту степень.|
|[min_exponent10](#min_exponent10)|Возвращает максимальную отрицательную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении десяти в эту степень.|
|[quiet_NaN](#quiet_nan)|Возвращает представление "тихого" нечисла (NAN) для типа.|
|[radix](#radix)|Возвращает целочисленное основание системы счисления, используемое для представления типа.|
|[round_error](#round_error)|Возвращает максимальную ошибку округления для типа.|
|[round_style](#round_style)|Возвращает значение, описывающее различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.|
|[signaling_NaN](#signaling_nan)|Возвращает представление обозначения нечисла (NAN) для типа.|
|[tinyness_before](#tinyness_before)|Проверяет, может ли тип определить, что значение слишком мало для представления в качестве нормализованного значения, до его округления.|
|[traps](#traps)|Проверяет, реализованы ли для типа исключения при выполнении арифметических операций.|

## <a name="requirements"></a>Требования

**Заголовок:** \<limits>

**Пространство имен:** std

## <a name="denorm_min"></a>  numeric_limits::denorm_min

Возвращает наименьшее ненулевое денормализованное значение.

```cpp
static constexpr Type denorm_min() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Наименьшее ненулевое денормализованное значение.

### <a name="remarks"></a>Примечания

**long double** совпадает со значением **двойные** для компилятора C++.

Функция возвращает минимальное значение для типа, так как [min](#min) Если [has_denorm](#has_denorm) не равно `denorm_present`.

### <a name="example"></a>Пример

```cpp
// numeric_limits_denorm_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The smallest nonzero denormalized value" << endl
        << "for float objects is: "
        << numeric_limits<float>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for double objects is: "
        << numeric_limits<double>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::denorm_min( ) << endl;

   // A smaller value will round to zero
   cout << numeric_limits<float>::denorm_min( )/2 <<endl;
   cout << numeric_limits<double>::denorm_min( )/2 <<endl;
   cout << numeric_limits<long double>::denorm_min( )/2 <<endl;
}
```

```Output
The smallest nonzero denormalized value
for float objects is: 1.4013e-045
The smallest nonzero denormalized value
for double objects is: 4.94066e-324
The smallest nonzero denormalized value
for long double objects is: 4.94066e-324
0
0
0
```

## <a name="digits"></a>  numeric_limits::digits

Возвращает количество цифр основания системы счисления, которое тип может представлять без потери точности.

```cpp
static constexpr int digits = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество цифр основания системы счисления, которое тип может представлять без потери точности.

### <a name="remarks"></a>Примечания

Член сохраняет количество цифр основания системы счисления, которое тип может представлять без изменения, то есть количество бит (кроме бита знака) для предопределенного целочисленного типа, либо количество цифр мантиссы для предопределенного типа числа с плавающей запятой.

### <a name="example"></a>Пример

```cpp
// numeric_limits_digits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits <<endl;
   cout << numeric_limits<double>::digits <<endl;
   cout << numeric_limits<long double>::digits <<endl;
   cout << numeric_limits<int>::digits <<endl;
   cout << numeric_limits<__int64>::digits <<endl;
}
```

```Output
24
53
53
31
63
```

## <a name="digits10"></a>  numeric_limits::digits10

Возвращает количество дробных десятичных цифр, которое тип может представлять без потери точности.

```cpp
static constexpr int digits10 = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество дробных десятичных цифр, которое тип может представлять без потери точности.

### <a name="example"></a>Пример

```cpp
// numeric_limits_digits10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits10 <<endl;
   cout << numeric_limits<double>::digits10 <<endl;
   cout << numeric_limits<long double>::digits10 <<endl;
   cout << numeric_limits<int>::digits10 <<endl;
   cout << numeric_limits<__int64>::digits10 <<endl;
   float f = (float)99999999;
   cout.precision ( 10 );
   cout << "The float is; " << f << endl;
}
```

```Output
6
15
15
9
18
The float is; 100000000
```

## <a name="epsilon"></a>  numeric_limits::epsilon

Функция возвращает разницу между 1 и наименьшим значением больше 1, которое может быть представлено для типа данных.

```cpp
static constexpr Type epsilon() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Разница между 1 и наименьшим значением больше 1, которое может быть представлено для типа данных.

### <a name="remarks"></a>Примечания

Для типа **float** значение будет FLT_EPSILON. `epsilon` для типа — это наименьшее положительное число с плавающей запятой *N*, так что *N* + `epsilon` + *N* можно представить.

### <a name="example"></a>Пример

```cpp
// numeric_limits_epsilon.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for float objects is: "
        << numeric_limits<float>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for double objects is: "
        << numeric_limits<double>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::epsilon( ) << endl;
}
```

```Output
The difference between 1 and the smallest value greater than 1
for float objects is: 1.19209e-007
The difference between 1 and the smallest value greater than 1
for double objects is: 2.22045e-016
The difference between 1 and the smallest value greater than 1
for long double objects is: 2.22045e-016
```

## <a name="has_denorm"></a>  numeric_limits::has_denorm

Проверяет, допускает ли тип денормализованные значения.

```cpp
static constexpr float_denorm_style has_denorm = denorm_absent;
```

### <a name="return-value"></a>Возвращаемое значение

Значение перечисления типа **const**`float_denorm_style`, указывающее, позволяет ли тип использовать денормализованные значения.

### <a name="remarks"></a>Примечания

Член сохраняет `denorm_present` для типа с плавающей запятой, который имеет денормализованные значения, по сути переменное число бит экспоненты.

### <a name="example"></a>Пример

```cpp
// numeric_limits_has_denorm.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects allow denormalized values: "
        << numeric_limits<float>::has_denorm
        << endl;
   cout << "Whether double objects allow denormalized values: "
        << numeric_limits<double>::has_denorm
        << endl;
   cout << "Whether long int objects allow denormalized values: "
        << numeric_limits<long int>::has_denorm
        << endl;
}
```

```Output
Whether float objects allow denormalized values: 1
Whether double objects allow denormalized values: 1
Whether long int objects allow denormalized values: 0
```

## <a name="has_denorm_loss"></a>  numeric_limits::has_denorm_loss

Проверяет, обнаружена ли потеря точности как потеря денормализации, а не неточный результат.

```cpp
static constexpr bool has_denorm_loss = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если потеря точности определена как потеря денормализации; в противном случае **false**.

### <a name="remarks"></a>Примечания

Член сохраняет значение true для типа, который определяет была ли потеря точности связана с представлением в виде денормализованного результата (слишком маленькое для представления в виде нормализованного значения) или поскольку оно неточное (отличается от результата, не подверженного ограничениям диапазона экспоненты и точности), опция с представлениями IEC 559 с плавающей точкой, которые могут повлиять не некоторые результаты.

### <a name="example"></a>Пример

```cpp
// numeric_limits_has_denorm_loss.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects can detect denormalized loss: "
        << numeric_limits<float>::has_denorm_loss
        << endl;
   cout << "Whether double objects can detect denormalized loss: "
        << numeric_limits<double>::has_denorm_loss
        << endl;
   cout << "Whether long int objects can detect denormalized loss: "
        << numeric_limits<long int>::has_denorm_loss
        << endl;
}
```

```Output
Whether float objects can detect denormalized loss: 1
Whether double objects can detect denormalized loss: 1
Whether long int objects can detect denormalized loss: 0
```

## <a name="has_infinity"></a>  numeric_limits::has_infinity

Проверяет, может ли тип представлять положительную бесконечность.

```cpp
static constexpr bool has_infinity = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если тип имеет представление для положительной бесконечности; в противном случае **false**.

### <a name="remarks"></a>Примечания

Член возвращает **true**, если [is_iec559](#is_iec559) имеет значение **true**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_has_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have infinity: "
        << numeric_limits<float>::has_infinity
        << endl;
   cout << "Whether double objects have infinity: "
        << numeric_limits<double>::has_infinity
        << endl;
   cout << "Whether long int objects have infinity: "
        << numeric_limits<long int>::has_infinity
        << endl;
}
```

```Output
Whether float objects have infinity: 1
Whether double objects have infinity: 1
Whether long int objects have infinity: 0
```

## <a name="has_quiet_nan"></a>  numeric_limits::has_quiet_NaN

Проверяет, может ли тип представлять "тихое" нечисло (NAN), которое является несигнализирующим.

```cpp
static constexpr bool has_quiet_NaN = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если **type** имеет представление для "тихого" нечисла; в противном случае **false**.

### <a name="remarks"></a>Примечания

"Тихое" NAN — это кодирование для нечисла, которое не обозначает свое присутствие в выражении. Возвращаемое значение — **true**, если [is_iec559](#is_iec559) имеет значение true.

### <a name="example"></a>Пример

```cpp
// numeric_limits_has_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have quiet_NaN: "
        << numeric_limits<float>::has_quiet_NaN
        << endl;
   cout << "Whether double objects have quiet_NaN: "
        << numeric_limits<double>::has_quiet_NaN
        << endl;
   cout << "Whether long int objects have quiet_NaN: "
        << numeric_limits<long int>::has_quiet_NaN
        << endl;
}
```

```Output
Whether float objects have quiet_NaN: 1
Whether double objects have quiet_NaN: 1
Whether long int objects have quiet_NaN: 0
```

## <a name="has_signaling_nan"></a>  numeric_limits::has_signaling_NaN

Проверяет, может ли тип представлять сообщения об обнаружении нечисла (NAN).

```cpp
static constexpr bool has_signaling_NaN = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если у типа есть представление для сообщения о нечисле (NAN); в противном случае **false**.

### <a name="remarks"></a>Примечания

Сообщение о нечисле — это кодирование для нечисла, которое сообщает о его присутствии в выражении. Возвращаемое значение — **true**, если [is_iec559](#is_iec559) имеет значение true.

### <a name="example"></a>Пример

```cpp
// numeric_limits_has_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signaling_NaN: "
        << numeric_limits<float>::has_signaling_NaN
        << endl;
   cout << "Whether double objects have a signaling_NaN: "
        << numeric_limits<double>::has_signaling_NaN
        << endl;
   cout << "Whether long int objects have a signaling_NaN: "
        << numeric_limits<long int>::has_signaling_NaN
        << endl;
}
```

```Output
Whether float objects have a signaling_NaN: 1
Whether double objects have a signaling_NaN: 1
Whether long int objects have a signaling_NaN: 0
```

## <a name="infinity"></a>  numeric_limits::infinity

Представление положительной бесконечности для типа, если имеется.

```cpp
static constexpr Type infinity() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Представление положительной бесконечности для типа, если имеется.

### <a name="remarks"></a>Примечания

Возвращаемое значение имеет смысл, только если [has_infinity](#has_infinity) имеет значение **true**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::has_infinity <<endl;
   cout << numeric_limits<double>::has_infinity<<endl;
   cout << numeric_limits<long double>::has_infinity <<endl;
   cout << numeric_limits<int>::has_infinity <<endl;
   cout << numeric_limits<__int64>::has_infinity <<endl;

   cout << "The representation of infinity for type float is: "
        << numeric_limits<float>::infinity( ) <<endl;
   cout << "The representation of infinity for type double is: "
        << numeric_limits<double>::infinity( ) <<endl;
   cout << "The representation of infinity for type long double is: "
        << numeric_limits<long double>::infinity( ) <<endl;
}
```

```Output
1
1
1
0
0
The representation of infinity for type float is: inf
The representation of infinity for type double is: inf
The representation of infinity for type long double is: inf
```

## <a name="is_bounded"></a>  numeric_limits::is_bounded

Проверяет, конечен ли набор значений, представляемый типом.

```cpp
static constexpr bool is_bounded = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если тип имеет конечный набор представимых значений; в противном случае **false**.

### <a name="remarks"></a>Примечания

Все предопределенные типы имеют конечный набор представимых значений и возвращают значение **true**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_is_bounded.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have bounded set "
        << "of representable values: "
        << numeric_limits<float>::is_bounded
        << endl;
   cout << "Whether double objects have bounded set "
        << "of representable values: "
        << numeric_limits<double>::is_bounded
        << endl;
   cout << "Whether long int objects have bounded set "
        << "of representable values: "
        << numeric_limits<long int>::is_bounded
        << endl;
   cout << "Whether unsigned char objects have bounded set "
        << "of representable values: "
        << numeric_limits<unsigned char>::is_bounded
        << endl;
}
```

```Output
Whether float objects have bounded set of representable values: 1
Whether double objects have bounded set of representable values: 1
Whether long int objects have bounded set of representable values: 1
Whether unsigned char objects have bounded set of representable values: 1
```

## <a name="is_exact"></a>  numeric_limits::is_exact

Проверяет, не содержат ли вычисления с типом ошибок округления.

```cpp
static constexpr bool is_exact = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если вычисления не содержат ошибок округления; в противном случае **false**.

### <a name="remarks"></a>Примечания

Все предопределенные целочисленные типы имеют точное представление для своих значений и возвращают **false**. Вещественное представление или представление с фиксированной запятой также считается точным, но представление с плавающей точкой — нет.

### <a name="example"></a>Пример

```cpp
// numeric_limits_is_exact.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<float>::is_exact
        << endl;
   cout << "Whether double objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<double>::is_exact
        << endl;
   cout << "Whether long int objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<long int>::is_exact
        << endl;
   cout << "Whether unsigned char objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<unsigned char>::is_exact
        << endl;
}
```

```Output
Whether float objects have calculations free of rounding errors: 0
Whether double objects have calculations free of rounding errors: 0
Whether long int objects have calculations free of rounding errors: 1
Whether unsigned char objects have calculations free of rounding errors: 1
```

## <a name="is_iec559"></a>  numeric_limits::is_iec559

Проверяет, соответствует ли тип стандартам IEC 559.

```cpp
static constexpr bool is_iec559 = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если тип соответствует стандартам IEC 559; в противном случае **false**.

### <a name="remarks"></a>Примечания

IEC 559 — это международный стандарт для представления значений с плавающей точкой, который также известен в США как IEEE 754.

### <a name="example"></a>Пример

```cpp
// numeric_limits_is_iec559.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects conform to iec559 standards: "
        << numeric_limits<float>::is_iec559
        << endl;
   cout << "Whether double objects conform to iec559 standards: "
        << numeric_limits<double>::is_iec559
        << endl;
   cout << "Whether int objects conform to iec559 standards: "
        << numeric_limits<int>::is_iec559
        << endl;
   cout << "Whether unsigned char objects conform to iec559 standards: "
        << numeric_limits<unsigned char>::is_iec559
        << endl;
}
```

```Output
Whether float objects conform to iec559 standards: 1
Whether double objects conform to iec559 standards: 1
Whether int objects conform to iec559 standards: 0
Whether unsigned char objects conform to iec559 standards: 0
```

## <a name="is_integer"></a>  numeric_limits::is_integer

Проверяет, может ли тип представлять целые числа.

```cpp
static constexpr bool is_integer = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если тип может представлять целые числа; в противном случае **false**.

### <a name="remarks"></a>Примечания

Все предопределенные целочисленные типы могут представлять целые числа.

### <a name="example"></a>Пример

```cpp
// numeric_limits_is_integer.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an integral representation: "
        << numeric_limits<float>::is_integer
        << endl;
   cout << "Whether double objects have an integral representation: "
        << numeric_limits<double>::is_integer
        << endl;
   cout << "Whether int objects have an integral representation: "
        << numeric_limits<int>::is_integer
        << endl;
   cout << "Whether unsigned char objects have an integral representation: "
        << numeric_limits<unsigned char>::is_integer
        << endl;
}
```

```Output
Whether float objects have an integral representation: 0
Whether double objects have an integral representation: 0
Whether int objects have an integral representation: 1
Whether unsigned char objects have an integral representation: 1
```

## <a name="is_modulo"></a>  numeric_limits::is_modulo

Проверяет, имеет ли тип **type** представление по модулю.

```cpp
static constexpr bool is_modulo = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если у типа есть представление по модулю; в противном случае **false**.

### <a name="remarks"></a>Примечания

Представление по модулю — это представление, в котором все результаты уменьшены по модулю на некоторое значение. Все предопределенные целочисленные беззнаковые типы имеют представление по модулю.

### <a name="example"></a>Пример

```cpp
// numeric_limits_is_modulo.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a modulo representation: "
        << numeric_limits<float>::is_modulo
        << endl;
   cout << "Whether double objects have a modulo representation: "
        << numeric_limits<double>::is_modulo
        << endl;
   cout << "Whether signed char objects have a modulo representation: "
        << numeric_limits<signed char>::is_modulo
        << endl;
   cout << "Whether unsigned char objects have a modulo representation: "
        << numeric_limits<unsigned char>::is_modulo
        << endl;
}
```

```Output
Whether float objects have a modulo representation: 0
Whether double objects have a modulo representation: 0
Whether signed char objects have a modulo representation: 1
Whether unsigned char objects have a modulo representation: 1
```

## <a name="is_signed"></a>  numeric_limits::is_signed

Проверяет, может ли тип представлять числа со знаком.

```cpp
static constexpr bool is_signed = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если тип может представлять числа со знаком; в противном случае **false**.

### <a name="remarks"></a>Примечания

Член хранит значение true для типа, который может представлять числа со знаком, что верно для всех предопределенных типов с плавающей точкой и целочисленных типов со знаком.

### <a name="example"></a>Пример

```cpp
// numeric_limits_is_signaled.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signed representation: "
        << numeric_limits<float>::is_signed
        << endl;
   cout << "Whether double objects have a signed representation: "
        << numeric_limits<double>::is_signed
        << endl;
   cout << "Whether signed char objects have a signed representation: "
        << numeric_limits<signed char>::is_signed
        << endl;
   cout << "Whether unsigned char objects have a signed representation: "
        << numeric_limits<unsigned char>::is_signed
        << endl;
}
```

```Output
Whether float objects have a signed representation: 1
Whether double objects have a signed representation: 1
Whether signed char objects have a signed representation: 1
Whether unsigned char objects have a signed representation: 0
```

## <a name="is_specialized"></a>  numeric_limits::is_specialized

Проверяет, задана ли для типа явная специализация в классе шаблона `numeric_limits`.

```cpp
static constexpr bool is_specialized = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если у типа есть явная специализация для класса-шаблона; в противном случае **false**.

### <a name="remarks"></a>Примечания

Все скалярные типы, кроме указателей, имеют явную специализацию, определенную для класса-шаблона `numeric_limits`.

### <a name="example"></a>Пример

```cpp
// numeric_limits_is_specialized.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float>::is_specialized
        << endl;
   cout << "Whether float* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float*>::is_specialized
        << endl;
   cout << "Whether int objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int>::is_specialized
        << endl;
   cout << "Whether int* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int*>::is_specialized
        << endl;
}
```

```Output
Whether float objects have an explicit specialization in the class: 1
Whether float* objects have an explicit specialization in the class: 0
Whether int objects have an explicit specialization in the class: 1
Whether int* objects have an explicit specialization in the class: 0
```

## <a name="lowest"></a>  numeric_limits::lowest

Возвращает наибольшее отрицательное конечное значение.

```cpp
static constexpr Type lowest() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает наибольшее отрицательное конечное значение.

### <a name="remarks"></a>Примечания

Возвращает наибольшее отрицательное конечное значение для типа (обычно `min()` для целочисленных типов и `-max()` для типов с плавающей запятой). Возвращаемое значение имеет смысл Если `is_bounded` — **true**.

## <a name="max"></a>  numeric_limits::max

Возвращает максимальное конечное значение типа.

```cpp
static constexpr Type max() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное конечное значение для типа.

### <a name="remarks"></a>Примечания

Максимальное конечное значение — INT_MAX для типа **int** и FLT_MAX для типа **float**. Возвращаемое значение имеет смысл, если [is_bounded](#is_bounded) имеет значение **true**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_max.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main() {
   cout << "The maximum value for type float is:  "
        << numeric_limits<float>::max( )
        << endl;
   cout << "The maximum value for type double is:  "
        << numeric_limits<double>::max( )
        << endl;
   cout << "The maximum value for type int is:  "
        << numeric_limits<int>::max( )
        << endl;
   cout << "The maximum value for type short int is:  "
        << numeric_limits<short int>::max( )
        << endl;
}
```

## <a name="max_digits10"></a>  numeric_limits::max_digits10

Возвращает количество цифр дробной части, необходимых, чтобы у двух различных значений типа были уникальные десятичные представления.

```cpp
static constexpr int max_digits10 = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество цифр дробной части, необходимых, чтобы у двух различных значений типа были уникальные десятичные представления.

### <a name="remarks"></a>Примечания

Этот член хранит количество цифр дробной части, необходимых, чтобы у двух различных значений типа были уникальные десятичные представления.

## <a name="max_exponent"></a>  numeric_limits::max_digits10

Возвращает максимальную положительную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении основания системы счисления в эту степень.

```cpp
static constexpr int max_exponent = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальная целочисленная степень для основания системы счисления, представляемая типом.

### <a name="remarks"></a>Примечания

Возвращаемое значение функции-члена имеет смысл только для типов с плавающей запятой. `max_exponent` — это значение FLT_MAX_EXP для типа **float**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_max_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum radix-based exponent for type float is:  "
        << numeric_limits<float>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type double is:  "
        << numeric_limits<double>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type long double is:  "
        << numeric_limits<long double>::max_exponent
        << endl;
}
```

```Output
The maximum radix-based exponent for type float is:  128
The maximum radix-based exponent for type double is:  1024
The maximum radix-based exponent for type long double is:  1024
```

## <a name="max_exponent10"></a>  numeric_limits::max_exponent10

Возвращает максимальную положительную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении десяти в эту степень.

```cpp
static constexpr int max_exponent10 = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальная целочисленная степень основания 10, которую может представить этот тип.

### <a name="remarks"></a>Примечания

Возвращаемое значение функции-члена имеет смысл только для типов с плавающей запятой. `max_exponent` — это значение FLT_MAX_10 для типа **float**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_max_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum base 10 exponent for type float is:  "
           << numeric_limits<float>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type double is:  "
           << numeric_limits<double>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type long double is:  "
           << numeric_limits<long double>::max_exponent10
           << endl;
}
```

```Output
The maximum base 10 exponent for type float is:  38
The maximum base 10 exponent for type double is:  308
The maximum base 10 exponent for type long double is:  308
```

## <a name="min"></a>  numeric_limits::min

Возвращает минимальное нормализованное значение для типа.

```cpp
static constexpr Type min() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное нормализованное значение для типа.

### <a name="remarks"></a>Примечания

Минимальное нормализованное значение — INT_MIN для типа **int** и — FLT_MIN для типа **float**. Возвращаемое значение имеет смысл Если [is_bounded](#is_bounded) — **true** или, если [is_signed](#is_signed) — **false**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum value for type float is:  "
        << numeric_limits<float>::min( )
        << endl;
   cout << "The minimum value for type double is:  "
        << numeric_limits<double>::min( )
        << endl;
   cout << "The minimum value for type int is:  "
        << numeric_limits<int>::min( )
        << endl;
   cout << "The minimum value for type short int is:  "
        << numeric_limits<short int>::min( )
        << endl;
}
```

```Output
The minimum value for type float is:  1.17549e-038
The minimum value for type double is:  2.22507e-308
The minimum value for type int is:  -2147483648
The minimum value for type short int is:  -32768
```

## <a name="min_exponent"></a>  numeric_limits::min_exponent

Возвращает максимальную отрицательную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении основания системы счисления в эту степень.

```cpp
static constexpr int min_exponent = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальная целочисленная степень основания системы счисления, которую может представить тип.

### <a name="remarks"></a>Примечания

Функция-член имеет смысл только для типов с плавающей запятой. `min_exponent` для типа **float** — FLT_MIN_EXP.

### <a name="example"></a>Пример

```cpp
// numeric_limits_min_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum radix-based exponent for type float is:  "
        << numeric_limits<float>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type double is:  "
        << numeric_limits<double>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type long double is:  "
         << numeric_limits<long double>::min_exponent
        << endl;
}
```

```Output
The minimum radix-based exponent for type float is:  -125
The minimum radix-based exponent for type double is:  -1021
The minimum radix-based exponent for type long double is:  -1021
```

## <a name="min_exponent10"></a>  numeric_limits::min_exponent10

Возвращает максимальную отрицательную целую степень, которую тип с плавающей запятой может представить как конечное значение при возведении десяти в эту степень.

```cpp
static constexpr int min_exponent10 = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальная целая степень числа 10, которую может представить тип.

### <a name="remarks"></a>Примечания

Функция-член имеет смысл только для типов с плавающей запятой. `min_exponent10` для типа **float** — значение FLT_MIN_10_EXP.

### <a name="example"></a>Пример

```cpp
// numeric_limits_min_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum base 10 exponent for type float is:  "
        << numeric_limits<float>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type double is:  "
        << numeric_limits<double>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type long double is:  "
        << numeric_limits<long double>::min_exponent10
        << endl;
}
```

```Output
The minimum base 10 exponent for type float is:  -37
The minimum base 10 exponent for type double is:  -307
The minimum base 10 exponent for type long double is:  -307
```

## <a name="quiet_nan"></a>  numeric_limits::quiet_NaN

Возвращает представление "тихого" нечисла (NAN) для типа.

```cpp
static constexpr Type quiet_NaN() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Представление "тихого" нечисла (NAN) для типа.

### <a name="remarks"></a>Примечания

Возвращаемое значение имеет смысл, только если [has_quiet_NaN](#has_quiet_nan) имеет значение **true**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The quiet NaN for type float is:  "
        << numeric_limits<float>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type int is:  "
        << numeric_limits<int>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type long double is:  "
        << numeric_limits<long double>::quiet_NaN( )
        << endl;
}
```

```Output
The quiet NaN for type float is:  1.#QNAN
The quiet NaN for type int is:  0
The quiet NaN for type long double is:  1.#QNAN
```

## <a name="radix"></a>  numeric_limits::radix

Возвращает целочисленное основание системы счисления, используемое для представления типа.

```cpp
static constexpr int radix = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Целочисленная база для представления типа.

### <a name="remarks"></a>Примечания

Для предопределенных целочисленных типов база — 2, а для предопределенных типов с плавающей запятой — база, в которую можно возвести степень, или FLT_RADIX.

### <a name="example"></a>Пример

```cpp
// numeric_limits_radix.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The base for type float is:  "
        << numeric_limits<float>::radix
        << endl;
   cout << "The base for type int is:  "
        << numeric_limits<int>::radix
        << endl;
   cout << "The base for type long double is:  "
        << numeric_limits<long double>::radix
        << endl;
}
```

```Output
The base for type float is:  2
The base for type int is:  2
The base for type long double is:  2
```

## <a name="round_error"></a>  numeric_limits::round_error

Возвращает максимальную ошибку округления для типа.

```cpp
static constexpr Type round_error() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальная ошибка округления для типа.

### <a name="example"></a>Пример

```cpp
// numeric_limits_round_error.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum rounding error for type float is:  "
        << numeric_limits<float>::round_error( )
        << endl;
   cout << "The maximum rounding error for type int is:  "
        << numeric_limits<int>::round_error( )
        << endl;
   cout << "The maximum rounding error for type long double is:  "
        << numeric_limits<long double>::round_error( )
        << endl;
}
```

```Output
The maximum rounding error for type float is:  0.5
The maximum rounding error for type int is:  0
The maximum rounding error for type long double is:  0.5
```

## <a name="round_style"></a>  numeric_limits::round_style

Возвращает значение, описывающее различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.

```cpp
static constexpr float_round_style round_style = round_toward_zero;
```

### <a name="return-value"></a>Возвращаемое значение

Значение из перечисления `float_round_style`, которое описывает тип округления.

### <a name="remarks"></a>Примечания

Член хранит значение, которое описывает различные методы, из которых реализация может выбирать для округления значения с плавающей точкой до целого значения.

Метод округления жестко закодирован в реализации, поэтому даже если программа запускается с другим методом округления, это значение не изменится.

### <a name="example"></a>Пример

```cpp
// numeric_limits_round_style.cpp
// compile with: /EHsc
#include <iostream>
#include <float.h>
#include <limits>

using namespace std;

int main( )
{
   cout << "The rounding style for a double type is: "
        << numeric_limits<double>::round_style << endl;
   _controlfp_s(NULL,_RC_DOWN,_MCW_RC );
   cout << "The rounding style for a double type is now: "
        << numeric_limits<double>::round_style << endl;
   cout << "The rounding style for an int type is: "
        << numeric_limits<int>::round_style << endl;
}
```

```Output
The rounding style for a double type is: 1
The rounding style for a double type is now: 1
The rounding style for an int type is: 0
```

## <a name="signaling_nan"></a>  numeric_limits::signaling_NaN

Возвращает представление обозначения нечисла (NAN) для типа.

```cpp
static constexpr Type signaling_NaN() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Представление сообщения о нечисле (NAN) для типа.

### <a name="remarks"></a>Примечания

Возвращаемое значение имеет смысл, только если [has_signaling_NaN](#has_signaling_nan) имеет значение **true**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The signaling NaN for type float is:  "
        << numeric_limits<float>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type int is:  "
        << numeric_limits<int>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type long double is:  "
        << numeric_limits<long double>::signaling_NaN( )
        << endl;
}
```

## <a name="tinyness_before"></a>  numeric_limits::tinyness_before

Проверяет, может ли тип определить, что значение слишком мало для представления в качестве нормализованного значения, до его округления.

```cpp
static constexpr bool tinyness_before = false;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если тип можно определить, что значение слишком мало перед округлением; **false** Если это невозможно.

### <a name="remarks"></a>Примечания

Типы, которые могут распознавать слишком малые значения, были включены в представления IEC 559 с плавающей запятой в качестве опции и их реализация может влиять на некоторые результаты.

### <a name="example"></a>Пример

```cpp
// numeric_limits_tinyness_before.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types can detect tinyness before rounding: "
        << numeric_limits<float>::tinyness_before
        << endl;
   cout << "Whether double types can detect tinyness before rounding: "
        << numeric_limits<double>::tinyness_before
        << endl;
   cout << "Whether long int types can detect tinyness before rounding: "
        << numeric_limits<long int>::tinyness_before
        << endl;
   cout << "Whether unsigned char types can detect tinyness before rounding: "
        << numeric_limits<unsigned char>::tinyness_before
        << endl;
}
```

```Output
Whether float types can detect tinyness before rounding: 1
Whether double types can detect tinyness before rounding: 1
Whether long int types can detect tinyness before rounding: 0
Whether unsigned char types can detect tinyness before rounding: 0
```

## <a name="traps"></a>  numeric_limits::traps

Проверяет, реализованы ли для типа исключения при выполнении арифметических операций.

```cpp
static constexpr bool traps = false;
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если для типа реализованы исключения; в противном случае **false**.

### <a name="example"></a>Пример

```cpp
// numeric_limits_traps.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types have implemented trapping: "
        << numeric_limits<float>::traps
        << endl;
   cout << "Whether double types have implemented trapping: "
        << numeric_limits<double>::traps
        << endl;
   cout << "Whether long int types have implemented trapping: "
        << numeric_limits<long int>::traps
        << endl;
   cout << "Whether unsigned char types have implemented trapping: "
        << numeric_limits<unsigned char>::traps
        << endl;
}
```

```Output
Whether float types have implemented trapping: 1
Whether double types have implemented trapping: 1
Whether long int types have implemented trapping: 0
Whether unsigned char types have implemented trapping: 0
```

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
