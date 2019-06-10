---
title: Улучшение соответствия C++
ms.date: 05/16/2019
description: Microsoft C++ в Visual Studio 2019 развивается в сторону полного соответствия со стандартом языка C ++ 20.
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 02b778f10ad94342c922a4e79a856cc2a7d53076
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451217"
---
# <a name="c-conformance-improvements-in-visual-studio-2019-rtw-and-version-161improvements161"></a>Улучшения соответствия C++ в Visual Studio 2019 RTW и версии [16.1](#improvements_161)

## <a name="improvements-in-visual-studio-2019-rtw"></a>Усовершенствования в Visual Studio 2019 RTW

Visual Studio 2019 RTW содержит следующие улучшения соответствия, исправления ошибок и изменения в поведении в компиляторе Microsoft C++ (MSVC).

**Примечание.** Возможности C ++ 20 будут доступны в режиме `/std:c++latest` до завершения реализации C++20 для компилятора и IntelliSense. На этом этапе будет введен режим компилятора `/std:c++20`.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Улучшенные модули поддерживают шаблоны и обнаружение ошибок

Модули теперь официально соответствуют стандарту C ++20. Улучшенная поддержка была добавлена в Visual Studio 2017 версии 15.9. Дополнительные сведения см. в разделе [Улучшенная поддержка шаблонов и обнаружение ошибок в модулях C++ MSVC 2017 версии 15.9](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Изменена спецификация типа агрегата

Спецификация типа агрегата была изменена в C++20 (см. раздел [Запрет агрегатов с объявленными пользователем конструкторами](https://wg21.link/p1008r1)). В Visual Studio 2019 в разделе `/std:c++latest` класс с любым конструктором, объявленным пользователем (например, конструктор, объявленный `= default` или `= delete`), не является агрегатом. Ранее только предоставленные пользователем конструкторы запрещали классу быть агрегатом. Это изменение накладывает дополнительные ограничения на способ инициализации таких типов.

Следующий код компилируется без ошибок в Visual Studio 2017, но вызывает ошибки C2280 и C2440 в Visual Studio 2019 в `/std:c++latest`:

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>Частичная поддержка оператора <=>

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C++20 вводит трехсторонний оператор сравнения `<=>`, также известный как "оператор — космический корабль". Visual Studio 2019 в режиме `/std:c++latest` вводит частичную поддержку оператора, вызывая ошибки синтаксиса, который сейчас запрещен. Например, следующий код компилируется без ошибок в Visual Studio 2017, но вызывает различные ошибки в Visual Studio 2019 в `/std:c++latest`:

```cpp
struct S
{
       bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };
int main(int argc, char** argv)
{
       U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

Чтобы избежать ошибок, вставляйте символ пробела в строку, вызывающую ошибку, перед последней скобкой: `U<&S::operator<= > u;`.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Ссылки на типы с несоответствием cv-квалификаторов

Ранее MSVC допускал прямую привязку ссылки из типа с несоответствием cv-квалификаторов ниже верхнего уровня. Это делало возможным изменение предположительно постоянных данных, на которые указывала ссылка, а теперь компилятор создает временные данные согласно требованиям стандарта. В Visual Studio 2017 следующий код компилировался без предупреждений. В Visual Studio 2019 компилятор выдает *предупреждение C4172: \<func:#1 "?PData@X@@QBEABQBXXZ"> возвращение адреса локальной переменной или временных данных*.

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```
### <a name="reinterpretcast-from-an-overloaded-function"></a>`reinterpret_cast` из перегруженной функции

Аргумент `reinterpret_cast` не является одним из контекстов, в которых разрешен адрес перегруженной функции. Приведенный ниже код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 выдает ошибку *C2440: невозможно выполнить преобразование из overloaded-function в fp*:

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

Чтобы избежать этой ошибки, используйте допустимые приведения для этого сценария:

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>Замыкания лямбда-выражений

В C ++ 14 типы замыкания лямбда-выражений не являются литералом. Основное последствие этого правила в том, что лямбда-выражение не может назначаться для переменной `constexpr`. Приведенный ниже код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 он вызывает ошибку *C2127: l: недопустимая инициализация сущности "constexpr" с неконстантным выражением* :

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Чтобы избежать этой ошибки, удалите квалификатор `constexpr` или измените режим совместимости на `/std:c++17`.

### <a name="stdcreatedirectory-failure-codes"></a>Коды сбоя std::create_directory

Безусловная реализация [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) из C ++ 20. Это изменяет `std::create_directory`, чтобы проверить, был ли целевой объект уже каталогом со сбоем. Ранее все ошибки типа ERROR_ALREADY_EXISTS были включены в коды "Выполнено успешно, но каталог не создан".

### <a name="operatorstdostream-nullptrt"></a>operator<<(std::ostream, nullptr_t)

Для [LWG 2221](https://cplusplus.github.io/LWG/issue2221) добавлен `operator<<(std::ostream, nullptr_t)` для записи nullptrs в потоки. 

### <a name="additional-parallel-algorithms"></a>Дополнительные параллельные алгоритмы

Новые параллельные версии `is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap` и `is_heap_until`.

### <a name="atomic-initialization"></a>Атомарная инициализация

[P0883 "Устранение атомарной инициализации"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) меняет `std::atomic`, чтобы инициализировать T по значению, а не по умолчанию. Исправление включено при использовании Clang/LLVM со стандартной библиотекой Майкрософт. В настоящее время оно отключено для компилятора Microsoft C++ в качестве обходного решения для ошибки во время обработки constexpr.

### <a name="removecvref-and-removecvreft"></a>remove_cvref и remove_cvref_t

Реализация признаков типа `remove_cvref` и `remove_cvref_t` из [P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf). Они удаляют ссылочность и cv-квалификацию из типа без ограничения функций и массивов до указателей (в отличие от `std::decay` и `std::decay_t`).

### <a name="feature-test-macros"></a>Макросы тестирования функций

[P0941R2 — макросы тестирования функций](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) завершены с поддержкой `__has_cpp_attribute`. Макросы для тестирования функций поддерживаются во всех стандартных режимах.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Запрет агрегирования с объявленными пользователем конструкторами

[C++ 20 P1008R1 — запрет агрегирования с объявленными пользователем конструкторами](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) завершен.

## <a name="improvements_161"></a> Усовершенствования в Visual Studio 2019 версии 16.1

### <a name="char8t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C ++ 20 добавляет новый тип символа, который используется для представления частей кода UTF-8. Строковые литералы U8 в C ++ 20 имеют тип `const char8_t[N]` вместо `const char[N]`, как раньше. Аналогичные изменения предложены для стандарта C в [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm). Рекомендации по обеспечению обратной совместимости с char8_t приведены в [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html). Компилятор Microsoft C++ добавляет поддержку char8_t в Visual Studio 2019 версии 16.1 при указании параметра компилятора **/Zc:char8_t**. В будущем он будет поддерживаться с [/std:c++latest](../../build/reference/std-specify-language-standard-version.md), который можно отменить, чтобы восстановить поведение C ++ 17 с помощью **/Zc:char8_t-** . Компилятор EDG, лежащий в основе IntelliSense, пока не поддерживает это, поэтому возникают ложные ошибки только для IntelliSense, которые не влияют на фактическую компиляцию.

#### <a name="example"></a>Пример

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtypeidentity-metafunction-and-stdidentity-function-object"></a>Метафункция std::type_identity и объект функции std::identity

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). Устаревшее расширение класса шаблонов `std::identity` было удалено и заменено на метафункцию `std::type_identity` и объект функции `std::identity` в C++20. Они доступны только в [/std:c++latest](../../build/reference/std-specify-language-standard-version.md). 

В следующем примере становится устаревшим предупреждение C4996 для `std::identity` (определено в \<type_traits>) в Visual Studio 2017: 

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

В следующем примере показано, как использовать новый `std::identity` (определено в \<functional>) вместе с новым `std::type_identity`:

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Проверка синтаксиса для универсальных лямбда-выражений

Новый обработчик лямбда-выражений включает некоторые проверки синтаксиса режима совместимости в универсальных лямбда-выражениях в [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) или в другом режиме языка с **/experimental:newLambdaProcessor**. 

В Visual Studio 2017 этот код компилируется без предупреждений, но в Visual Studio 2019 возникает ошибка *C2760 синтаксическая ошибка: непредвиденный токен "\<id-expr>", ожидается "id-expression"* :

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

В следующем примере показан правильный синтаксис, который теперь применяется компилятором принудительно:

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>Зависящий от аргументов поиск вызовов функций

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html) (C++20). Улучшена возможность поиска шаблонов функций с помощью зависящего от аргументов поиска выражений вызова функции с явно заданными аргументами шаблона. Требуется **/std:c++latest**.

### <a name="designated-initialization"></a>Назначенная инициализация

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf) (C++20). Назначенная инициализация позволяет выбирать определенные члены в агрегатной инициализации с помощью синтаксиса `Type t { .member = expr }`. Требуется **/std:c++latest**.

### <a name="new-and-updated-standard-library-functions-c20"></a>Новые и обновленные функции стандартной библиотеки (C++20)

- `starts_with()` и `ends_with()` для `basic_string` и `basic_string_view`.
- `contains()` для ассоциативных контейнеров;
- `remove()`, `remove_if()` и `unique()` для ` list` и `forward_list` теперь возвращают `size_type`.
- `shift_left()` и `shift_right()` добавлены к \<algorithm>.

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-rtw"></a>Исправления ошибок и изменения в поведении в Visual Studio 2019 RTW

### <a name="correct-diagnostics-for-basicstring-range-constructor"></a>Правильная диагностика для конструктора диапазонов basic_string

В Visual Studio 2019 конструктор диапазонов `basic_string` больше не подавляет диагностику компилятора с помощью `static_cast`. Приведенный ниже код компилируется без предупреждений в Visual Studio 2017, несмотря на возможную потерю данных при преобразовании из `wchar_t` в `char` при инициализации `out`:

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 корректно выдает предупреждение *C4244: "argument": преобразование из "wchar_t" в "const _Elem", возможна потеря данных*. Чтобы избежать этого предупреждения, можно инициализировать std::string, как показано в следующем примере:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>Неправильные вызовы += и-= в /clr or /ZW теперь корректно обнаруживаются

В Visual Studio 2017 возникла ошибка, из-за которой компилятор автоматически пропускал ошибки и не создавал код для недопустимых вызовов += и-= с `/clr` или `/ZW`. Следующий код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 корректно вызывает *ошибку C2845: 'System::String ^': расчеты с указателями недопустимы для этого типа*:

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Чтобы избежать данной ошибки в этом примере, используйте оператор с методом ToString(): `s += E::e.ToString();`.

### <a name="initializers-for-inline-static-data-members"></a>Инициализаторы для встроенных статических элементов данных

Доступ к недопустимым элементам в `inline` и `static constexpr` теперь определяется правильно. Следующий пример компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 в режиме `/std:c++17` он выдает *ошибку C2248: не удается обратиться к закрытому элементу, объявленному в классе X*.

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

Чтобы избежать этой ошибки, объявите элемент `X::c` как защищенный:

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>Возобновлено использование C4800

MSVC выдавал предупреждение о производительности C4800 о неявном преобразовании в bool, которое было слишком назойливым и не отключалось, поэтому мы удалили его в Visual Studio 2017. Но за время работы Visual Studio 2017 мы получили множество отзывов о полезности этого предупреждения. Мы вернули в Visual Studio 2019 тщательно настроенное предупреждение C4800 с сопутствующим C4165, и их можно легко отключить с помощью явного приведения или сравнения с 0 соответствующего типа. C4800 — это по умолчанию отключенное предупреждение уровня 4, а C4165 — это по умолчанию отключенное предупреждение уровня 3. Их можно обнаружить с помощью параметра компилятора `/Wall`.

В следующем примере возникают предупреждения C4800 и C4165 в режиме `/Wall`:

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

Чтобы избежать предупреждений в предыдущем примере, можно написать следующий код:

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>Функция-член локального класса не имеет тела

В Visual Studio 2017 предупреждение *C4822: функция-член локального класса не имеет тела* возникает только тогда, когда параметр компилятора `/w14822` явно не задан; он не отображается с `/Wall`. В Visual Studio 2019 C4822 является предупреждением, отключенным по умолчанию, которое можно обнаружить в `/Wall` без явного задания `/w14822`.

```cpp
void foo()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>Тела шаблонов функций, содержащие операторы constexpr if

Для тел шаблонов функций, содержащих операторы `if constexpr`, включены некоторые проверки `/permissive-`, связанные с синтаксическим анализом. Например, в Visual Studio 2017 следующий код вызывает предупреждение C*7510: 'Type': имя зависимого типа должно иметь префикс "typename"* , только если параметр `/permissive-` не задан. В Visual Studio 2019 тот же код вызывает ошибки независимо от того, задан ли параметр `/permissive-`:

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}

```

Чтобы избежать этой ошибки, добавьте ключевое слово `typename` в объявление `a`: `typename T::Type a;`.

### <a name="inline-assembly-code-is-not-supported-in-a-lambda-expression"></a>Встроенный код сборки не поддерживается в лямбда-выражении

Недавно команда Visual C++ узнала о проблеме безопасности, из-за которой использование встроенного ассемблера в лямбда-выражении могло привести к повреждению "ebp" (регистра обратного адреса) во время выполнения. Злоумышленник сможет воспользоваться этим сценарием. Учитывая характер проблемы, тот факт, что встроенный ассемблер поддерживается только на x86, а также слабое взаимодействие встроенного ассемблера с остальной частью компилятора, было решено, что лучшим решением этой проблемы будет запрет встроенного ассемблера в лямбда-выражении.

Примечание: мы нашли только одно использование встроенного ассемблера в лямбда-выражении, и целью было получить обратный адрес. В этом сценарии можно получить обратный адрес на всех платформах, просто используя `_ReturnAddress()` в компиляторе.

В приведенном ниже коде возникает предупреждение *C7552: встроенный ассемблер не поддерживается в лямбда-выражении* в Visual Studio 2017 15.9 и Visual Studio 2019:

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

Чтобы избежать этой ошибки, переместите код сборки в именованную функцию, как показано в следующем примере:

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmoveiterator"></a>Отладка итераторов и std::move_iterator

Функция отладки итераторов теперь может правильно развертывать `std::move_iterator`. Например, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` теперь использует быстрый путь `memcpy`.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>Исправления для принудительного применения ключевого слова \<xkeycheck.h >

Применение ключевого слова в стиле макроса стандартной библиотеки \<xkeycheck.h> было исправлено, чтобы выдавать ключевое слово фактически обнаруженной проблемы вместо сообщения общего характера. Также поддерживаются ключевые слова C ++ 20, а IntelliSense не сообщает, что случайные ключевые слова являются макросами.

### <a name="allocator-types-un-deprecated"></a>Типы распределителя больше не считаются нерекомендуемыми

`std::allocator<void>`, `std::allocator::size_type` и `std::allocator::difference_type` больше не считаются нерекомендуемыми.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Правильное предупреждение для сужающих преобразований строк

Ложный `static_cast`, не вызывающийся по стандарту, который случайно отключает предупреждения о сужении C4244, был удален из std::string. Попытка вызова `std::string::string(const wchar_t*, const wchar_t*)` теперь правильно вызывает предупреждение *C4244: "сужение wchar_t до char."*

### <a name="various-filesystem-correctness-fixes"></a>Различные исправления правильности \<filesystem>

- Исправлен сбой `std::filesystem::last_write_time` при попытке изменить последнее время записи каталога.
- Теперь конструктор `std::filesystem::directory_entry` сохраняет результат сбоя, а не создает исключение, если задан несуществующий целевой путь.
- Версия `std::filesystem::create_directory` с двумя параметрами была изменена для вызова версии с одним параметром, так как базовая функция `CreateDirectoryExW` выполняла бы `copy_symlink`, если бы existing_p был символьной ссылкой.
- `std::filesystem::directory_iterator` больше не завершается сбоем при обнаружении неработающей символьной ссылки.
- `std::filesystem::space` теперь принимает относительные пути.
- `std::filesystem::path::lexically_relative` больше не путается из-за конечных знаков косой черты, как сообщалось в [LWG 3096](https://cplusplus.github.io/LWG/issue3096).
- Найдено обходное решение для проблемы, при которой `CreateSymbolicLinkW` отклонял пути с символами косой черты в `std::filesystem::create_symlink`.
- Найдено обходное решение проблемы, при которой функция `delete` режима удаления POSIX существовала в Windows 10 LTSB 1609, но фактически не могла удалять файлы.
- Конструкторы копий `std::boyer_moore_searcher` и `std::boyer_moore_horspool_searcher` и операторы присваивания копий теперь действительно копируют элементы.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Параллельные алгоритмы в Windows 8 и более поздних версий

Библиотека параллельных алгоритмов теперь правильно использует реальное семейство `WaitOnAddress` в Windows 8 и более поздних версий вместо того, чтобы всегда использовать Windows 7 и более ранние фиктивные версии.

### <a name="stdsystemcategorymessage-whitespace"></a>Пробел в std::system_category::message()

`std::system_category::message()` теперь удаляет конечный пробел из возвращенного сообщения.

### <a name="stdlinearcongruentialengine-divide-by-zero"></a>std::linear_congruential_engine — деление на ноль

Некоторые условия, приводящие к тому, что `std::linear_congruential_engine` вызывает деление на ноль, были исправлены.

### <a name="fixes-for-iterator-unwrapping"></a>Исправления для распаковывания итератора

Система распаковывания итератора, впервые предоставленная для интеграции пользователя и программиста в Visual Studio 2017 15.8 (как описано в разделе https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/), больше не распаковывает итераторы, производные от итераторов стандартных библиотек. Например, пользователь, который происходит от `std::vector<int>::iterator` и пытается настроить поведение, теперь получает настроенное поведение при вызове алгоритмов стандартной библиотеки, а не поведение указателя.
Функция резерва неупорядоченного контейнера теперь действительно резервирует его для N элементов, как описано в [LWG 2156](https://cplusplus.github.io/LWG/issue2156).

### <a name="time-handling"></a>Обработка времени

- Ранее некоторые значения времени, которые передавались в библиотеку параллелизма, вызывали переполнение, например `condition_variable::wait_for(seconds::max())`. Эти переполнения, теперь исправленные, изменяли поведение для кажущегося случайным 29-дневного цикла (когда uint32_t миллисекунд принимались переполненными API Win32).

- Заголовок <ctime> теперь правильно объявляет timespec и timespec_get в пространстве имен std помимо их объявления в глобальном пространстве имен.

### <a name="various-fixes-for-containers"></a>Различные исправления для контейнеров

- Многие функции внутреннего контейнера стандартной библиотеки стали закрытыми для повышения эффективности IntelliSense. В последующих выпусках MSVC ожидаются дополнительные исправления для пометки членов закрытыми.

- Проблемы правильности безопасности исключения, при которых контейнеры на основе узла, например `list`, `map` и `unordered_map`, повреждались, теперь исправлены. Во время операции переназначения `propagate_on_container_copy_assignment` или `propagate_on_container_move_assignment` мы освобождаем граничный узел контейнера с помощью старого распределителя, выполняем назначение POCCA/POCMA в старом распределителе, а затем пробуем получить граничный узел из нового распределителя. Если это распределение не удалось, контейнер поврежден и не может даже быть уничтожен, поскольку обладание граничным узлом является инвариантной жесткой структурой данных. Это было исправлено, чтобы выделять новый граничный узел из распределителя исходного контейнера перед удалением существующего граничного узла.

- Контейнеры были исправлены и всегда копируют, перемещают или меняют распределители согласно `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment` и `propagate_on_container_swap` даже для распределителей, объявленных `is_always_equal`.

- Добавлены перегрузки для функций-членов слияния и извлечения контейнеров, которые принимают контейнеры rvalue в соответствии с [P0083 "Соединение карт и наборов"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)

### <a name="stdbasicistreamread-processing-of-rn--n"></a>std::basic_istream::read — обработка \r\n => \n

`std::basic_istream::read` исправлен, чтобы не делать временные записи в части предоставленного буфера в рамках обработки \r\n => \n. Это сокращает некоторые преимущества производительности, полученные в Visual Studio 2017 15.8 для операций чтения размером более 4 КБ, но повышение эффективности сохраняется благодаря тому, что удается избежать трех виртуальных вызовов на символ.

### <a name="stdbitset-constructor"></a>Конструктор std::bitset

Конструктор `std::bitset` больше не считывает единицы и нули в обратном порядке для больших наборов битов.

### <a name="stdpairoperator-regression"></a>Регрессия std::pair::operator=

Исправлена регрессия в операторе присваивания `std::pair`, которая появилась при реализации [LWG 2729 "Отсутствует SFINAE для std::pair::operator="](https://cplusplus.github.io/LWG/issue2729). Теперь снова правильно принимаются типы, которые можно преобразовывать в `std::pair`.

### <a name="non-deduced-contexts-for-addconstt"></a>Невыводимые контексты для add_const_t

Исправлена ошибка признаков дополнительного типа, где `add_const_t` и связанные функции должны быть невыводимым контекстом. Другими словами, `add_const_t` должен быть псевдонимом для `typename add_const<T>::type`, а не `const T`.

## <a name="see-also"></a>См. также

[Новые возможности Visual Studio 2019](../what-s-new-for-visual-cpp-in-visual-studio.md)