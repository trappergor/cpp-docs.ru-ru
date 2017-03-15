---
title: "complex&lt;double&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.complex<double>"
  - "complex<double>"
  - "std::complex<double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция комплексного < double >"
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# complex&lt;double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта, который хранит упорядоченную пару объектов типа **double***;* первый представляет вещественную часть комплексного числа, а второй — мнимую.  
  
## Синтаксис  
  
```  
template<>  
   class complex<double> {  
public:  
   constexpr complex(  
      double _RealVal = 0,   
      double _ImagVal = 0  
   );  
  
   constexpr complex(  
      const complex<double>& _ComplexNum  
   );  
   constexpr explicit complex(  
      const complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### Параметры  
 `_RealVal`  
 Значение типа **double** для вещественной части конструируемого комплексного числа.  
  
 `_ImagVal`  
 Значение типа **double** для мнимой части конструируемого комплексного числа.  
  
 `_ComplexNum`  
 Комплексное число типа **float** или типа `long double`, вещественные и мнимые части которого используются для инициализации конструируемого комплексного числа типа **double**.  
  
## Возвращаемое значение  
 Комплексное число типа **double**.  
  
## Заметки  
 Явная специализация комплексного класса шаблонов для комплексного класса типа **double** отличается от класса шаблона только определяемыми конструкторами. Преобразование из **float** в **double** может быть неявным, но преобразование из `long double` в **double** должно быть **явным**. Использование **явного** типа исключает инициацию преобразования типа при помощи синтаксиса назначения.  
  
 Дополнительные сведения о классе шаблона `complex`, в разделе [Класс complex](../standard-library/complex-class.md). Список членов класса шаблона `complex` см. в разделе.  
  
## Пример  
  
```  
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
```  
  
 **Указание начальной реальные и мнимые части, как тип double дает c1 \= \(4,5\) неявное преобразование из типа float в тип double, предоставляет c2double \= \(4,5\) явное преобразование из типа float в тип double, c3longdouble дает \= \(4,5\) модуль c3 восстанавливается с помощью c3: abs \(c3\) \= 6.40312 аргумент c3 восстанавливается с помощью c3: arg \(c3\) \= 0.896055 радианах, который является 51.3402 градусов.**   
## Требования  
 **Заголовок**: \<complex\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Класс complex](../standard-library/complex-class.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)