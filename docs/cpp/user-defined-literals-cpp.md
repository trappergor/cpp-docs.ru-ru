---
title: Определяемые пользователем литералы (C++)
description: Описывает назначение и использование определяемых пользователем литералов в стандарте C++.
ms.date: 02/10/2020
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
ms.openlocfilehash: a6636be414fa4dc199ce10fca1b33f092492575f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2020
ms.locfileid: "79090564"
---
# <a name="user-defined-literals"></a>Определенные пользователем литералы

В C++существует шесть основных категорий литералов: целое число, символ, число с плавающей запятой, строка, логическое значение и указатель. Начиная с C++ 11, можно определить собственные литералы на основе этих категорий, чтобы предоставить синтаксические сочетания клавиш для общих идиом и повышения безопасности типов. Например, предположим, что у вас есть `Distance` класс. Вы можете определить литерал для километра, а другой — для миль, и порекомендовать пользователю явно указать единицы измерения, написав: `auto d = 42.0_km` или `auto d = 42.0_mi`. Нет преимуществ в производительности или недостатков для пользовательских литералов; они предназначены в первую очередь для удобства или для выведения типа во время компиляции. Стандартная библиотека содержит пользовательские литералы для `std::string`, для `std::complex`и для единиц в операциях времени и длительности в заголовке \<Chrono >:

```cpp
Distance d = 36.0_mi + 42.0_km;         // Custom UDL (see below)
std::string str = "hello"s + "World"s;  // Standard Library <string> UDL
complex<double> num =
   (2.0 + 3.01i) * (5.0 + 4.3i);        // Standard Library <complex> UDL
auto duration = 15ms + 42h;             // Standard Library <chrono> UDLs
```

## <a name="user-defined-literal-operator-signatures"></a>Сигнатуры определяемых пользователем литеральных операторов

Определяемый пользователем литерал реализуется путем определения **оператора ""** в области пространства имен с помощью одной из следующих форм:

```cpp
ReturnType operator "" _a(unsigned long long int);   // Literal operator for user-defined INTEGRAL literal
ReturnType operator "" _b(long double);              // Literal operator for user-defined FLOATING literal
ReturnType operator "" _c(char);                     // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _d(wchar_t);                  // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _e(char16_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _f(char32_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _g(const char*, size_t);      // Literal operator for user-defined STRING literal
ReturnType operator "" _h(const wchar_t*, size_t);   // Literal operator for user-defined STRING literal
ReturnType operator "" _i(const char16_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _g(const char32_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

Имена операторов, использованные в предыдущем примере, можно заменить на любые другие. Обязательным является лишь символ подчеркивания в начале. (Только стандартная библиотека может определять литералы без подчеркивания.) Тип возвращаемого значения — это место, где вы настраиваете преобразование или другие операции, выполняемые литералом. Кроме того, все эти операторы могут быть определены как `constexpr`.

## <a name="cooked-literals"></a>Литералы с обработкой

В исходном коде любой литерал, определяемый пользователем или нет, по сути представляет собой последовательность буквенно-цифровых символов, например `101`или `54.7`или `"hello"` или `true`. Компилятор интерпретирует последовательность как целое число, float, const char\* строку и т. д. Определяемый пользователем литерал, принимающий в качестве входных данных любой тип, присвоенный литеральному значению, формально называется *литералом обработанные*. Все операторы, описанные выше, за исключением `_r` и `_t`, являются литералами с обработкой. Например, литерал `42.0_km` будет привязан к оператору с именем _km, имеющему сигнатуру похожую на _b, а литерал `42_km` будет привязан к оператору с сигнатурой похожей на _a.

В следующем примере показано, как определяемые пользователем литералы могут потребовать от пользователей явно указывать входные данные. Чтобы создать `Distance`, пользователь должен явно указать километры или мили с помощью соответствующего пользовательского литерала. Такой же результат можно получить другими способами, но определенные пользователем литералы менее детализированы, чем альтернативные варианты.

```cpp
// UDL_Distance.cpp

#include <iostream>
#include <string>

struct Distance
{
private:
    explicit Distance(long double val) : kilometers(val)
    {}

    friend Distance operator"" _km(long double val);
    friend Distance operator"" _mi(long double val);

    long double kilometers{ 0 };
public:
    const static long double km_per_mile;
    long double get_kilometers() { return kilometers; }

    Distance operator+(Distance other)
    {
        return Distance(get_kilometers() + other.get_kilometers());
    }
};

const long double Distance::km_per_mile = 1.609344L;

Distance operator"" _km(long double val)
{
    return Distance(val);
}

