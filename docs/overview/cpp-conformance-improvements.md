---
title: Улучшение соответствия C++
ms.date: 06/14/2019
description: Microsoft C++ в Visual Studio развивается в сторону полного соответствия стандарту языка C++20.
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 1652c7ab9a48de65b32123b34c3231a0b06a410a
ms.sourcegitcommit: 0ad35b26e405bbde17dc0bd0141e72f78f0a38fb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2019
ms.locfileid: "67194766"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Улучшения соответствия C++ в Visual Studio

В каждом выпуске Microsoft C++ добавляются улучшения соответствия и исправления ошибок. В этой статье перечислены улучшения в разбивке по основным выпускам и версиям системы. Также здесь перечислены основные исправления ошибок в разбивке по версиям. Чтобы перейти непосредственно к изменениям в конкретной версии, используйте список из **этой статьи**.

::: moniker range=">=vs-2019"

## <a name="improvements_160"></a> Усовершенствования в Visual Studio 2019 RTW (версия 16.0)

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

### <a name="partial-support-for-operator-"></a>Частичная поддержка для `operator <=>`

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

Чтобы избежать этих ошибок, добавьте символ пробела в строку, вызывающую ошибку, перед последней скобкой: `U<&S::operator<= > u;`.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Ссылки на типы с несоответствием cv-квалификаторов

Ранее MSVC допускал прямую привязку ссылки из типа с несоответствием cv-квалификаторов ниже верхнего уровня. Это делало возможным изменение предположительно постоянных данных, на которые указывала ссылка. Теперь компилятор создает временные данные согласно требованиям стандарта. В Visual Studio 2017 следующий код компилировался без предупреждений. В Visual Studio 2019 компилятор выдает *предупреждение C4172: \<func:#1 "?PData@X@@QBEABQBXXZ"> возвращение адреса локальной переменной или временных данных*.

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

В C++14 типы замыкания лямбда-выражений не являются литералами. Основное последствие этого правила в том, что лямбда-выражение не может назначаться для переменной `constexpr`. Приведенный ниже код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 он вызывает ошибку *C2127: l: недопустимая инициализация сущности "constexpr" с неконстантным выражением*:

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Чтобы избежать этой ошибки, удалите квалификатор `constexpr` или измените режим совместимости на `/std:c++17`.

### <a name="stdcreatedirectory-failure-codes"></a>Коды сбоя `std::create_directory`

Безусловная реализация [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) из C ++ 20. Это изменяет `std::create_directory`, чтобы проверить, был ли целевой объект уже каталогом со сбоем. Ранее все ошибки типа ERROR_ALREADY_EXISTS были включены в коды "Выполнено успешно, но каталог не создан".

### `operator<<(std::ostream, nullptr_t)`

Для [LWG 2221](https://cplusplus.github.io/LWG/issue2221) добавлен `operator<<(std::ostream, nullptr_t)` для записи nullptrs в потоки.

### <a name="additional-parallel-algorithms"></a>Дополнительные параллельные алгоритмы

Новые параллельные версии `is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap` и `is_heap_until`.

### <a name="atomic-initialization"></a>Атомарная инициализация

[P0883 "Устранение атомарной инициализации"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) меняет `std::atomic`, чтобы инициализировать T по значению, а не по умолчанию. Это исправление включается при использовании Clang/LLVM со стандартной библиотекой Майкрософт. В настоящее время оно отключено для компилятора Microsoft C++ в качестве обходного решения для ошибки во время обработки `constexpr`.

### <a name="removecvref-and-removecvreft"></a>`remove_cvref` и `remove_cvref_t`

Реализация признаков типа `remove_cvref` и `remove_cvref_t` из [P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf). Они удаляют ссылочность и cv-квалификацию из типа без ограничения функций и массивов до указателей (в отличие от `std::decay` и `std::decay_t`).

### <a name="feature-test-macros"></a>Макросы тестирования функций

[P0941R2 — макросы тестирования функций](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) завершены с поддержкой `__has_cpp_attribute`. Макросы тестирования функций поддерживаются во всех стандартных режимах.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Запрет агрегирования с объявленными пользователем конструкторами

[C++ 20 P1008R1 — запрет агрегирования с объявленными пользователем конструкторами](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) завершен.

## <a name="improvements_161"></a> Усовершенствования в Visual Studio 2019 версии 16.1

### <a name="char8t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C ++ 20 добавляет новый тип символа, который используется для представления частей кода UTF-8. Строковые литералы `u8` в C++20 имеют тип `const char8_t[N]`, а не `const char[N]`, как было раньше. Аналогичные изменения предложены для стандарта C в [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm). Рекомендации по обеспечению обратной совместимости для `char8_t` приведены в [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html). Компилятор Microsoft C++ добавляет поддержку `char8_t` в Visual Studio 2019 версии 16.1, если вы укажете параметр компилятора **/Zc:char8_t**. В будущем он будет поддерживаться с [/std:c++latest](../build/reference/std-specify-language-standard-version.md), который можно отменить, чтобы восстановить поведение C ++ 17 с помощью **/Zc:char8_t-** . Компилятор EDG, лежащий в основе IntelliSense, пока не поддерживает эту возможность, поэтому возникают ложные ошибки для IntelliSense, которые не влияют на фактическую компиляцию.

#### <a name="example"></a>Пример

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtypeidentity-metafunction-and-stdidentity-function-object"></a>Метафункция std::type_identity и объект функции std::identity

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). Устаревшее расширение класса шаблонов `std::identity` было удалено и заменено на метафункцию `std::type_identity` и объект функции `std::identity` в C++20. Они доступны только в [/std:c++latest](../build/reference/std-specify-language-standard-version.md).

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

Новый обработчик лямбда-выражений включает некоторые проверки синтаксиса режима совместимости в универсальных лямбда-выражениях в [/std:c++latest](../build/reference/std-specify-language-standard-version.md) или в другом режиме языка с **/experimental:newLambdaProcessor**.

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
- `remove()`, `remove_if()` и `unique()` для `list` и `forward_list` теперь возвращают `size_type`;
- `shift_left()` и `shift_right()` добавлены к \<algorithm>.

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019"></a>Исправления ошибок и изменения в поведении в Visual Studio 2019

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

В Visual Studio 2017 появилась ошибка, из-за которой компилятор пропускал ошибки без предупреждений и не создавал код для недопустимых вызовов += и –= в `/clr` или `/ZW`. Следующий код компилируется без ошибок в Visual Studio 2017, но в Visual Studio 2019 корректно вызывает *ошибку C2845: 'System::String ^': расчеты с указателями недопустимы для этого типа*:

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

В MSVC ранее создавалось предупреждение о производительности C4800 для неявных преобразований в `bool`. Это предупреждение было слишком назойливым и его нельзя было отключить, в результате чего мы решили удалить его в Visual Studio 2017. Но за время работы Visual Studio 2017 мы получили множество отзывов о полезности этого предупреждения. В выпуске Visual Studio 2019 мы возвращаем предупреждение C4800, тщательно настроив его и дополнив пояснительным предупреждением C4165. Обоих предупреждений можно легко избежать с помощью явного приведения типов или сравнения со значением 0 соответствующего типа. C4800 — это по умолчанию отключенное предупреждение уровня 4, а C4165 — это по умолчанию отключенное предупреждение уровня 3. Их можно обнаружить с помощью параметра компилятора `/Wall`.

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
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>Тела шаблонов функций, содержащие операторы constexpr if

Для тел шаблонов функций, содержащих операторы `if constexpr`, включены некоторые проверки `/permissive-`, связанные с синтаксическим анализом. Например, в Visual Studio 2017 следующий код вызывает предупреждение C*7510: Type: имя зависимого типа должно дополняться префиксом "typename"* только в том случае, если параметр `/permissive-` не задан. В Visual Studio 2019 тот же код вызывает ошибки независимо от того, задан ли параметр `/permissive-`:

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

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Встроенный код сборки не поддерживается в лямбда-выражении

Недавно команда Visual C++ узнала о проблеме безопасности, из-за которой использование встроенного ассемблера в лямбда-выражении могло привести к повреждению `ebp` (регистра обратного адреса) во время выполнения. Злоумышленник может воспользоваться этим сценарием. Учитывая характер проблемы, тот факт, что встроенный ассемблер поддерживается только на x86, а также слабое взаимодействие встроенного ассемблера с остальной частью компилятора, для решения этой проблемы был выбран самый безопасный путь: запрет встроенного ассемблера в лямбда-выражении.

Мы нашли "в реальной жизни" только один вариант применения встроенного ассемблера в лямбда-выражении, а именно получение обратного адреса. В этом сценарии можно получить обратный адрес на всех платформах, просто используя `_ReturnAddress()` в компиляторе.

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

### <a name="iterator-debugging-and-stdmoveiterator"></a>Отладка перечислителя и `std::move_iterator`

