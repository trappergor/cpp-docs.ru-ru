---
title: "complex&lt;float&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::complex<float>
- std.complex<float>
- complex<float>
dev_langs:
- C++
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b3c76d33bcdf1e5882bd09b49c73dcef4d0474b3
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="complexltfloatgt"></a>complex&lt;float&gt;
Описывает объект, который хранит упорядоченную пару объектов типа **float***,* первый представляет вещественную часть комплексного числа, а второй — мнимую.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as template class complex
};
```  
  
#### <a name="parameters"></a>Параметры  
 `_RealVal`  
 Значение типа **float** для вещественной части конструируемого комплексного числа.  
  
 `_ImagVal`  
 Значение типа **float** для мнимой части конструируемого комплексного числа.  
  
 `complexNum`  
 Комплексное число типа **double** или типа `long double`, вещественные и мнимые части которого используются для инициализации конструируемого комплексного числа типа **float**.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Комплексное число типа **float**.  
  
## <a name="remarks"></a>Примечания  
 Явная специализация класса шаблона complex для класса complex типа **float** отличается от класса шаблона только определяемыми конструкторами. Преобразование из **float** в **double** может быть неявным, но менее безопасное преобразование из **float** в `long double` должно быть **явным**. Использование **явного** типа исключает инициацию преобразования типа при помощи синтаксиса назначения.  
  
 Дополнительные сведения о классе шаблона `complex` см. в разделе [Класс complex](../standard-library/complex-class.md). Список членов класса шаблона `complex` см. в разделе.  
  
## <a name="example"></a>Пример  
  
```cpp  
// complex_comp_flt.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <float> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type double  
   complex <double> c2double ( 1.0 , 3.0 );  
   complex <float> c2float ( c2double );  
   cout << "Implicit conversion from type double to type float,"  
        << "\n gives c2float = " << c2float << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type long double  
   complex <long double> c3longdouble ( 3.0 , 4.0 );  
   complex <float> c3float ( c3longdouble );  
   cout << "Explicit conversion from type long double to type float,"  
        << "\n gives c3float = " << c3float << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3float);  
   double argc3 = arg ( c3float);  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
\* Output:   
Specifying initial real & imaginary parts,  
 as type float gives c1 = (4,5)  
Implicit conversion from type double to type float,  
 gives c2float = (1,3)  
Explicit conversion from type long double to type float,  
 gives c3float = (3,4)  
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5  
Argument of c3 is recovered from c3 using:  
 arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.  
*\  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок**: \<complex>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Класс complex](../standard-library/complex-class.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




