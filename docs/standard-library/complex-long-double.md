---
title: complex&lt;long double&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
dev_langs:
- C++
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92b0a7c9ae697bc28ad9fe3bd89d37f22d7a8cdc
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313472"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

Описывает объект, который хранит упорядоченную пару объектов типа **long double**, первый представляет вещественную часть комплексного числа, а второй мнимую.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Параметры

*_RealVal*<br/>
Значение типа **long double** для вещественной части конструируемого комплексного числа.

*_ImagVal*<br/>
Значение типа **long double** для мнимой части конструируемого комплексного числа.

*complexNum*<br/>
Комплексное число типа **двойные** или типа **float** , и действительная и мнимая части которого используются для инициализации комплексное число типа **long double** конструируемого.

## <a name="return-value"></a>Возвращаемое значение

Комплексное число типа **long double**.

## <a name="remarks"></a>Примечания

Явная специализация класса шаблона complex для класса complex типа **long double** отличается от класса шаблона только конструкторами. Преобразование из **long double** для **float** может быть неявным, но преобразование из **двойные** для **long double** является обязательным Чтобы быть **явные**. Использование **явного** типа исключает инициацию преобразования типа при помощи синтаксиса назначения.

Дополнительные сведения о классе шаблона `complex` см. в разделе [Класс complex](../standard-library/complex-class.md). Список членов класса шаблона `complex` см. в разделе.

## <a name="example"></a>Пример

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <long double> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type float
   complex <float> c2float ( 1.0 , 3.0 );
   complex <long double> c2longdouble ( c2float );
   cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type double
   complex <double> c3double ( 3.0 , 4.0 );
   complex <long double> c3longdouble ( c3double );
   cout << "Implicit conversion from type long double to type float,"
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
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>Требования

**Заголовок**: \<complex>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс complex](../standard-library/complex-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