Функция отладки итераторов теперь может правильно развертывать `std::move_iterator`. Например, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` теперь использует быстрый путь `memcpy`.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>Исправления для принудительного применения ключевого слова \<xkeycheck.h >

Применение ключевого слова в стиле макроса стандартной библиотеки \<xkeycheck.h> было исправлено, чтобы выдавать ключевое слово фактически обнаруженной проблемы вместо сообщения общего характера. Также поддерживаются ключевые слова C ++ 20, а IntelliSense не сообщает, что случайные ключевые слова являются макросами.

### <a name="allocator-types-no-longer-deprecated"></a>Типы распределителей теперь не считаются нерекомендуемыми

`std::allocator<void>`, `std::allocator::size_type` и `std::allocator::difference_type` теперь не считаются нерекомендуемыми.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Правильное предупреждение для сужающих преобразований строк

Лишний вызов `static_cast`, который не соответствовал стандарту и случайно отключал предупреждения о сужении C4244, был удален из `std::string`. Попытка вызова `std::string::string(const wchar_t*, const wchar_t*)` теперь правильно вызывает предупреждение *C4244: "сужение wchar_t до char."*

### <a name="various-filesystem-correctness-fixes"></a>Различные исправления правильности \<filesystem>

- Исправлен сбой `std::filesystem::last_write_time` при попытке изменить последнее время записи каталога.
- Теперь конструктор `std::filesystem::directory_entry` сохраняет результат сбоя, а не создает исключение, если задан несуществующий целевой путь.
- Версия `std::filesystem::create_directory` с двумя параметрами была изменена для вызова версии с одним параметром, так как базовая функция `CreateDirectoryExW` использовала бы `copy_symlink`, если бы `existing_p` был символьной ссылкой.
- `std::filesystem::directory_iterator` больше не завершается сбоем при обнаружении неработающей символьной ссылки.
- `std::filesystem::space` теперь принимает относительные пути.
- `std::filesystem::path::lexically_relative` больше не путается из-за конечных знаков косой черты, как сообщалось в [LWG 3096](https://cplusplus.github.io/LWG/issue3096).
- Найдено обходное решение для проблемы, при которой `CreateSymbolicLinkW` отклонял пути с символами косой черты в `std::filesystem::create_symlink`.
- Найдено обходное решение проблемы, при которой функция `delete` режима удаления POSIX существовала в Windows 10 LTSB 1609, но фактически не могла удалять файлы.
- Конструкторы копий `std::boyer_moore_searcher` и `std::boyer_moore_horspool_searcher` и операторы присваивания копий теперь действительно копируют элементы.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Параллельные алгоритмы в Windows 8 и более поздних версий

Библиотека параллельных алгоритмов теперь правильно использует реальное семейство `WaitOnAddress` в Windows 8 и более поздних версий вместо того, чтобы всегда использовать Windows 7 и более ранние фиктивные версии.

### <a name="stdsystemcategorymessage-whitespace"></a>Пробелы в `std::system_category::message()`

`std::system_category::message()` теперь удаляет конечный пробел из возвращенного сообщения.

### <a name="stdlinearcongruentialengine-divide-by-zero"></a>Деление на ноль в `std::linear_congruential_engine`

Некоторые условия, приводящие к тому, что `std::linear_congruential_engine` вызывает деление на ноль, были исправлены.

### <a name="fixes-for-iterator-unwrapping"></a>Исправления для распаковывания итератора

Система распаковывания итератора, впервые предоставленная для интеграции пользователя и программиста в Visual Studio 2017 15.8 (как описано в записи блога [STL Features and Fixes in VS 2017 15.8](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/) (Функции STL и исправления ошибок в VS 2017 15.8), больше не распаковывает итераторы, производные от итераторов стандартных библиотек. Например, пользователь, который происходит от `std::vector<int>::iterator` и пытается настроить поведение, теперь получает настроенное поведение при вызове алгоритмов стандартной библиотеки, а не поведение указателя.

Функция неупорядоченного контейнера `reserve` теперь действительно резервирует N элементов, как описано в [LWG 2156](https://cplusplus.github.io/LWG/issue2156).

### <a name="time-handling"></a>Обработка времени

- Ранее некоторые значения времени, которые передавались в библиотеку параллелизма, вызывали переполнение, например `condition_variable::wait_for(seconds::max())`. Эти исправленные переполнения ранее изменяли поведение псевдослучайным образом в течение 29-дневного цикла (когда значение миллисекунд uint32_t принималось с переполнением в базовые API Win32).

- Заголовок <ctime> теперь правильно объявляет `timespec` и `timespec_get` в пространстве имен `std`, а не только в глобальном пространстве имен.

### <a name="various-fixes-for-containers"></a>Различные исправления для контейнеров

- Многие функции внутреннего контейнера стандартной библиотеки стали закрытыми для повышения эффективности IntelliSense. В последующих выпусках MSVC ожидаются дополнительные исправления, которые позволят объявлять элементы закрытыми.

- Проблемы правильности безопасности исключения, при которых контейнеры на основе узла, например `list`, `map` и `unordered_map`, повреждались, теперь исправлены. Во время операции переназначения `propagate_on_container_copy_assignment` или `propagate_on_container_move_assignment` мы освобождаем граничный узел контейнера с помощью старого распределителя, выполняем назначение POCCA/POCMA в старом распределителе, а затем пробуем получить граничный узел из нового распределителя. Если это распределение не удавалось, контейнер становился поврежденным и не мог даже быть уничтожен, поскольку обладание граничным узлом является инвариантной жесткой структурой данных. Этот код был исправлен так, чтобы выделять новый граничный узел из распределителя исходного контейнера перед удалением существующего граничного узла.

- Контейнеры были исправлены и всегда копируют, перемещают или меняют распределители согласно `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment` и `propagate_on_container_swap` даже для распределителей, объявленных `is_always_equal`.

- Добавлены перегрузки для функций-членов слияния и извлечения контейнеров, которые принимают контейнеры rvalue в соответствии с [P0083 "Соединение карт и наборов"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)

### <a name="stdbasicistreamread-processing-of-rn--n"></a>Обработка \\r\\n => \\n в `std::basic_istream::read`

`std::basic_istream::read` исправлен так, чтобы не записывать временные данные в части предоставленного буфера при обработке операции \\r\\n => \\n. Это изменение несколько нивелирует преимущество в производительности, достигнутое в Visual Studio 2017 15.8 для операций чтения размером более 4 КБ. Но при этом сохраняется повышенная эффективность за счет избавления от трех виртуальных вызовов на каждый символ.

### <a name="stdbitset-constructor"></a>Конструктор `std::bitset`

Конструктор `std::bitset` теперь не считывает единицы и нули в обратном порядке для больших наборов битов.

### <a name="stdpairoperator-regression"></a>Регрессия в `std::pair::operator=`

Исправлена регрессия в операторе присваивания `std::pair`, которая появилась при реализации [LWG 2729 "Отсутствует SFINAE для std::pair::operator="](https://cplusplus.github.io/LWG/issue2729). Теперь снова правильно принимаются типы, которые можно преобразовывать в `std::pair`.

### <a name="non-deduced-contexts-for-addconstt"></a>Невыводимые контексты для `add_const_t`

Исправлена ошибка признаков дополнительного типа, где `add_const_t` и связанные функции должны быть невыводимым контекстом. Другими словами, `add_const_t` должен быть псевдонимом для `typename add_const<T>::type`, а не `const T`.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="improvements_150"></a> Усовершенствования в Visual Studio 2017 RTW (версия 15.0)

Благодаря поддержке обобщенного `constexpr` и NSDMI (нестатическая инициализация элементов данных) для статистических выражений, компилятор Microsoft C++ в Visual Studio 2017 теперь включает все функции, добавленные в стандарте C++14. Обратите внимание, что в компиляторе по-прежнему отсутствуют несколько функций из стандартов C++11 и C++98. Сведения о текущем состоянии компилятора см. в статье [Соответствие стандартам языка Visual C++](../visual-cpp-language-conformance.md).

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++11 Поддержка выражения SFINAE в большем числе библиотек

Мы продолжаем улучшать в компиляторе Visual C++ поддержку SFINAE в выражениях. Это необходимо для определения и замены аргументов шаблонов, когда выражения `decltype` и `constexpr` могут выступать в качестве параметров шаблонов. Дополнительные сведения см. в разделе [Усовершенствования выражения SFINAE в версии-кандидате Visual Studio 2017](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

### <a name="c14-nsdmi-for-aggregates"></a>C++14: NSDMI для статистических выражений

Статистическое выражение — это массив или класс без предоставленного пользователем конструктора, без закрытых или защищенных нестатических данных-членов, без базовых классов и виртуальных функций. Начиная с версии C++14, статистические выражения могут содержать инициализаторы членов. Дополнительные сведения см. в разделе [Инициализаторы членов и статистические выражения](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

### <a name="c14-extended-constexpr"></a>C++14: Расширенный `constexpr`

Выражения, объявленные как `constexpr`, теперь могут содержать определенные виды объявлений, операторы if и switch, операторы циклов, а также изменения объектов, время существования которых началось с вычисления выражения constexpr. Кроме того, теперь не требуется, чтобы нестатическая функция-член `constexpr` явным образом была `const`. Дополнительные сведения см. в статье [Нестрогие ограничения для функций constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html).

### <a name="c17-terse-staticassert"></a>C++17 Сжатое `static_assert`

Параметр сообщения для `static_assert` является необязательным. Дополнительные сведения см. в разделе [Расширение static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

### <a name="c17-fallthrough-attribute"></a>C++17: атрибут `[[fallthrough]]`

В режиме **/std:c++17** атрибут `[[fallthrough]]` можно использовать в контексте операторов switch как указание для компилятора передать управление вниз. Этот атрибут позволит избежать вывода предупреждений компилятора в таких ситуациях. Дополнительные сведения см. в разделе [Формулировка для атрибута \[\[fallthrough\]\]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

### <a name="generalized-range-based-for-loops"></a>Обобщенный цикл for на основе диапазона

Циклы for на основе диапазона больше не требуют, чтобы `begin()` и `end()` возвращали объекты одного типа. Это изменение позволяет `end()` возвращать граничную метку согласно использованию в диапазонах [range-v3](https://github.com/ericniebler/range-v3) и технической спецификации по диапазонам (которая уже готова, но еще не опубликована). Дополнительные сведения см. в разделе [Обобщение цикла For на основе диапазона](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a> Усовершенствования в Visual Studio 2017 версии 15.3

### <a name="constexpr-lambdas"></a>Лямбда-выражения constexpr

Лямбда-выражения теперь можно использоваться в константных выражениях. Дополнительные сведения см. в разделе [Лямбда-выражения constexpr на C++](../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>`if constexpr` в шаблонах функций

Шаблон функции может содержать операторы `if constexpr` для выполнения ветвления во время компиляции. Дополнительные сведения см. в разделе [Операторы if constexpr](../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Операторы выбора с инициализаторами

Оператор `if` может включать инициализатор, который вводит переменную в области видимости блока внутри самого оператора. Дополнительные сведения см. в разделе [Операторы if с инициализатором](../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybeunused-and-nodiscard-attributes"></a>Атрибуты `[[maybe_unused]]` и `[[nodiscard]]`

Новый атрибут `[[maybe_unused]]` подавляет предупреждения о неиспользовании сущности. Атрибут `[[nodiscard]]` создает предупреждение, если при вызове функции отбрасывается возвращаемое значение. Дополнительные сведения см. в статье [Attributes in C++](../cpp/attributes.md) (Атрибуты в C++).

### <a name="using-attribute-namespaces-without-repetition"></a>Использование пространств имен атрибутов без повторения

Новый синтаксис позволяет включать в список атрибутов всего один идентификатор пространства имен. Дополнительные сведения см. в статье [Attributes in C++](../cpp/attributes.md) (Атрибуты в C++).

### <a name="structured-bindings"></a>Структурированные привязки

Теперь можно одним объявлением сохранить значение с отдельными именами компонентов, когда значение является массивом, `std::tuple` или `std::pair`, либо когда все его нестатические элементы данных являются открытыми. Дополнительные сведения см. в разделах [Структурированные привязки](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) и [Возврат нескольких значений из функции](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Правила создания для значений `enum class`

Теперь происходит неявное и несужающее преобразование из базового типа перечисления в области в само перечисление, когда определение перечисления не вводит перечислитель, а источник перечисления использует синтаксис инициализации списка. Дополнительные сведения см. в разделе [Правила конструкции значений класса перечисления](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) и [Перечисления](../cpp/enumerations-cpp.md#no_enumerators).

### <a name="capturing-this-by-value"></a>Захват `*this` по значению

Теперь лямбда-выражение может обращаться к объекту `*this` по значению. Это позволяет использовать лямбда-выражения в сценариях с параллельными и асинхронными операциями, особенно на новых архитектурах компьютеров. Дополнительные сведения см. в документе о [захвате объекта \*this по значению в виде \[=,\*this\] в лямбда-выражении](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html).

### <a name="removing-operator-for-bool"></a>Удаление `operator++` для `bool`

`operator++` для типов `bool` больше не поддерживается. Дополнительные сведения см. в документе об [удалении устаревшего объекта operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

### <a name="removing-deprecated-register-keyword"></a>Удаление нерекомендуемого ключевого слова `register`

Ключевое слово `register`, ранее признанное нерекомендуемым (и игнорируемое компилятором), теперь удалено из языка. Дополнительные сведения см. в документе об [удалении нерекомендуемого ключевого слова register](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

## <a name="improvements_155"></a> Усовершенствования в Visual Studio 2017 версии 15.5

Функции, отмеченные как \[14], доступны без дополнительных условий даже в режиме **/std:c++14**.

### <a name="new-compiler-switch-for-extern-constexpr"></a>Новый параметр компилятора для `extern constexpr`

В более ранних версиях Visual Studio компилятор всегда обеспечивал переменной `constexpr` внутреннюю компоновку даже в том случае, когда переменная была помечена как `extern`. В Visual Studio 2017 версии 15.5 новый параметр компилятора [/Zc:externConstexpr](../build/reference/zc-externconstexpr.md) обеспечивает правильное поведение, соответствующее стандартам. Дополнительные сведения см. в разделе о [компоновке extern constexpr](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Удаление динамических спецификаций исключений

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html): динамические спецификации исключений в C++11 стали нерекомендуемыми. Эта функция удалена из C++17, но (по-прежнему) нерекомендуемая спецификация `throw()` сохраняется исключительно в качестве псевдонима для `noexcept(true)`. Дополнительные сведения см. в разделе [Удаление спецификации динамических исключений и noexcept](#noexcept_removal).

### `not_fn()`

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html): `not_fn` является заменой `not1` и `not2`.

### <a name="rewording-enablesharedfromthis"></a>Изменение формулировки для `enable_shared_from_this`

[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html): класс `enable_shared_from_this` добавлен в C++11. Стандарт C++17 обновляет спецификацию, чтобы лучше обрабатывать некоторые пограничные случаи. [14]

### <a name="splicing-maps-and-sets"></a>Соединение карт и наборов

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf). Эта возможность позволяет извлекать узлы из ассоциативных контейнеров (например, `map`, `set`, `unordered_map`, `unordered_set`), а затем изменять их и вставлять обратно в тот же или другой контейнер с тем же типом узла. (Типичный вариант использования — извлечение узла из `std::map`, изменение ключа и повторная вставка.)

### <a name="deprecating-vestigial-library-parts"></a>Нерекомендуемые части библиотек

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html). Со временем несколько функций стандартной библиотеки C++ были заменены новыми, признаны нецелесообразными или проблемными. Эти функции являются официально нерекомендуемыми в C++17.

### <a name="removing-allocator-support-in-stdfunction"></a>Удаление поддержки распределителя в `std::function`

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html). До появления C++17 шаблон класса `std::function` содержал несколько конструкторов, принимающих аргумент распределителя. Однако использование распределителей в данном контексте было проблематичным, а семантика — неясной. Проблема конструкторов теперь устранена.

### <a name="fixes-for-notfn"></a>Исправления для `not_fn()`

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html). Новая формулировка `std::not_fn` поддерживает передачу категории значения при вызове класса-оболочки.

### <a name="sharedptrt-sharedptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html): внесение изменений `shared_ptr` из Library Fundamentals в C++17. [14]

### <a name="fixing-sharedptr-for-arrays"></a>Исправление `shared_ptr` для массивов

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html): исправления поддержки shared_ptr для массивов. [14]

### <a name="clarifying-insertreturntype"></a>Пояснение `insert_return_type`

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html): ассоциативные и неупорядоченные контейнеры с уникальными ключами имеют функцию-член `insert`, возвращающую `insert_return_type` вложенного типа. Тип возвращаемого значения теперь определяется как специализация типа, который параметризуется по итератору и типу узла контейнера.

### <a name="inline-variables-for-the-standard-library"></a>Встроенные переменные для стандартной библиотеки

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>Нерекомендуемые функции в приложении D

Приложение D стандарта C++ содержит все функции, признанные нерекомендуемыми, включая `shared_ptr::unique()`, `<codecvt>` и `namespace std::tr1`. Если задан параметр компилятора **/std:c++17**, почти все функции стандартной библиотеки в приложении D помечаются как нерекомендуемые. Дополнительные сведения см. в [этой статье](#annex_d).

Пространство имен `std::tr2::sys` в `<experimental/filesystem>` теперь по умолчанию выдает предупреждение о нерекомендуемых функциях при использовании **/std:c++14**, а при использовании **/std:c++17** оно по умолчанию удалено.

Улучшено соответствие в `<iostream>` за счет отказа от нестандартного расширения (явных специализаций в классе).

Стандартная библиотека теперь использует шаблоны переменных внутренним образом.

Стандартная библиотека была обновлена в ответ на изменения в компиляторе C++17. Среди прочего добавлен `noexcept` в систему типов и удалены динамические спецификации исключений.

## <a name="improvements_156"></a> Улучшения в Visual Studio 2017 версии 15.6

### <a name="c17-library-fundamentals-v1"></a>C++17. Основы работы с библиотеками V1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) включает технические спецификации основ библиотек для C++17 в стандарт. Содержит обновления для \<experimental/tuple>, \<experimental/optional>, \<experimental/functional>, \<experimental/any>, \<experimental/string_view>, \<experimental/memory>, \<experimental/memory_resource> и \<experimental/algorithm>.

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++17 Улучшение выведения аргументов шаблонов класса для стандартной библиотеки

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html). Переместите `adopt_lock_t` в начало списка параметров, чтобы `scoped_lock` разрешил согласованное использование `scoped_lock`. Разрешите конструктору `std::variant` участвовать в разрешении перегрузки в большем числе случаев, чтобы поддерживать присваивание копированием.

## <a name="improvements_157"></a> Усовершенствования в Visual Studio 2017 версии 15.7

### <a name="c17-rewording-inheriting-constructors"></a>C++17 Изменение формулировки наследуемых конструкторов

[P0136R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html) указывает, что объявление **using**, которое указывает конструктор, теперь делает соответствующие конструкторы базового класса видимыми для инициализаций производного класса, поэтому можно не объявлять дополнительные конструкторы для производного класса. Это является изменением формулировки по сравнению с C++14. В Visual Studio 2017 версии 15.7 и более поздних в режиме **/std:c++17** может оказаться недопустимым или иметь иную семантику код, который нормально работает в C++14 с использованием наследуемых конструкторов.

В следующем примере показана реакция на событие в C++14:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n) = delete; // Error C2280
};

B b(42L); // Calls B<long>(long), which calls A(int)
          //  due to substitution failure in A<long>(long).
```