Distance operator"" _mi(long double val)
{
    return Distance(val * Distance::km_per_mile);
}

int main()
{
    // Must have a decimal point to bind to the operator we defined!
    Distance d{ 402.0_km }; // construct using kilometers
    std::cout << "Kilometers in d: " << d.get_kilometers() << std::endl; // 402

    Distance d2{ 402.0_mi }; // construct using miles
    std::cout << "Kilometers in d2: " << d2.get_kilometers() << std::endl;  //646.956

    // add distances constructed with different units
    Distance d3 = 36.0_mi + 42.0_km;
    std::cout << "d3 value = " << d3.get_kilometers() << std::endl; // 99.9364

    // Distance d4(90.0); // error constructor not accessible

    std::string s;
    std::getline(std::cin, s);
    return 0;
}
```

Литеральное число должно иметь десятичное значение. В противном случае число будет интерпретировано как целое число, а тип не будет совместим с оператором. Для ввода с плавающей запятой тип должен быть **длинным Double**, а для целочисленных типов он должен **быть длинным**целым числом.

## <a name="raw-literals"></a>Необработанные литералы

В необработанном определяемом пользователем литерале оператор, который вы определяете, принимает литерал как последовательность значений Char. Вы можете интерпретировать эту последовательность как число или строку или другой тип. В списке операторов, приведенном ранее на этой странице, есть операторы, `_r` и `_t`, которые можно использовать для определения необработанных литералов:

```cpp
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

Необработанные литералы можно использовать для предоставления пользовательской интерпретации входной последовательности, которая отличается от нормальной работы компилятора. Например, вы можете определить литерал, преобразующий последовательность `4.75987` в пользовательский тип десятичного числа вместо типа с плавающей запятой по стандарту IEEE 754. Необработанные литералы, такие как литералы обработанные, можно также использовать для проверки входных последовательностей во время компиляции.

### <a name="example-limitations-of-raw-literals"></a>Пример: ограничения необработанных литералов

Оператор необработанного литерала и шаблон оператора литерала работают только с пользовательскими литералами, имеющими целочисленный тип или тип числа с плавающей запятой, как показано в следующем примере.

```cpp
#include <cstddef>
#include <cstdio>

// Literal operator for user-defined INTEGRAL literal
void operator "" _dump(unsigned long long int lit)
{
    printf("operator \"\" _dump(unsigned long long int) : ===>%llu<===\n", lit);
};

// Literal operator for user-defined FLOATING literal
void operator "" _dump(long double lit)
{
    printf("operator \"\" _dump(long double)            : ===>%Lf<===\n",  lit);
};

// Literal operator for user-defined CHARACTER literal
void operator "" _dump(char lit)
{
    printf("operator \"\" _dump(char)                   : ===>%c<===\n",   lit);
};

void operator "" _dump(wchar_t lit)
{
    printf("operator \"\" _dump(wchar_t)                : ===>%d<===\n",   lit);
};

void operator "" _dump(char16_t lit)
{
    printf("operator \"\" _dump(char16_t)               : ===>%d<===\n",   lit);
};

void operator "" _dump(char32_t lit)
{
    printf("operator \"\" _dump(char32_t)               : ===>%d<===\n",   lit);
};

// Literal operator for user-defined STRING literal
void operator "" _dump(const     char* lit, size_t)
{
    printf("operator \"\" _dump(const     char*, size_t): ===>%s<===\n",   lit);
};

void operator "" _dump(const  wchar_t* lit, size_t)
{
    printf("operator \"\" _dump(const  wchar_t*, size_t): ===>%ls<===\n",  lit);
};

void operator "" _dump(const char16_t* lit, size_t)
{
    printf("operator \"\" _dump(const char16_t*, size_t):\n"                  );
};

void operator "" _dump(const char32_t* lit, size_t)
{
    printf("operator \"\" _dump(const char32_t*, size_t):\n"                  );
};

// Raw literal operator
void operator "" _dump_raw(const char* lit)
{
    printf("operator \"\" _dump_raw(const char*)        : ===>%s<===\n",   lit);
};

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

    // There is no raw literal operator or literal operator template support on these types:
    //  'A'_dump_raw;
    // L'B'_dump_raw;
    // u'C'_dump_raw;
    // U'D'_dump_raw;
    //   "Hello World"_dump_raw;
    //  L"Wide String"_dump_raw;
    // u8"UTF-8 String"_dump_raw;
    //  u"UTF-16 String"_dump_raw;
    //  U"UTF-32 String"_dump_raw;
}
```

```Output
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
```
