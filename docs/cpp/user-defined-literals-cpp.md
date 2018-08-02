---
title: Определяемые пользователем литералы (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38c3f60f7460a3d03f16141b5629bfc2d6183cae
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462379"
---
# <a name="user-defined-literals--c"></a>Определяемые пользователем литералы (C++)
Существует пять основных категорий литералов: целое число, символ, число с плавающей запятой, строка, логическое значение и указатель.  Начиная с версии C++ 11, можно определять собственные литералы на основе этих категорий для создания синтаксических ярлыков для общих идиом и повышения безопасности типов. Например, предположим, имеется класс "Расстояние". Можно определить один литерал для километров и еще один — для миль и требовать от пользователя указывать явно единицы измерения, написав: auto d = 42,0_km или auto d = 42,0_mi. Определяемые пользователем литералы не дают выигрыша в производительности. Они служат, главным образом, для удобства и для определения типов во время компиляции. Стандартная библиотека содержит определяемые пользователем литералы для std: String, std::complex и единиц времени и длительности операций в \<chrono > заголовка:  
  
```cpp 
Distance d = 36.0_mi + 42.0_km;         // Custom UDL (see below)  
    std::string str = "hello"s + "World"s;  // Standard Library <string> UDL  
    complex<double> num =   
        (2.0 + 3.01i) * (5.0 + 4.3i);       // Standard Library <complex> UDL  
    auto duration = 15ms + 42h;             // Standard Library <chrono> UDLs  
```  
  
## <a name="user-defined-literal-operator-signatures"></a>Сигнатуры определяемых пользователем литеральных операторов  
 Реализовать определяемый пользователем литерал, определив **оператор "»** в пределах пространства имен с одним из следующих форм:  
  
```cpp 
ReturnType operator "" _a(unsigned long long int);   // Literal operator for user-defined INTEGRAL literal  
ReturnType operator "" _b(long double);              // Literal operator for user-defined FLOATING literal  
ReturnType operator "" _c(char);                     // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _d(wchar_t);                  // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _e(char16_t);                 // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _f(char32_t);                 // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _g(const     char*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _h(const  wchar_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _i(const char16_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _g(const char32_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _r(const char*);              // Raw literal operator  
template<char...> ReturnType operator "" _t();       // Literal operator template  
```  
  
 Имена операторов, использованные в предыдущем примере, можно заменить на любые другие. Обязательным является лишь символ подчеркивания в начале. (Только в стандартной библиотеке разрешено определять литералы без символа подчеркивания.) Тип возвращаемого значения находится там, где настраивается преобразование или другая операция, выполняемая литералом. Кроме того, все эти операторы могут быть определены как `constexpr`.  
  
## <a name="cooked-literals"></a>Литералы с обработкой  
 В исходном коде любой литерал, определяемых пользователем или не является фактически последовательностью буквенно-цифровые символы, такие как `101`, или `54.7`, или `"hello"` или **true**. Компилятор интерпретирует последовательность как целое число, число с плавающей запятой, const char\* строки и т. д. Определяемый пользователем литерал, который принимает в качестве входных данных тот тип, который компилятор назначит значению литерала, неофициально называется *литерал с обработкой*. Все операторы, описанные выше, за исключением `_r` и `_t`, являются литералами с обработкой. Например, литерал `42.0_km` будет привязан к оператору с именем _km, имеющему сигнатуру похожую на _b, а литерал `42_km` будет привязан к оператору с сигнатурой похожей на _a.  
  
 В следующем примере показано, как определяемые пользователем литералы могут потребовать от пользователей явно указывать входные данные. Чтобы создать `Distance`, пользователь должен явно указать километры или мили с помощью соответствующего пользовательского литерала. Такого же результата можно добиться и другими способами, но с помощью пользовательских литералов это сделать проще.  
  
```cpp 
struct Distance  
{  
private:  
    explicit Distance(long double val) : kilometers(val)  
    {}  
  
    friend Distance operator"" _km(long double  val);  
    friend Distance operator"" _mi(long double val);  
    long double kilometers{ 0 };  
public:  
    long double get_kilometers() { return kilometers; }  
    Distance operator+(Distance& other)  
    {  
        return Distance(get_kilometers() + other.get_kilometers());  
    }  
};  
  
Distance operator"" _km(long double  val)  
{  
    return Distance(val);  
}  
  
Distance operator"" _mi(long double val)  
{  
    return Distance(val * 1.6);  
}  
int main(int argc, char* argv[])  
{  
    // Must have a decimal point to bind to the operator we defined!  
    Distance d{ 402.0_km }; // construct using kilometers  
    cout << "Kilometers in d: " << d.get_kilometers() << endl; // 402  
  
    Distance d2{ 402.0_mi }; // construct using miles  
    cout << "Kilometers in d2: " << d2.get_kilometers() << endl;  //643.2  
  
    // add distances constructed with different units  
    Distance d3 = 36.0_mi + 42.0_km;  
    cout << "d3 value = " << d3.get_kilometers() << endl; // 99.6  
  
   // Distance d4(90.0); // error constructor not accessible  
  
    string s;  
    getline(cin, s);  
    return 0;  
}  
```  
  
 Обратите внимание, что число литерала должно быть в десятичном формате. В противном случае оно будет интерпретировано как целое число и тип будет несовместим с оператором. Также Обратите внимание, что для плавающей входных данных, тип должен быть **long double**, а для целочисленных типов, он должен быть **long long**.  
  
## <a name="raw-literals"></a>Необработанные литералы  
 В необработанном пользовательском литерале определяемый оператор воспринимает литерал как последовательность значений символьного типа, которую можно по-разному интерпретировать: как число, как строку или как значение другого типа. В списке операторов, приведенном ранее на этой странице, есть операторы, `_r` и `_t`, которые можно использовать для определения необработанных литералов:  
  
```cpp 
ReturnType operator "" _r(const char*);              // Raw literal operator  
template<char...> ReturnType operator "" _t();       // Literal operator template  
```  
  
 Необработанные литералы можно использовать для получения пользовательских интерпретаций входной последовательности, отличных от тех, которые реализовал бы компилятор. Например, вы можете определить литерал, преобразующий последовательность `4.75987` в пользовательский тип десятичного числа вместо типа с плавающей запятой по стандарту IEEE 754. Необработанные литералы, так же как и литералы с обработкой, можно использовать для выполнения проверки входных последовательностей во время компиляции.  
  
### <a name="example"></a>Пример  
  
### <a name="limitations-of-raw-literals"></a>Ограничения для необработанных литералов  
 Оператор необработанного литерала и шаблон оператора литерала работают только с пользовательскими литералами, имеющими целочисленный тип или тип числа с плавающей запятой, как показано в следующем примере.  
  
```cpp 
#include <cstddef>  
#include <cstdio>  
  
void operator "" _dump(unsigned long long int lit)  { printf("operator \"\" _dump(unsigned long long int) : ===>%llu<===\n", lit); };  // Literal operator for user-defined INTEGRAL literal  
void operator "" _dump(long double lit)             { printf("operator \"\" _dump(long double)            : ===>%Lf<===\n",  lit); };  // Literal operator for user-defined FLOATING literal  
void operator "" _dump(char lit)                    { printf("operator \"\" _dump(char)                   : ===>%c<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(wchar_t lit)                 { printf("operator \"\" _dump(wchar_t)                : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(char16_t lit)                { printf("operator \"\" _dump(char16_t)               : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(char32_t lit)                { printf("operator \"\" _dump(char32_t)               : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(const     char* lit, size_t) { printf("operator \"\" _dump(const     char*, size_t): ===>%s<===\n",   lit); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const  wchar_t* lit, size_t) { printf("operator \"\" _dump(const  wchar_t*, size_t): ===>%ls<===\n",  lit); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const char16_t* lit, size_t) { printf("operator \"\" _dump(const char16_t*, size_t):\n"                  ); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const char32_t* lit, size_t) { printf("operator \"\" _dump(const char32_t*, size_t):\n"                  ); };  // Literal operator for user-defined STRING literal  
void operator "" _dump_raw(const char* lit)         { printf("operator \"\" _dump_raw(const char*)        : ===>%s<===\n",   lit); };  // Raw literal operator  
  
template<char...> void operator "" _dump_template();       // Literal operator template  
  
int main(int argc, const char* argv[])  
{  
    42_dump;  
    3.1415926_dump;  
    3.14e+25_dump;  
     'A'_dump;  
    L'B'_dump;  
    u'C'_dump;  
    U'D'_dump;  
      "Hello World"_dump;  
     L"Wide String"_dump;  
    u8"UTF-8 String"_dump;  
     u"UTF-16 String"_dump;  
     U"UTF-32 String"_dump;  
  
    42_dump_raw;  
    3.1415926_dump_raw;  
    3.14e+25_dump_raw;  
    // 'A'_dump_raw;               // There is no raw literal operator or literal operator template support on this type  
    //L'B'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //u'C'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //U'D'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //  "Hello World"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    // L"Wide String"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    //u8"UTF-8 String"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    // u"UTF-16 String"_dump_raw;  // There is no raw literal operator or literal operator template support on this type  
    // U"UTF-32 String"_dump_raw;  // There is no raw literal operator or literal operator template support on this type  
}  
/*****  
Output:  
operator "" _dump(unsigned long long int) : ===>42<===  
operator "" _dump(long double)            : ===>3.141593<===  
operator "" _dump(long double)            : ===>31399999999999998506827776.000000<===  
operator "" _dump(char)                   : ===>A<===  
operator "" _dump(wchar_t)                : ===>66<===  
operator "" _dump(char16_t)               : ===>67<===  
operator "" _dump(char32_t)               : ===>68<===  
operator "" _dump(const     char*, size_t): ===>Hello World<===  
operator "" _dump(const  wchar_t*, size_t): ===>Wide String<===  
operator "" _dump(const     char*, size_t): ===>UTF-8 String<===  
operator "" _dump(const char16_t*, size_t):  
operator "" _dump(const char32_t*, size_t):  
operator "" _dump_raw(const char*)        : ===>42<===  
operator "" _dump_raw(const char*)        : ===>3.1415926<===  
operator "" _dump_raw(const char*)        : ===>3.14e+25<===   
*****/  
```