В следующем примере показана реакция на событие **/std:c++17** в Visual Studio 15.7:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n)
    {
        //do something
    }
};

B b(42L); // now calls B(int)
```

Дополнительные сведения см. в разделе [Конструкторы](../cpp/constructors-cpp.md#inheriting_constructors).

### <a name="c17-extended-aggregate-initialization"></a>C++17 Расширенная агрегатная инициализация

[P0017R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)

Если конструктор базового класса не является открытым, но доступен производному классу, то в режиме **/std:c ++17** в Visual Studio версии 15.7 больше нельзя использовать пустые фигурные скобки для инициализации объекта производного типа.

В следующем примере показана соответствующая реакция на событие в C++14:

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};

Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

В C++17 `Derived` теперь считается агрегатным типом. Это означает, что инициализация `Base` через закрытый конструктор по умолчанию происходит непосредственно как часть расширенного правила агрегатной инициализации. Закрытый конструктор `Base` ранее вызывался через конструктор `Derived`, и это работало успешно благодаря объявлению дружественных отношений.

В следующем примере показано поведение C++17 в Visual Studio версии 15.7 в режиме **/std:c++17**:

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};

Derived d1; // OK. No aggregate init involved.

Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++17 Объявление параметров шаблона, не являющихся типами, с использованием auto

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

В режиме **/std:c ++17** компилятор теперь может выводить тип аргумента шаблона, не являющегося типом и объявленного с **auto**:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

В результате код C++14 может быть недопустимым или иметь другую семантику. Например, стали допустимыми некоторые перегрузки, которые ранее были недопустимыми. В следующем примере показан код C++14, который компилируется, поскольку вызов `example(p)` привязан к `example(void*);`. В Visual Studio 2017 версии 15.7 в режиме **/std:c++17** шаблон функции `example` является оптимальным.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

В следующем примере показан код C++17 в Visual Studio 15.7 в режиме **/std:c++17**:

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*);

void example(void *);

void sample(A<0> *p)
{
    example(p); // C2280: 'int example<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++17 Простые преобразования строк (частично)

[P0067R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html). Независимые от языкового стандарта функции низкого уровня для преобразования между целыми числами и строками и между числами с плавающей запятой и строками.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++20. Отказ от лишнего вырождения (частично)

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf). Проводит различие между концепцией "вырождения" и простым удалением константы или квалификаторов ссылки.  Новый признак типа `remove_reference_t` заменяет `decay_t` в некоторых контекстах. В Visual Studio 2019 реализована поддержка `remove_cvref_t`.

### <a name="c17-parallel-algorithms"></a>C++17 Параллельные алгоритмы

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html). Технические спецификации параллелизма включены в стандарт с небольшими изменениями.

### <a name="c17-hypotx-y-z"></a>C++17: `hypot(x, y, z)`

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf). Добавлены три новые перегрузки в `std::hypot` для типов **float**, **double** и **long double**, у каждой из которых есть три входных параметра.

### <a name="c17-filesystem"></a>C++17: \<filesystem>

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html). Включает технические спецификации файловой системы в стандарт с некоторыми изменениями формулировок.

### <a name="c17-mathematical-special-functions"></a>C++17 Специальные математические функции

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html). Включает предыдущие технические спецификации для специальных математических функций в стандарт \<cmath> header.

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++17 Рекомендации по удержанию для стандартной библиотеки

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html). Обновляет до STL, чтобы воспользоваться преимуществами внедрения в C++17 [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), который добавляет поддержку для выведения аргумента шаблона класса.

### <a name="c17-repairing-elementary-string-conversions"></a>C++17 Исправление простых преобразований строк

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html). Перемещение новых функций по простому преобразованию строк из P0067R5 в новый заголовок \<charconv> и другие усовершенствования, включая изменение обработки ошибок для использования `std::errc` вместо `std::error_code`.

### <a name="c17-constexpr-for-chartraits-partial"></a>C++17: `constexpr` для `char_traits` (частично)

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html). Изменения в функциях-членах `length`, `compare` и `find` типа `std::traits_type`, позволяющие использовать `std::string_view` в константных выражениях. (В Visual Studio 2017 версии 15.6 поддерживается только для Clang/LLVM. В версии 15.7, предварительная версия 2, почти полная поддержка и для ClXX.)

## <a name="improvements_159"></a> Усовершенствования в Visual Studio 2017 версии 15.9

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>Порядок вычисления слева направо для операторов `->*`, `[]`, `>>` и `<<`

Начиная с C++17, операнды операторов `->*`, `[]`, `>>` и `<<` должны обрабатываться в порядке слева направо. Есть два случая, в которых компилятор не может обеспечить этот порядок:

- если одно из выражений операндов является объектом, передаваемым по значению, или содержит объект, передаваемый по значению;

- при компиляции с использованием **/clr**, когда один из операндов является полем объекта или элемента массива.

Компилятор выдает предупреждение [C4866](https://docs.microsoft.com/cpp/error-messages/compiler-warnings/c4866?view=vs-2017), когда он не может обеспечить вычисление слева направо. Компилятор создает это предупреждение только в том случае, если указан режим **/std:c++17** или более поздней версии, так как в C++17 добавлено требование обработки этих операторов в порядке слева направо.

Чтобы устранить это предупреждение, проверьте наличие этого требования (например, при вычислении операндов могут наблюдаться нежелательные явления, связанные с нарушением порядка). Во многих случаях порядок вычисления операндов не имеет никакого значения. Если порядок вычисления должен быть слева направо, попробуйте передать операнды с использованием ссылки на константу. Это изменение устраняет предупреждение в следующем примере кода.

```cpp
// C4866.cpp
// compile with: /w14866 /std:c++17

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x) : x(x) {}
    HasCopyConstructor(const HasCopyConstructor& h) : x(h.x) { }
};

