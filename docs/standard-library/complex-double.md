---
title: complex&lt;double&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- complex/std::complex<double>
dev_langs:
- C++
helpviewer_keywords:
- complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6008d97b0fab437a9ba2e6b8e0af8d3bc111532a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218961"
---
# <a name="complexltdoublegt"></a>complex&lt;double&gt;

Описывает объект, который хранит упорядоченную пару объектов типа **двойные**, первый представляет вещественную часть комплексного числа, а второй мнимую.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class complex<double> {
public:
    constexpr complex(
    double RealVal = 0,
    double ImagVal = 0);

constexpr complex(const complex<double>& complexNum);

constexpr explicit complex(const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Параметры

*RealVal*<br/>
Значение типа **double** для вещественной части конструируемого комплексного числа.

*ImagVal*<br/>
Значение типа **double** для мнимой части конструируемого комплексного числа.

*complexNum*<br/>
Комплексное число типа **float** или типа **long double** , и действительная и мнимая части которого используются для инициализации комплексное число типа **двойные** конструируемого.

## <a name="return-value"></a>Возвращаемое значение

Комплексное число типа **double**.

## <a name="remarks"></a>Примечания

Явная специализация комплексного класса шаблонов для комплексного класса типа **double** отличается от класса шаблона только определяемыми конструкторами. Преобразование из **float** для **двойные** может быть неявным, но преобразование из **long double** для **двойные** должен быть **явные**. Использование **явного** типа исключает инициацию преобразования типа при помощи синтаксиса назначения.

Дополнительные сведения о классе шаблона `complex` см. в разделе [Класс complex](../standard-library/complex-class.md). Список членов класса шаблона `complex` см. в разделе.

## <a name="example"></a>Пример

```cpp
// complex_comp_dbl.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <double> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type double gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type float
   complex <float> c2float ( 4.0 , 5.0 );
   complex <double> c2double ( c2float );
   cout << "Implicit conversion from type float to type double,"
        << "\n gives c2double = " << c2double << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 4.0 , 5.0 );
   complex <double> c3double ( c3longdouble );
   cout << "Explicit conversion from type float to type double,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3longdouble );
   double argc3 = arg ( c3longdouble );
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
 as type double gives c1 = (4,5)
Implicit conversion from type float to type double,
 gives c2double = (4,5)
Explicit conversion from type float to type double,
 gives c3longdouble = (4,5)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 6.40312
Argument of c3 is recovered from c3 using:
 arg ( c3 ) = 0.896055 radians, which is 51.3402 degrees.
*/
```

## <a name="requirements"></a>Требования

**Заголовок**: \<complex>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс complex](../standard-library/complex-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
