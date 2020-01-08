---
title: Определяемые пользователем литералы (C++)
ms.date: 12/10/2019
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
ms.openlocfilehash: 31b8f1dfb261839c04a6829132975ada9c09d619
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301305"
---
# <a name="user-defined-literals"></a>Определенные пользователем литералы

Существует пять основных категорий литералов в C++: целочисленный, символьный, с плавающей запятой, строка, логическое значение и указатель.  Начиная с версии C++ 11, можно определять собственные литералы на основе этих категорий для создания синтаксических ярлыков для общих идиом и повышения безопасности типов. Например, предположим, имеется класс "Расстояние". Можно определить один литерал для километров и еще один — для миль и требовать от пользователя указывать явно единицы измерения, написав: auto d = 42,0_km или auto d = 42,0_mi. Определяемые пользователем литералы не дают выигрыша в производительности. Они служат, главным образом, для удобства и для определения типов во время компиляции. Стандартная библиотека содержит определяемые пользователем литералы для std: String, для std:: Complex и для единиц в операциях времени и длительности в заголовке \<Chrono >:

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

Имена операторов, использованные в предыдущем примере, можно заменить на любые другие. Обязательным является лишь символ подчеркивания в начале. (Только стандартная библиотека может определять литералы без подчеркивания.) Тип возвращаемого значения — это место, где выполняется настройка преобразования или другой операции, выполняемой литералом. Кроме того, все эти операторы могут быть определены как `constexpr`.

## <a name="cooked-literals"></a>Литералы с обработкой

В исходном коде любой литерал, определяемый пользователем или нет, является фактически последовательностью буквенно-цифровых символов, например, `101`, `54.7`, `"hello"` или `true`. Компилятор интерпретирует последовательность как целое число, float, const char\* строку и т. д. Определяемый пользователем литерал, принимающий в качестве входных данных любой тип, присвоенный литеральному значению, формально называется *литералом обработанные*. Все операторы, описанные выше, за исключением `_r` и `_t`, являются литералами с обработкой. Например, литерал `42.0_km` будет привязан к оператору с именем _km, имеющему сигнатуру похожую на _b, а литерал `42_km` будет привязан к оператору с сигнатурой похожей на _a.

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

Обратите внимание, что число литерала должно быть в десятичном формате. В противном случае оно будет интерпретировано как целое число и тип будет несовместим с оператором. Также обратите внимание, что для ввода с плавающей запятой тип должен быть **длинным Double**, а для целочисленных типов он должен **быть длинным**целым числом.

## <a name="raw-literals"></a>Необработанные литералы

В необработанном пользовательском литерале определяемый оператор воспринимает литерал как последовательность значений символьного типа, которую можно по-разному интерпретировать: как число, как строку или как значение другого типа. В списке операторов, приведенном ранее на этой странице, есть операторы, `_r` и `_t`, которые можно использовать для определения необработанных литералов:

```cpp
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

Необработанные литералы можно использовать для получения пользовательских интерпретаций входной последовательности, отличных от тех, которые реализовал бы компилятор. Например, вы можете определить литерал, преобразующий последовательность `4.75987` в пользовательский тип десятичного числа вместо типа с плавающей запятой по стандарту IEEE 754. Необработанные литералы, так же как и литералы с обработкой, можно использовать для выполнения проверки входных последовательностей во время компиляции.

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