int operator>>(HasCopyConstructor a, HasCopyConstructor b) { return a.x >> b.x; }

// This version of operator>> does not trigger the warning:
// int operator>>(const HasCopyConstructor& a, const HasCopyConstructor& b) { return a.x >> b.x; }

int main()
{
    HasCopyConstructor a{ 1 };
    HasCopyConstructor b{ 2 };

    a>>b;        // C4866 for call to operator>>
};
```

## <a name="update_150"></a> Исправления ошибок в Visual Studio 2017 RTW (версии 15.0)

### <a name="copy-list-initialization"></a>Инициализация копии списка

Visual Studio 2017 правильно вызывает ошибки компилятора, связанные с созданием объектов с использованием списков инициализаторов, которые не обнаруживались в Visual Studio 2015 и могли приводить к сбоям или неопределенному поведению во время выполнения. Согласно N4594 13.3.1.7p1, при инициализации копии списка компилятор должен учитывать явный конструктор для разрешения перегрузки, но выдавать ошибку, если эта перегрузка выбирается на самом деле.

Следующие два примера кода компилируются в Visual Studio 2015, но не в Visual Studio 2017.

```cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

Чтобы исправить эту ошибку, следует использовать прямую инициализацию:

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

В Visual Studio 2015 компилятор ошибочно интерпретировал инициализацию копии списка так же, как обычную инициализацию копии. Он рассматривал только преобразование конструкторов для разрешения перегрузки. В следующем примере Visual Studio 2015 выбирает MyInt(23), но Visual Studio 2017 правильно выводит ошибку.

```cpp
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
    explicit MyStore(int initialCapacity);
};

struct MyInt {
    MyInt(int i);
};

struct Printer {
    void operator()(MyStore const& s);
    void operator()(MyInt const& i);
};

void f() {
    Printer p;
    p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

Этот пример аналогичен предыдущему, но выводит другую ошибку. Он выполняется успешно в Visual Studio 2015, а в Visual Studio 2017 с C2668 завершается ошибкой.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>Нерекомендуемые определения типов

Теперь Visual Studio 2017 выдает правильное предупреждение для нерекомендуемых определений типов, объявленных в классе или структуре. В следующем примере показана компиляция без предупреждений в Visual Studio 2015, но в Visual Studio 2017 выводится предупреждение C4996.

```cpp
struct A
{
    // also for __declspec(deprecated)
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### `constexpr`

Visual Studio 2017 правильно выдает ошибку, если левый операнд в операции условного вычисления является недопустимым в контексте constexpr. Следующий код компилируется в Visual Studio 2015, но не в Visual Studio 2017 (ошибка C3615: функция «f» с квалификатором constexpr не может выдавать константное выражение):

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615
}
```

Чтобы исправить эту ошибку, объявите функцию `array::size()` как `constexpr` или удалите квалификатор `constexpr` из `f`.

### <a name="class-types-passed-to-variadic-functions"></a>Типы классов, передаваемые в функции с переменным числом аргументов

В Visual Studio 2017 классы и структуры, передаваемые в функцию с переменным числом аргументов, например printf, должны быть доступны для простого копирования. При передаче таких объектов компилятор просто выполняет побитовое копирование и не вызывает конструктор или деструктор.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function.
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Чтобы исправить эту ошибку, можно вызвать функцию-член, возвращающую тип, доступный для простого копирования,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

или выполнить статическое приведение для преобразования объекта перед его передачей:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Для строк, созданных и управляемых с помощью CString, следует использовать предоставленный `operator LPCTSTR()` для приведения объекта CString к указателю C, ожидаемому строкой формата.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>CV-квалификаторы в конструкторах класса

В Visual Studio 2015 компилятор иногда ошибочно игнорирует cv-квалификатор при создании объекта класса путем вызова конструктора. Эта проблема может привести к сбою или непредсказуемому поведению среды выполнения. Следующий пример компилируется в Visual Studio 2015, но вызывает ошибку компилятора в Visual Studio 2017:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Чтобы исправить эту ошибку, объявите `operator int()` как `const`.

### <a name="access-checking-on-qualified-names-in-templates"></a>Проверка доступа к полным именам в шаблонах

В предыдущих версиях компилятора не выполнялась проверка доступа к полным именам в некоторых контекстах шаблонов. Эта проблема может помешать ожидаемой работе SFINAE там, где подстановка должна завершиться ошибкой из-за отсутствия доступа к имени. Это может приводить к сбою или неожиданному поведению во время выполнения из-за того, что компилятор ошибочно вызывает неверную перегрузку оператора. В Visual Studio 2017 выводится ошибка компилятора. Конкретные ошибки могут различаться, но чаще всего возникает ошибка C2672 "совпадающая перегруженная функция не найдена". Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017:

```cpp
#include <type_traits>

template <class T> class S {
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```

### <a name="missing-template-argument-lists"></a>Отсутствующие списки аргументов шаблона

В Visual Studio 2015 и более ранних версиях компилятор не диагностировал отсутствующие списки аргументов шаблона при отображении шаблона в списке параметров шаблона (например, в составе аргумента шаблона по умолчанию или как параметр шаблона, не являющийся типом). Эта проблема может привести к непредсказуемому поведению, включая сбои компилятора или непредсказуемое поведение среды выполнения. Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>Выражение SFINAE

Для поддержки выражения SFINAE компилятор теперь анализирует аргументы `decltype` при объявлении шаблонов, а не при создании их экземпляров. Это означает, что независимая специализация, обнаруженная в аргументе decltype, не откладывается до момента создания. Она обрабатывается немедленно и в этот же момент проверяется на все возможные ошибки.

В следующем примере показана такая ошибка компилятора, возникающая во время объявления.

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT>
class IsCallable
{
public:
    struct BadType {};

    template <class U>
    static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>

    template <class U>
    static BadType Test(...);

    static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

### <a name="classes-declared-in-anonymous-namespaces"></a>Классы, объявляемые в анонимных пространствах имен

Согласно стандарту C++, объявленный внутри анонимного пространства имен класс имеет внутреннюю компоновку и не может быть экспортирован. В Visual Studio 2015 и более ранних версиях это правило не применялось. В Visual Studio 2017 это правило применяется частично. Приведенный ниже пример кода вызывает в Visual Studio 2017 такую ошибку: "Ошибка C2201: const anonymous в пространстве имен ::S1::vftable: требуется внешняя ссылка для экспорта или импорта".

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Инициализаторы по умолчанию для членов класса значения (C++/CLI)

В Visual Studio 2015 и более ранних версиях компилятор допускал (но игнорировал) инициализатор членов по умолчанию для члена класса значений. Инициализатор по умолчанию для класса значений всегда инициализирует члены нулевым значением. Конструктор по умолчанию не допускается. В Visual Studio 2017 инициализаторы членов по умолчанию вызывают ошибку компилятора, как показано в следующем примере:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Индексаторы по умолчанию (C++/CLI)

В Visual Studio 2015 и более ранних версиях в некоторых случаях компилятор неправильно определял свойство по умолчанию как индексатор по умолчанию. Эту проблему удавалось решить с использованием идентификатора `default` для доступа к свойству. Возможное решение само по себе стало создавать проблемы после того, как значение `default` было введено как ключевое слово в C++11. В Visual Studio 2017 были исправлены ошибки, требующие обходного решения. Теперь компилятор выдает ошибку, когда `default` используется для доступа к свойству класса по умолчанию.

```cpp
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

В Visual Studio 2017 оба свойства значения доступны по их именам:

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a> Исправления ошибок в Visual Studio 2017 версии 15.3

### <a name="calls-to-deleted-member-templates"></a>Вызовы шаблонов удаленного элемента

В предыдущих версиях Visual Studio компилятор в некоторых случаях не сообщал об ошибках при некорректных вызовах шаблона удаленного элемента, которые могли стать причиной сбоев при выполнении. Теперь приведенный ниже код возвращает ошибку C2280: "'int S\<int>::f\<int>(void)': попытка ссылки на удаленную функцию":

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail
}
```

Чтобы устранить эту ошибку, объявите элемент `i` как `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Проверки предварительных условий для признаков типов

В Visual Studio 2017 версии 15.3 улучшены проверки предварительных условий для признаков типов на более строгое следование стандарту. Одна из проверок проверяет присвоение. Для следующего кода создается ошибка C2139 в Visual Studio 2017 версии 15.3:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Новое предупреждение компилятора и проверки среды выполнения для маршалинга между собственными и управляемыми функциями

Вызов собственных функций из управляемых функций требует маршалинга. Среда CLR выполняет такой маршалинг, но не понимает семантику C++. Если вы передадите собственный объект по значению, CLR вызовет конструктор копии объекта или применит функцию `BitBlt`, что может привести к непредсказуемому поведению в среде выполнения.

Теперь компилятор выдает предупреждение, если во время компиляции он обнаруживает, что через границу собственной и управляемой функции передается по значению собственный объект с удаленным конструктором копии. Если компилятор во время компиляции не может получить такую информацию, он внедряет проверку времени выполнения, чтобы программа немедленно вызвала `std::terminate` в случае некорректного маршалинга. В Visual Studio 2017 версии 15.3 следующий код вызовет предупреждение C4606: "'A': для передачи аргумента по значению через границу собственных и управляемых функций требуется допустимый конструктор копии. В противном случае поведение в среде выполнения будет неопределенным.

```cpp
class A
{
public:
   A() : p_(new int) {}
   ~A() { delete p_; }

   A(A const &) = delete;
   A(A &&rhs) {
   p_ = rhs.p_;
}

private:
   int *p_;
};

#pragma unmanaged

void f(A a)
{
}

#pragma managed

int main()
{
    f(A()); // This call from managed to native requires marshaling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

Чтобы устранить такую ошибку, удалите директиву `#pragma managed`, чтобы вызывающая функция стала собственной. Это позволит избежать маршалинга.

### <a name="experimental-api-warning-for-winrt"></a>Экспериментальные предупреждения API для WinRT

API-интерфейсы WinRT, выпускаемые для экспериментов и обратной связи, обозначаются атрибутом `Windows.Foundation.Metadata.ExperimentalAttribute`. В Visual Studio 2017 версии 15.3 при обнаружении этого атрибута компилятор выдает предупреждение C4698. Некоторые API-интерфейсы в предыдущих версиях Windows SDK уже помечены этим атрибутом, поэтому обращения к этим API теперь вызывают указанное выше предупреждение. В новых Windows SDK атрибут удален из всех поставляемых типов, но если вы используете старые версии SDK, эти предупреждения нужно подавлять для всех вызовов поставляемых типов.

Для следующего кода создается предупреждение C4698: "'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' предоставляется только для ознакомительных целей и подлежит изменению или удалению в будущих обновлениях":

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Чтобы отключить это предупреждение, добавьте атрибут #pragma.

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Определение функции-члена шаблона вне строки

Visual Studio 2017 версии 15.3 выводит сообщение об ошибке, если встречает внешние определения функций элемента шаблона, не объявленных в классе. Для следующего кода создается ошибка C2039: элемент 'f': не является членом элемента 'S':

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Чтобы исправить такую ошибку, добавьте в класс следующее объявление:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>Попытка получить адрес для указателя `this`

В C++ `this` является значением prvalue с типом указателя для X. Вы не можете получить адрес `this` или привязать его к ссылке на lvalue. В предыдущих версиях Visual Studio компилятор позволял обойти это ограничение, выполнив приведение типов. В Visual Studio 2017 версии 15.3 компилятор выдает ошибку C2664.

### <a name="conversion-to-an-inaccessible-base-class"></a>Преобразование в недоступный базовый класс

Visual Studio 2017 версии 15.3 выводит сообщение об ошибке при попытке преобразовать тип в недоступный базовый класс. В компиляторе появляется "ошибка C2243: "приведение типа": преобразование из "D *" в "B *" существует, но является недоступным". Следующий код является некорректным и может привести к сбою в среде выполнения. Теперь компилятор создает ошибку C2243 для такого кода:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>Аргументы по умолчанию не допускаются во внешних определениях функций-членов

Аргументы по умолчанию не допускаются во внешних определениях функций-членов в классах шаблонов. Компилятор выдаст предупреждение в режиме **/permissive** и критическую ошибку в режиме **/permissive-** .

В предыдущих версиях Visual Studio следующий некорректный код может вызвать сбой среды выполнения. В Visual Studio 2017 версии 15.3 возникает предупреждение C5034, "A\<T>::f": внешнее определение члена шаблона класса не может иметь аргументы по умолчанию.

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034
{
    // ...
}
```

Чтобы устранить такую ошибку, удалите аргумент по умолчанию `= false`.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Использование `offsetof` с обозначением составного члена

Если используется `offsetof(T, m)`, где *m* является "обозначением составного члена", Visual Studio 2017 версии 15.3 выдает предупреждение при компиляции с параметром **/Wall**. Следующий код является некорректным и может привести к сбою во время выполнения. Visual Studio 2017 версии 15.3 выдает "предупреждение C4841: использовано нестандартное расширение — обозначение составного элемента в offsetof":

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Чтобы исправить этот код, отключите предупреждение с помощью директивы pragma или уберите из кода `offsetof`.

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Использование `offsetof` со статическим элементом данных или функцией-членом

Если используется `offsetof(T, m)`, где *m* ссылается на статические данные-член или на функцию-член, Visual Studio 2017 версии 15.3 выдает ошибку. Для следующего примера кода создается "ошибка C4597, неопределенное поведение, offsetof применяется к функции-члену example" и "ошибка C4597, неопределенное поведение, offsetof применяется к данным-члену sample".

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

Этот код является некорректным и может привести к сбою во время выполнения. Чтобы устранить такую ошибку, измените код так, чтобы он не создавал неопределенное поведение. Это код не является переносимым и запрещен стандартом C++.

### <a name="declspec"></a> Новое предупреждение для атрибутов `__declspec`

В Visual Studio 2017 версии 15.3 компилятор больше не игнорирует атрибуты, если `__declspec(...)` применяется перед спецификацией компоновки `extern "C"`. В прошлом компилятор игнорировал такой атрибут, что могло повлиять на работу в среде выполнения. Если заданы параметры **/Wall** и **/WX**, для следующего кода выдается "предупреждение C4768: атрибуты __declspec перед спецификацией компоновки игнорируются":

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Чтобы устранить это предупреждение, переместите `extern "C"` вперед:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

В версии 15.3 это предупреждение по умолчанию отключено, а в 15.5 — включено. Оно влияет только на код, скомпилированный с параметрами **/Wall** **/WX**.

### <a name="decltype-and-calls-to-deleted-destructors"></a>`decltype` и вызовы удаленных деструкторов

В предыдущих версиях Visual Studio компилятор не отслеживал возникновение вызовов удаленных деструкторов в контексте выражений, связанных с `decltype`. В Visual Studio 2017 версии 15.3 следующий код вызывает сообщение "Ошибка C2280. 'A\<T>::~A(void)': предпринята попытка ссылки на удаленную функцию".

```cpp
template<typename T>
struct A
{
   ~A() = delete;
};

template<typename T>
auto f() -> A<T>;

template<typename T>
auto g(T) -> decltype((f<T>()));

void h()
{
   g(42);
}
```

### <a name="uninitialized-const-variables"></a>Неинициализированные переменные const

В выпуске Visual Studio 2017 RTW использовалась регрессия, из-за которой компилятор C++ не выдавал диагностических сообщений о том, что переменная `const` не инициализирована. Эта регрессия была устранена в Visual Studio 2017 версии 15.3. Следующий код теперь вызывает "Предупреждение C4132. 'Value': для константного объекта требуется инициализация".

```cpp
const int Value; //C4132
```

Чтобы исправить эту ошибку, присвойте значение переменной `Value`.

### <a name="empty-declarations"></a>Пустые объявления

Теперь Visual Studio 2017 версии 15.3 предупреждает о пустых объявлениях для всех типов, а не только для встроенных. Теперь для следующего кода создаются предупреждения C4091 уровня 2 для всех четырех объявлений:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Чтобы устранить эти предупреждения, закомментируйте или удалите все пустые объявления. В случаях, когда объекты без имен созданы специально для побочных эффектов (например, RAII), им следует присвоить имена.

Это предупреждение отключено при использовании **/Wv:18** и включено по умолчанию на уровне предупреждений W2.

### <a name="stdisconvertible-for-array-types"></a>`std::is_convertible` для типов массивов

В предыдущих версиях компилятора класс [std::is_convertible](../standard-library/is-convertible-class.md) выдавал неверные результаты для типов массива. Из-за этого разработчикам библиотек необходимо было особым образом обрабатывать в компиляторе Microsoft C++ признаки типа `std::is_convertible<...>`. В следующем примере статические функции assert успешно срабатывают в предыдущих версиях Visual Studio, но в Visual Studio 2017 версии 15.3 завершаются ошибкой:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>` проверяет, правильно ли сформировано определение мнимой функции.

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdisconstructible"></a>Частные деструкторы и `std::is_constructible`

Предыдущие версии компилятора не проверяли, является ли деструктор закрытым, при получении результата [std::is_constructible](../standard-library/is-constructible-class.md). Теперь это принимается во внимание. В следующем примере статические функции assert успешно срабатывают в предыдущих версиях Visual Studio, но в Visual Studio 2017 версии 15.3 завершаются ошибкой:

```cpp
#include <type_traits>

class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};

// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```

Закрытые деструкторы могут сделать тип неконструируемым. При вычислении `std::is_constructible<T, Args...>` подразумевается следующее объявление.

```cpp
   T obj(std::declval<Args>()...)
```

Этот вызов подразумевает вызов деструктора.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: неоднозначное разрешение перегрузки

Предыдущим версиям компилятора иногда не удавалось обнаружить неоднозначность, если при использовании объявлений и при поиске функций по аргументам выявлялись различные кандидаты. Эта ошибка может привести к некорректному выбору перегрузки и непредсказуемому поведению в среде выполнения. В следующем примере Visual Studio 2017 версии 15.3 корректно выдает ошибку C2668, неоднозначный вызов перегруженной функции "f":

```cpp
namespace N {
   template<class T>
   void f(T&, T&);

   template<class T>
   void f();
}

template<class T>
void f(T&, T&);

struct S {};
void f()
{
   using N::f;

   S s1, s2;
   f(s1, s2); // C2668
}
```

Чтобы исправить код, удалите оператор using `N::f`, если вы намереваетесь вызвать `::f()`.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: локальные объявления функций и проверка по аргументам

При локальном объявлении функции скрываются внутри области, поэтому поиск по аргументам не осуществляется. Но предыдущие версии компилятора в этом случае выполняли поиск функции по аргументам, что могло привести к некорректному выбору перегрузки и непредсказуемому поведению в среде выполнения. Как правило, такая ошибка связана с ошибкой в сигнатуре локального объявления функции. В следующем примере Visual Studio 2017 версии 15.3 корректно выдает ошибку C2660 (функция f не принимает 2 аргумента).

```cpp
struct S {};
void f(S, int);

void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

Чтобы устранить эту проблему, измените сигнатуру `f(S)` или удалите ее.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: порядок инициализации в списках инициализатора

Члены класса инициализируются в порядке их объявления, а не в порядке отображения в списках инициализаторов. В предыдущих версиях компилятора, когда порядок списка инициализаторов отличался от порядка объявления, никакого предупреждения не выводилось. Эта проблема могла приводить к неопределенному поведению во время выполнения, если инициализация одного члена зависела от другого уже инициализированного члена в списке. В следующем примере Visual Studio 2017 версии 15.3 (с параметром **/Wall**) выдает "предупреждение C5038: данные-член 'A::y' будет инициализирован после данных-члена 'A::x'":

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Чтобы устранить проблему, список инициализатора должен иметь тот же порядок, что и объявления. Похожее предупреждение возникает, когда один инициализатор или оба ссылаются на члены базового класса.

Это предупреждение по умолчанию отключено и относится только к коду, скомпилированному с параметром **/Wall**.

## <a name="update_155"></a> Исправления ошибок и другие изменения поведения в Visual Studio 2017 версии 15.5

### <a name="partial-ordering-change"></a>Частичное упорядочение изменений

Компилятор теперь правильно отклоняет следующий код и выводит нужное сообщение об ошибке:

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```

```Output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
```

Проблема в приведенном выше примере заключается в том, что имеется два различия в типах (const и non-const и pack и non-pack). Чтобы устранить ошибку компилятора, удалите одно из различий. После этого компилятор сможет однозначно упорядочивать функции.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```

### <a name="exception-handlers"></a>Обработчики исключений

Обработчики ссылок на тип массива или функции никогда не соответствуют никаким объектам исключений. Теперь компилятор правильно учитывает это правило и создает предупреждение уровня 4. Он также больше не соответствует обработчику `char*` или `wchar_t*` в строковом литерале, если используется **/Zc:strictstrings**.

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```Output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```

Следующий код позволяет избежать этой ошибки:

```cpp
catch (int (*)[1]) {}
```

### <a name="tr1"></a> Пространство имен `std::tr1` является нерекомендуемым

Нестандартное пространство имен `std::tr1` теперь помечается как нерекомендуемое в режимах C++14 и C++17. В Visual Studio 2017 версии 15.5 приведенный ниже код вызывает предупреждение C4996:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```Output
warning C4996: 'std::tr1': warning STL4002: The non-standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

Чтобы исправить ошибку, удалите ссылку на пространство имен `tr1`.

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

### <a name="annex_d"></a> Функции стандартной библиотеки в приложении D помечены как нерекомендуемые

Если задан режим компилятора **/std:c++17**, почти все функции стандартной библиотеки в приложении D помечаются как нерекомендуемые.

В Visual Studio 2017 версии 15.5 приведенный ниже код вызывает предупреждение C4996:

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```Output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

Чтобы устранить ошибку, следуйте инструкциям в тексте предупреждения, как показано в следующем коде:

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>Неиспользуемые локальные переменные

В Visual Studio версии 15.5 предупреждение C4189 создается в большинстве случаев, как показано в следующем коде:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Чтобы устранить ошибку, удалите неиспользуемую переменную.

### <a name="single-line-comments"></a>Однострочные комментарии

В Visual Studio 2017 версии 15.5 компилятор C больше не создает предупреждения C4001 и C4179. Ранее они создавались только при использовании параметра компилятора **/Za**.  Эти предупреждения больше не нужны, так как однострочные комментарии входят в стандарт C, начиная с версии C99.

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

Если код не должен поддерживать обратную совместимость, вы можете избежать этих предупреждений, удалив подавление предупреждений C4001/C4179. Если код должен поддерживать обратную совместимость, подавите вывод только предупреждения C4619.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="declspec-attributes-with-extern-c-linkage"></a>Атрибуты `__declspec` с компоновкой `extern "C"`

В более ранних версиях Visual Studio компилятор игнорировал атрибуты `__declspec(...)`, когда `__declspec(...)` был применен перед спецификацией компоновки `extern "C"`. Это поведение приводило к созданию кода, который не планировался пользователем, с возможными последствиями для среды выполнения. Это предупреждение было добавлено в Visual Studio версии 15.3, но было отключено по умолчанию. В Visual Studio 2017 версии 15.5 предупреждение включено по умолчанию.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Чтобы устранить ошибку, поместите спецификацию компоновки перед атрибутом __declspec:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Это новое предупреждение C4768 выдается для некоторых заголовков Windows SDK, которые поставлялись с Visual Studio 2017 15.3 или более ранними версиями (например, с версией 10.0.15063.0, также известной как пакет SDK для RS2). Однако в более поздних версиях заголовков Windows SDK (в частности в ShlObj.h и ShlObj_core.h) внесены исправления, чтобы это предупреждение не создавалось. При появлении этого предупреждения от заголовков Windows SDK можно выполнить следующие действия:

1. Переключитесь на последнюю версию Windows SDK, поставляемую вместе с выпуском Visual Studio 2017 версии 15.5.

1. Отключите предупреждение вокруг #include инструкции заголовка пакета Windows SDK:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>Компоновка extern constexpr

В более ранних версиях Visual Studio компилятор всегда обеспечивал переменной `constexpr` внутреннюю компоновку даже в том случае, когда переменная была помечена как `extern`. В Visual Studio 2017 версии 15.5 новый параметр компилятора ( **/Zc:externConstexpr**) обеспечивает корректное поведение, соответствующее стандартам. В конечном счете это поведение будет использоваться по умолчанию.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Если файл заголовка содержит переменную, объявленную как `extern constexpr`, она должна быть помечена как `__declspec(selectany)` для правильного объединения повторяющихся объявлений:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>`typeid` нельзя использовать с неполным типом класса

В более ранних версиях Visual Studio компилятор неправильно разрешал выполнение следующего кода, что приводило к выводу потенциально неверных сведений о типе. В Visual Studio 2017 версии 15.5 компилятор правильно выдает сообщение об ошибке:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdisconvertible-target-type"></a>Тип целевого объекта `std::is_convertible`

Для `std::is_convertible` необходимо, чтобы целевой тип был допустимым возвращаемым типом. В более ранних версиях Visual Studio компилятор неправильно разрешал использование абстрактных типов, что могло приводить к неверному разрешению перегрузки и непредусмотренному поведению среды выполнения.  Следующий код теперь правильно выводит предупреждение C2338:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Чтобы избежать этой ошибки, при использовании `is_convertible` следует сравнить типы указателей, поскольку сравнение типа, отличного от указателя, может завершиться неудачно, если один тип является абстрактным:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="noexcept_removal"></a> Удаление спецификации динамических исключений и `noexcept`

В C++17 `throw()` является псевдонимом для `noexcept`, `throw(<type list>)` и `throw(...)` удалены, а определенные типы могут включать `noexcept`. Это изменение может привести к проблемам совместимости для исходного кода, который соответствует C++14 или более ранней версии. Параметр **/Zc:noexceptTypes-** можно использовать для возврата к версии C++14 `noexcept` при использовании режима C++17 в целом. Это позволяет обновить исходный код для соответствия C++17, не переписывая весь код `throw()`.

Компилятор теперь также проверяет дополнительные спецификации несоответствующих исключений в объявлениях в режиме C++17 или с параметром **/permissive-** с новым предупреждением C5043.

Следующий код вызывает ошибки C5043 и C5040 в Visual Studio 2017 версии 15.5 при использовании параметра **/std:c++17**:

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```

Чтобы исправить ошибки и продолжать использовать **/std:c++17**, либо добавьте параметр **/Zc:noexceptTypes-** в командную строку, либо обновите код для использования `noexcept`, как показано в следующем примере:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```

### <a name="inline-variables"></a>Встроенные переменные

Статические члены данных constexpr теперь являются неявно встроенными. Это означает, что их объявления в пределах класса теперь являются определениями. Использование внешних определений для статических членов данных constexpr избыточно и не рекомендуется. Если в Visual Studio 2017 версии 15.5 указать параметр **/std:c++17**, следующий код теперь выдает предупреждение "C5041: *size, невстроенное определение статических данных-члена constexpr не требуется и является нерекомендуемым в C++17*":

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>Теперь предупреждение C4768 `extern "C" __declspec(...)` включено по умолчанию

Это предупреждение было добавлено в Visual Studio 2017 версии 15.3, но было отключено по умолчанию. В Visual Studio 2017 версии 15.5 предупреждение включено по умолчанию. Дополнительные сведения см. в разделе [Новое предупреждение для атрибутов \_\_declspec](#declspec).

### <a name="defaulted-functions-and-declspecnothrow"></a>Заданные по умолчанию функции и `__declspec(nothrow)`

Компилятор ранее разрешал объявление установленных по умолчанию функций с `__declspec(nothrow)`, если соответствующие базовые функции или функции-члены разрешали исключения. Это противоречит стандарту C++ и может привести к неопределенному поведению во время выполнения. Согласно стандарту, такие функции должны быть определены как удаленные, если имеется несовпадение спецификации исключений.  Если указан параметр **/std:c++17**, приведенный ниже код выдает ошибку C2280: *попытка ссылки на удаленную функцию. Функция была неявно удалена из-за несовместимости спецификации явного исключения со спецификацией неявного объявления*.

```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

Чтобы исправить этот код, удалите __declspec(nothrow) из функции по умолчанию или удалите `= default` и предоставьте определение функции вместе с любой необходимой обработкой исключений:

```cpp
struct A {
    A& operator=(const A& other) {
        // ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```

### <a name="noexcept-and-partial-specializations"></a>`noexcept` и частичные специализации

При наличии `noexcept` в системе типов частичные специализации для сопоставления отдельных "вызываемых" типов могут не пройти компиляцию или приводить к выбору основного шаблона из-за отсутствия частичной специализации для указателей на функции noexcept.

В таких случаях может потребоваться добавить дополнительные частичные специализации для обработки указателей на функции `noexcept` и указателей `noexcept` на функции-члены. Эти перегрузки допустимы только в режиме **/std:c++17**. Если вам необходимо поддерживать обратную совместимость с C++14 и вы создаете код, который будут использовать другие разработчики, следует защитить эти новые перегрузки внутри директив `#ifdef`. Если вы работаете в автономном модуле, то вместо защиты `#ifdef` можно просто выполнять компиляцию с параметром **/Zc:noexceptTypes-** .

Следующий код компилируется с параметром **/std:c++14**, но при использовании **/std:c++17** выдает ошибку C2027: "использование неопределенного типа 'A\<T>'":

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

Следующий код успешно компилируется при указании параметра **/std:c++17**, так как компилятор выбирает новую частичную специализацию `A<void (*)() noexcept>`:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="update_157"></a> Исправления ошибок и другие изменения в поведении в Visual Studio 2017 версии 15.7

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++17 Аргумент по умолчанию в шаблоне основного класса

Это изменение в поведении является обязательным условием для [выведения аргумента шаблона для шаблонов класса — P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html).

Ранее компилятор игнорировал аргумент по умолчанию в шаблоне основного класса.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

В Visual Studio 2017 версии 15.7 в режиме **/std:c++17** аргумент по умолчанию не игнорируется:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Разрешение имен зависимых объектов

Это изменение в поведении является обязательным условием для [выведения аргумента шаблона для шаблонов класса — P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html).

В следующем примере компилятор в Visual Studio 15.6 и более ранних версий разрешает `D::type` для `B<T>::type` в шаблоне основного класса.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = B<T*>::type;
};
```

Visual Studio 2017 версии 15.7 в режиме **/std:c++17** требует указать ключевое слово `typename` в инструкции `using` из D. Без `typename` компилятор вызывает предупреждение C4346, *"B<T\*>::type": зависимое имя не является типом*, а также ошибку C2061, *Синтаксическая ошибка: идентификатор type*.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = typename B<T*>::type;
};
```

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++17. Атрибут `[[nodiscard]]` — повышение порога предупреждения

В Visual Studio 2017 версии 15.7 в режиме **/std:c++17** порог предупреждения C4834 ("отмена возвращаемого значения функции с атрибутом nodiscard") повышается с W3 до W1. Вы можете отключить это предупреждение с помощью приведения к `void` или путем передачи **/wd:4834** компилятору

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Список инициализации для базового класса конструктора шаблонов с переменным числом аргументов

В предыдущих версиях Visual Studio список инициализации для базового класса конструктора шаблонов с переменным числом аргументов мог не содержать аргументов шаблона (что недопустимо), и при этом не выдавалась ошибка. В Visual Studio 2017 версии 15.7 компилятор выдает ошибку.

В следующем примере кода в Visual Studio 2017 версии 15.7 возникает *Ошибка C2614. D\<int>: недопустимая инициализация члена. "B" не является базовым классом или членом*.

```cpp
template<typename T>
struct B {};

template<typename T>
struct D : B<T>
{

    template<typename ...C>
    D() : B() {} // C2614. Missing template arguments to B.
};

D<int> d;
```

Чтобы устранить ошибку, измените выражение B() на B\<T>().

### <a name="constexpr-aggregate-initialization"></a>Агрегатная инициализация `constexpr`

В предыдущих версиях компилятор C++ неправильно обрабатывал агрегатную инициализацию `constexpr`, то есть принимал недопустимый код, в котором список агрегатной инициализации содержал слишком много элементов, что приводило к созданию неправильного объекта Codegen. Примером является следующий код:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {
        { 1, 2 },
        { 3, 4 }
    };
    return 0;
}
```

В Visual Studio 2017 версии 15.7 с обновлением 3 и более поздних версий в предыдущий пример добавляется *C2078 too many initializers*. В приведенном ниже примере показано, как исправить код. При инициализации `std::array`, когда используются вложенные списки инициализации в скобках, укажите для внутреннего массива собственный вложенный список в скобках:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {{ // note double braces
        { 1, 2 },
        { 3, 4 }
    }}; // note double braces
    return 0;
}
```

## <a name="update_158"></a> Исправления ошибок и изменения в поведении в Visual Studio 2017 15.8

Изменения компилятора в Visual Studio 2017 версии 15.8 входят в категорию исправления ошибок и изменений в поведении и перечислены ниже:

### <a name="typename-on-unqualified-identifiers"></a>`typename` для неквалифицированных идентификаторов

В режиме [/permissive-](../build/reference/permissive-standards-conformance.md) компилятор больше не принимает ложные ключевые слова `typename` в неквалифицированных идентификаторах в определениях шаблонов псевдонимов. Следующий код теперь вызывает ошибку C7511: *"T": после ключевого слова typename должно следовать полное имя*.

```cpp
template <typename T>
using  X = typename T;
```

Чтобы исправить эту ошибку, измените вторую строку на `using  X = T;`.

### <a name="declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()` справа от определений шаблонов псевдонимов

Ключевое слово [__declspec](../cpp/declspec.md) теперь запрещено указывать справа от определения шаблона псевдонима. Ранее компилятор принимал такой код, но игнорировал его и никогда не создавал предупреждение об устаревании при использовании псевдонима.

Вместо этого можно использовать стандартный атрибут C++ [\[\[deprecated\]\]](../cpp/attributes.md). Он учитывается в Visual Studio, начиная с выпуска 2017 версии 15.6. Следующий код теперь вызывает ошибку C2760: *синтаксическая ошибка: непредвиденный токен __declspec, ожидается type specifier*.

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

Чтобы исправить эту ошибку, измените код на следующий (укажите атрибут перед знаком "=" определения псевдонима).

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>Диагностика двухэтапного поиска имен

Для двухэтапного поиска имен нужно, чтобы независимые имена, используемые в тексте шаблона, отображались в шаблоне во время определения. Ранее компилятор Microsoft C++ мог не искать ненайденное имя до момента создания экземпляров. Теперь ему требуется, чтобы независимые имена привязывались уже в тексте шаблона.

Ошибка может возникать при поиске в зависимых базовых классах. Ранее компилятор разрешал использовать имена, определенные в зависимых базовых классах, так как их поиск выполнялся во время создания экземпляров после разрешения всех типов. Теперь такой код считается ошибкой. В этом случае вы можете принудительно использовать поиск переменной во время создания экземпляров, задав ей в качестве квалификатора тип базового класса или другим образом сделав ее зависимой, например с помощью указателя `this->`.

В режиме **/permissive-** следующий код теперь вызывает ошибку C3861: *base_value: идентификатор не найден*.

```cpp
template <class T>
struct Base {
    int base_value = 42;
};

template <class T>
struct S : Base<T> {
    int f() {
        return base_value;
    }
};
```

Чтобы исправить эту ошибку, измените инструкцию `return` на `return this->base_value;`.

**Примечание.** В Python-библиотеке Boost в течение долгого времени существовало относящееся к MSVC обходное решение для опережающего объявления шаблона в [unwind_type.hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp). В режиме [/permissive-](../build/reference/permissive-standards-conformance.md), начиная с Visual Studio 2017 версии 15.8 (_MSC_VER=1915), компилятор MSVC корректно выполняет поиск в зависимости от аргументов (ADL) и согласуется с другими компиляторами, делая условие обходного решения ненужным. Чтобы избежать ошибки *"C3861: unwind_type, идентификатор не найден"* , обновите файл заголовков по инструкции [PR 229](https://github.com/boostorg/python/pull/229) из репозитория Boostorg. Мы уже исправили пакет Boost [vcpkg](../build/vcpkg.md), поэтому при получении или обновлении источника Boost из vcpkg не нужно применять отдельное исправление.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>Прямые объявления и определения в пространстве имен `std`

Стандарт C++ запрещает пользователю добавлять опережающие объявления и определения в пространство имен `std`. Добавление объявлений или определений в пространство имен `std` или в пространство имен, вложенное в `std`, теперь приводит к неопределенному поведению.

В дальнейшем корпорация Майкрософт изменит место определения для некоторых типов стандартной библиотеки. Это изменение нарушит работу существующего кода, который добавляет прямые объявления в пространство имен `std`. Новое предупреждение C4643 помогает выявить такие проблемы с источником. Предупреждение можно включить в режиме **/default**; по умолчанию оно отключено. Оно повлияет на программы, которые компилируются с параметром **/Wall** или **/WX**.

Следующий код теперь вызывает ошибку C4643: *опережающее объявление vector в пространстве имен std запрещено стандартом C++* .

```cpp
namespace std {
    template<typename T> class vector;
}
```

Чтобы исправить эту ошибку, используйте директиву **include** вместо опережающего объявления.

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>Конструкторы, делегирующие самим себе

Стандарт C++ предполагает, что компилятор должен породить диагностическое сообщение, если делегирующий конструктор делегирует самому себе. Компилятор Microsoft C++ в режимах [/std:c++17](../build/reference/std-specify-language-standard-version.md) и [/std:c++latest](../build/reference/std-specify-language-standard-version.md) теперь вызывает ошибку C7535, *"X::X": делегирующий конструктор вызывает сам себя*.

Без этой ошибки следующая программа скомпилируется, но создаст бесконечный цикл.

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
};
```

Чтобы избежать этого, делегируйте в другой конструктор.

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>Постоянные выражения для `offsetof`

Макрос [offsetof](../c-runtime-library/reference/offsetof-macro.md) обычно реализовывался с помощью макроса, требующего [reinterpret_cast](../cpp/reinterpret-cast-operator.md). Такое использование недопустимо в контекстах, требующих константного выражения, но обычно компилятор Microsoft C++ разрешал его. Макрос `offsetof`, входящий в состав стандартной библиотеки, правильно использует встроенную конструкцию компилятора ( **__builtin_offsetof**), но многие разработчики применяли эту особенность для определения собственных `offsetof`.

В Visual Studio 2017 версии 15.8 компилятор ограничивает области, в которых можно использовать операторы `reinterpret_cast` в режиме по умолчанию, чтобы поведение кода лучше соответствовало стандарту C++. В режиме [/permissive-](../build/reference/permissive-standards-conformance.md) ограничения еще строже. Использование результата `offsetof` там, где требуются константные выражения, может привести к тому, что код вызовет предупреждение *"C4644: использование шаблона offsetof на основе макроса в константных выражениях противоречит стандарту; используйте вместо этого offsetof, заданный в стандартной библиотеке C++"* или "C2975: *недопустимый аргумент шаблона, ожидается константное выражение времени компиляции*".

Следующий код вызывает ошибку C4644 в режимах **/default** и **/std:c++17**, а также ошибку C2975 в режиме **/permissive-** :

```cpp
struct Data {
    int x;
};

// Common pattern of user-defined offsetof
#define MY_OFFSET(T, m) (unsigned long long)(&(((T*)nullptr)->m))

int main()

{
    switch (0) {
    case MY_OFFSET(Data, x): return 0;
    default: return 1;
    }
}
```

Чтобы исправить эту ошибку, используйте `offsetof`, определенный через \<cstddef>.

```cpp
#include <cstddef>

struct Data {
    int x;
};

int main()
{
    switch (0) {
    case offsetof(Data, x): return 0;
    default: return 1;
    }
}
```

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>Квалификаторы cv-qualifier в базовых классах, участвующих в раскрытии пакета

Компиляторы Microsoft C++ предыдущих версий не обнаруживали квалификаторы cv-qualifier в базовом классе, если он также участвовал в раскрытии пакета.

В Visual Studio 2017 версии 15.8 в режиме **/permissive-** следующий код вызывает ошибку C3770: *const S: не является допустимым базовым классом*.

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>Ключевое слово `template` и вложенные описатели имен

В режиме **/permissive-** компилятор теперь требует, чтобы ключевое слово `template` предшествовало имени шаблона, если оно стоит после зависимого вложенного описателя имен.

Следующий код в режиме **/permissive-** теперь вызывает ошибку "C7510: *example, перед зависимым именем шаблона теперь должен стоять префикс template. Примечание. См. справку по компилируемому экземпляру шаблона класса "X<T>"* .

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        Base<T>::example<int>();
    }
};
```

Чтобы исправить эту ошибку, добавьте ключевое слово `template` в инструкцию `Base<T>::example<int>();`, как показано в следующем примере.

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        // Add template keyword here:
        Base<T>::template example<int>();
    }
};
```

## <a name="update_159"></a> Исправления ошибок и изменения в поведении в Visual Studio 2017 версии 15.9

### <a name="identifiers-in-member-alias-templates"></a>Идентификаторы в шаблонах псевдонимов членов

Идентификатор, используемый в определении шаблона псевдонима члена, должен быть объявлен до использования.

В предыдущих версиях компилятора допускался следующий код:

```cpp
template <typename... Ts>
struct A
{
  public:
    template <typename U>
    using from_template_t = decltype(from_template(A<U>{}));

  private:
    template <template <typename...> typename Type, typename... Args>
    static constexpr A<Args...> from_template(A<Type<Args...>>);
};

A<>::from_template_t<A<int>> a;
```

В Visual Studio 2017 версии 15.9 в режиме **/permissive-** выводится ошибка компилятора C3861: *from_template: идентификатор не найден*.

Чтобы устранить эту ошибку, объявите `from_template_t` перед `from_template`.

### <a name="modules-changes"></a>Изменения модулей

В Visual Studio 2017 версии 15.9 компилятор выводит ошибку C5050, если на сторонах создания и потребления используются несогласованные параметры командной строки для модулей. В следующем примере показаны две проблемы:

- на стороне потребления (файл main.cpp) не указан параметр **/EHsc**;

- на стороне создания используется версия C++ **/std:c++17**, а на стороне потребления — **/std:c++14**.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

В обоих случаях компилятор вызывает *Предупреждение C5050. Возможная несовместимая среда при импорте модуля m: несоответствие версий C++.  Несоответствие версий модуля — "201402" и "201703"* .

Компилятор также выдает ошибку C7536 при каждом изменении IFC-файла. Заголовок интерфейса модуля содержит хэш SHA2 содержимого. При импорте IFC-файл хэшируется точно так же и проверяется на соответствие хэшу в заголовке. В случае несовпадения возникает ошибка "C7536: *ifc не прошел проверку целостности".  Ожидается SHA2: "66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6"* .

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Частичное упорядочение с использованием псевдонимов и невыведенных контекстов

Существует расхождение реализации в правилах частичного упорядочения, использующих псевдонимы в невыведенных контекстах. В следующем примере GCC и компилятор Microsoft C++ (в режиме **/permissive-** ) выводят ошибку, тогда как Clang принимает код.

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <class T, class Alloc>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

В предыдущем примере выводится ошибка C2668:

```Output
partial_alias.cpp(32): error C2668: 'f': ambiguous call to overloaded function
partial_alias.cpp(18): note: could be 'int f<Alloc,void>(A<void> &,const AlignedBuffer<10,4> &)'
partial_alias.cpp(12): note: or       'int f<Alloc,A<void>>(Alloc &,const AlignedBuffer<10,4> &)'
        with
        [
            Alloc=A<void>
        ]
partial_alias.cpp(32): note: while trying to match the argument list '(A<void>, AlignedBuffer<10,4>)'
```

Расхождение реализаций связано с регрессией в формулировках стандарта C++. Для устранения ошибки 2235 потребовалось удалить часть текста, который позволял упорядочивать эти перегрузки. В текущем стандарте C++ отсутствует механизм для частичного упорядочения этих функций, поэтому они считаются неоднозначными.

В качестве обходного решения мы рекомендуем не применять частичное упорядочение. Вместо этого используйте SFINAE для удаления конкретной перегрузки. В следующем примере используется вспомогательный класс `IsA`, позволяющий удалять первую перегрузку, если `Alloc` является специализацией `A`:

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <typename T> struct IsA : std::false_type {};
template <typename T> struct IsA<A<T>> : std::true_type {};

template <class T, class Alloc, typename = std::enable_if_t<!IsA<Alloc>::value>>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>Недопустимые выражения и типы, не являющиеся литералами, в определениях функций на основе шаблона

Недопустимые выражения и типы, не являющиеся литералами, теперь правильно выявляются в определениях шаблонных функций, которые специализируются явным образом. Ранее такие ошибки не возникали для определения функции. Тем не менее недопустимое выражение или нелитеральный тип будут по-прежнему диагностироваться при вычислении как часть константного выражения.

В предыдущих версиях Visual Studio следующий код компилировался без предупреждений:

```cpp
void g();

template<typename T>
struct S
{
    constexpr void f();
};
  
template<>
constexpr void S<int>::f()
{
    g(); // C3615 in 15.9
}
```

В Visual Studio 2017 версии 15.9 этот код вызывает такую ошибку:

```Output
error C3615: constexpr function 'S<int>::f' cannot result in a constant expression.
note: failure was caused by call of undefined function or one not declared 'constexpr'
note: see usage of 'g'.
```

Чтобы избежать этой ошибки, удалите квалификатор `constexpr` из явного создания экземпляра функции `f()`.

::: moniker-end

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>Улучшения соответствия стандарту C++ в Visual Studio 2015

Полный список улучшений соответствия вплоть до версии Visual Studio 2015 с обновлением 3 см. в разделе [Visual C++ What's New 2003 through 2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015) (Новые возможности Visual C++ 2003–2015).

## <a name="see-also"></a>См. также

[Соответствие стандартам языка Visual C++](../visual-cpp-language-conformance.md)
