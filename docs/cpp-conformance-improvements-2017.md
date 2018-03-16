---
title: "Улучшения соответствия C++ | Документы Майкрософт"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45f22597944084ecd2d30fe29bf4e8ab3ef80201
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="c-conformance-improvements-in-visual-studio-2017-versions-150-153improvements153-and-155improvements155"></a>Улучшения соответствия C++ в Visual Studio 2017 версий 15.0, [15.3](#improvements_153) и [15.5](#improvements_155)

Благодаря поддержке обобщенных constexpr и NSDMI для статистических выражений, компилятор Microsoft Visual C++ теперь включает все функции, добавленные в стандарте C++14. Обратите внимание, что в компиляторе по-прежнему отсутствует несколько функций из стандартов C++11 и C++98. Сведения о текущем состоянии компилятора см. в статье [Соответствие стандартам языка Visual C++](visual-cpp-language-conformance.md).

## <a name="c11"></a>C++11

**Поддержка SFINAE в выражениях из большего числа библиотек**  
Мы продолжаем улучшать в компиляторе Visual C++ поддержку SFINAE в выражениях. Это необходимо для определения и замены аргументов шаблонов, когда выражения decltype и constexpr могут выступать в качестве параметров шаблонов. Дополнительные сведения см. в разделе [Усовершенствования выражения SFINAE в версии-кандидате Visual Studio 2017](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

## <a name="c-14"></a>C++14

**NSDMI для статистических выражений**  
Статистическое выражение — это массив или класс без предоставленного пользователем конструктора, без закрытых или защищенных нестатических данных-членов, без базовых классов и виртуальных функций. Начиная с версии C++14, статистические выражения могут содержать инициализаторы членов. Дополнительные сведения см. в разделе [Инициализаторы членов и статистические выражения](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

**Расширенные constexpr**  
Выражения, объявленные как constexpr, теперь могут содержать определенные виды объявлений, операторы if и switch, операторы циклов, а также изменения объектов, время существования которых началось с вычисления выражения constexpr. Кроме того, больше не требуется, чтобы нестатическая функция-член была явной константой. Дополнительные сведения см. в статье [Нестрогие ограничения для функций constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html).

## <a name="c17"></a>C++17

**Сжатые static_assert** (доступны в **/std:c++17**)  
В C++17 параметр сообщения для static_assert является необязательным. Дополнительные сведения см. в разделе [Расширение static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

**Атрибут [[fallthrough]]** (доступен в **/std:c++17**)  
Атрибут [[fallthrough]] можно использовать в контексте операторов switch как подсказку для компилятора о том, что после завершения ветви требуется не прерывание, а переход к следующей. Это позволит избежать вывода предупреждений компилятора. Дополнительные сведения см. в разделе [Формулировка для атрибута [[fallthrough]]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

**Циклы for на основе универсального диапазона** (без переключения компилятора)  
Циклы for на основе диапазона больше не требуют, чтобы begin() и end() возвращали объекты одного типа. Это позволяет end() возвращать граничную метку согласно использованию в диапазонах [range-v3](https://github.com/ericniebler/range-v3) и технической спецификации по диапазонам (завершенной, но еще не опубликованной). Дополнительные сведения см. в разделе [Обобщение цикла For на основе диапазона](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a> Усовершенствования в Visual Studio 2017 версии 15.3

**Лямбда-выражения constexpr**  
Лямбда-выражения теперь можно использоваться в константных выражениях. Дополнительные сведения см. в документе о [лямбда-выражениях](http://open-std.org/JTC1/SC22/WG21/docs/papers/2015/n4487.pdf).

**Операторы if constexpr в шаблонах функций**  
Шаблон функции может содержать операторы `if constexpr` для выполнения ветвления во время компиляции. Дополнительные сведения см. в документе об [if constexpr](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0128r1.html).

**Операторы выбора с инициализаторами**  
Оператор `if` может включать инициализатор, который вводит переменную в области видимости блока внутри самого оператора. Дополнительные сведения см. в документе об [инструкциях выбора с инициализатором](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0305r1.html).

**Атрибуты [[maybe_unused]] и [[nodiscard]]**  
Новые атрибуты для отключения предупреждений, когда сущность не используется, или для выдачи предупреждений, когда возвращаемое значение вызова функции отбрасывается. Дополнительные сведения см. в документах о [формулировке для атрибута maybe_unused](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0212r0.pdf) и [предложении атрибутов unused,nodiscard и fallthrough](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0068r0.pdf).

**Использование пространств имен атрибутов без повторения**  
Новый синтаксис позволяет включать в список атрибутов всего один идентификатор пространства имен. Дополнительные сведения см. в статье [Attributes in C++](cpp/attributes2.md) (Атрибуты в C++).

**Структурированные привязки**  
Теперь одно объявление позволяет хранить значение с отдельными именами для его компонентов, когда значение является массивом, std::tuple или std::pair, либо когда все его нестатические данные-члены являются открытыми. Дополнительные сведения см. в документе по [структурированным привязкам](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf).

**Правила конструкции для значений класса перечисления**  
Теперь когда определение перечисления не вводит перечислитель, а источник перечисления использует синтаксис инициализации списка, происходит неявное и несужающее преобразование из базового типа перечисления в области в само перечисление. Дополнительные сведения см. в документе о [правилах конструкции значений класса enum](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf).

**Обращение к объекту *this по значению**  
Теперь лямбда-выражение может обращаться к объекту `*this` по значению. Это позволяет использовать лямбда-выражения в сценариях с параллельными и асинхронными операциями, особенно на новых архитектурах компьютеров. Дополнительные сведения см. в документе о [захвате объекта \*this по значению в виде [=,\*this] в лямбда-выражении](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html).

**Удаление operator++ для типа bool**  
`operator++` для типов `bool` больше не поддерживается. Дополнительные сведения см. в документе об [удалении устаревшего объекта operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

**Удаление нерекомендуемого ключевого слова register**  
Ключевое слово `register`, ранее признанное нерекомендуемым (и игнорируемое компилятором), теперь удалено из языка. Дополнительные сведения см. в документе об [удалении нерекомендуемого ключевого слова register](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

Полный список улучшений соответствия вплоть до версии Visual Studio 2015 с обновлением 3 см. в разделе [Visual C++ What's New 2003 through 2015](https://msdn.microsoft.com/en-us/library/mt723604.aspx) (Новые возможности Visual C++ 2003–2015).

## <a name="improvements_155"></a> Усовершенствования в Visual Studio 2017 версии 15.5

Функции, отмеченные [14], доступны без ограничений даже в режиме /std:c++14.

**Новый параметр компилятора для extern constexpr**  
В более ранних версиях Visual Studio компилятор всегда обеспечивал переменной `constexpr` внутреннюю компоновку даже в том случае, когда переменная была помечена как `extern`. В Visual Studio 2017 версии 15.5 новый параметр компилятора [/Zc:externConstexpr](build/reference/zc-externconstexpr.md) обеспечивает правильное поведение, соответствующее стандартам. Дополнительные сведения см. в разделе о [компоновке extern constexpr](#extern_linkage).

**Удаление динамических спецификаций исключений**  
[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html): динамические спецификации исключений в C++11 стали нерекомендуемыми. Функция удалена из C++17, но (по-прежнему) нерекомендуемая спецификация `throw()` сохраняется исключительно в качестве псевдонима для `noexcept(true)`. Дополнительные сведения см. в разделе [Удаление спецификации динамических исключений и noexcept](#noexcept_removal). 

**not_fn()**  
[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html): `not_fn` является заменой `not1` и `not2`.

**Переформулировка enable_shared_from_this**  
[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html): класс `enable_shared_from_this` добавлен в C++11. Стандарт C++17 обновляет спецификацию для улучшения обработки некоторых сложных случаев. [14]

**Соединение карт и наборов**  
[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf): эта возможность позволяет извлекать узлы из ассоциативных контейнеров (например, сопоставлений, наборов, unordered\_map, unordered\_set), а затем изменять их и вставлять обратно в тот же или другой контейнер, использующий этот же тип узла. (Типичный вариант использования — извлечение узла из `std::map`, изменение ключа и повторная вставка.)

**Нерекомендуемые части библиотек**  
[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html): с течением лет некоторые функции стандартной библиотеки C++ были заменены более новыми, признаны нецелесообразными или проблемными. Эти функции являются официально нерекомендуемыми в C++17. 

**Удаление поддержки распределителя в std::function**  
[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html): до появления C++17 шаблон класса `std::function` содержал несколько конструкторов, принимающих аргумент распределителя. Однако использование распределителей в данном контексте было проблематичным, а семантика — неясной. Поэтому эти конструкторы были удалены.

**Исправления для not_fn()**  
[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html): новая формулировка `std::not_fn` поддерживает передачу категории значения при вызове класса-оболочки.

**shared_ptr\<T[]>, shared_ptr\<T[N]>**  
[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html): внесение изменений `shared_ptr` из Library Fundamentals в C++17. [14]

**Исправление shared_ptr для массивов**  
[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html): исправления поддержки shared_ptr для массивов. [14]

**Уточнение insert_return_type**  
[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html): ассоциативные и неупорядоченные контейнеры с уникальными ключами имеют функцию-член `insert`, возвращающую `insert_return_type` вложенного типа. Тип возвращаемого значения теперь определяется как специализация типа, который параметризуется по итератору и типу узла контейнера.

**Встроенные переменные для STL**  
[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

**Нерекомендуемые функции в приложении D**  
Приложение D стандарта C++ содержит все функции, признанные нерекомендуемыми, включая `shared_ptr::unique()`, `<codecvt>` и `namespace std::tr1`. Если задан параметр компилятора **/std:c++17**, почти все функции стандартной библиотеки в приложении D помечаются как нерекомендуемые. Дополнительные сведения см. в разделе [Функции стандартной библиотеки в приложении D помечены как нерекомендуемые](#annex_d).

Пространство имен `std::tr2::sys` в `<experimental/filesystem>` теперь по умолчанию выдает предупреждение о нерекомендуемых функциях при использовании /std:c++14, а при использовании **/std:c++17** оно по умолчанию удалено.

Улучшенное соответствие в потоках ввода-вывода за счет отказа от нестандартного расширения (явных специализаций в классе).

Стандартная библиотека теперь использует шаблоны переменных внутренним образом.

Стандартная библиотека была обновлена в соответствии с изменениями компилятора C++17, включая добавление noexcept в систему типов и удаление спецификаций динамических исключений.

## <a name="bug-fixes-in-visual-studio-versions-150-153update153-and-155update155"></a>Исправления ошибок в Visual Studio версии 15.0, [15.3](#update_153) и [15.5](#update_155)

### <a name="copy-list-initialization"></a>Инициализация копии списка

Visual Studio 2017 правильно вызывает ошибки компилятора, связанные с созданием объектов с использованием списков инициализаторов, которые не обнаруживались в Visual Studio 2015 и могли приводить к сбоям или неопределенному поведению во время выполнения. Согласно N4594 13.3.1.7p1 в инициализации копии списка компилятор должен учитывать явный конструктор для разрешения перегрузки, но должен выдавать ошибку, если эта перегрузка выбирается на самом деле.

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

### <a name="constexpr"></a>constexpr

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

Для строк, созданных и управляемых с помощью CStringW, следует использовать предоставленный `operator LPCWSTR()` для приведения объекта CStringW к указателю C, ожидаемому строкой формата.

```cpp
CStringW str1;
CStringW str2;
str1.Format(L"%s", static_cast<LPCWSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>CV-квалификаторы при построении класса

В Visual Studio 2015 компилятор иногда ошибочно игнорирует cv-квалификатор при создании объекта класса путем вызова конструктора. Это может привести к сбою или непредсказуемому поведению среды выполнения. Следующий пример компилируется в Visual Studio 2015, но вызывает ошибку компилятора в Visual Studio 2017:

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

В предыдущих версиях компилятора проверка доступа к полным именам в некоторых контекстах шаблонов не выполнялась. Это может помешать ожидаемой работе SFINAE там, где подстановка должна завершиться ошибкой из-за отсутствия доступа к имени. Такая ситуация может приводить к сбою или неожиданному поведению во время выполнения из-за того, что компилятор неправильно вызывает неверную перегрузку оператора. В Visual Studio 2017 выводится ошибка компилятора. Ошибки могут различаться, но, как правило, это ошибка C2672: "Совпадающая перегруженная функция не найдена". Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017:

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

В Visual Studio 2015 и более ранних версиях компилятор не диагностировал отсутствующие списки аргументов шаблона при отображении шаблона в списке параметров шаблона (например, в составе аргумента шаблона по умолчанию или как параметр шаблона, не являющийся типом). Это может привести к непредсказуемому поведению, включая сбои компилятора или непредсказуемое поведение среды выполнения. Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>Выражение SFINAE

Для поддержки выражения SFINAE компилятор теперь анализирует аргументы decltype при объявлении, а не создании шаблонов. Соответственно, независимая специализация, обнаруженная в аргументе decltype, не откладывается до момента создания и немедленно обрабатывается. Кроме того, в это время выявляются все возникающие ошибки.

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

Согласно стандарту C++ класс, объявленный внутри анонимного пространства имен, имеет внутреннюю компоновку и не может быть экспортирован. В Visual Studio 2015 и более ранних версиях это правило не применялось. В Visual Studio 2017 это правило применяется частично. Приведенный ниже пример кода вызывает в Visual Studio 2017 такую ошибку: "Ошибка C2201: const anonymous в пространстве имен ::S1::vftable: требуется внешняя ссылка для экспорта или импорта".

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Инициализаторы по умолчанию для членов класса значения (C++/CLI)

В Visual Studio 2015 и более ранних версиях компилятор допускал (но игнорировал) инициализатор членов по умолчанию для члена класса значений. Инициализатор по умолчанию для класса значений всегда инициализирует члены нулевым значением. Конструктор по умолчанию не допускается. В Visual Studio 2017 инициализаторы членов по умолчанию вызывают ошибку компилятора, как показано в следующем примере:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Индексаторы по умолчанию (C++/CLI)

В Visual Studio 2015 и более ранних версиях в некоторых случаях компилятор неправильно определял свойство по умолчанию как индексатор по умолчанию. Эту проблему удавалось решить с использованием идентификатора `default` для доступа к свойству. Возможное решение само по себе стало создавать проблемы после того, как значение `default` было введено как ключевое слово в C++11. Поэтому в Visual Studio 2017 были исправлены ошибки, требующие обходного решения. Теперь компилятор выдает ошибку, когда `default` используется для доступа к свойству класса по умолчанию.

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

В предыдущих версиях Visual Studio компилятор в некоторых случаях не сообщал об ошибках при некорректных вызовах шаблона удаленного элемента, которые могли стать причиной сбоев в среде выполнения. Теперь приведенный ниже код возвращает ошибку C2280: "'int S\<int>::f\<int>(void)': попытка ссылки на удаленную функцию":

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

Чтобы устранить эту ошибку, объявите элемент "i" как `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Проверки предварительных условий для признаков типов

В Visual Studio 2017 версии 15.3 улучшены проверки предварительных условий для признаков типов на более строгое следование стандарту. Одна из проверок проверяет присвоение. Для следующего кода создается ошибка C2139 в Visual Studio 2017 версии 15.3:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Новое предупреждение компилятора и проверки среды выполнения для маршалинга между собственными и управляемыми функциями

Вызов собственных функций из управляемых функций требует маршалинга. Среда CLR выполняет такой маршалинг, но не понимает семантики C++. Если вы передадите собственный объект по значению, CLR вызовет конструктор копии объекта или применит функцию BitBlt, что может привести к непредсказуемому поведению в среде выполнения.

Теперь компилятор выдает предупреждение, если во время компиляции он обнаруживает, что через границу собственной и управляемой функции передается по значению собственный объект с удаленным конструктором копии. Если компилятор во время компиляции не может получить такую информацию, он внедряет проверку времени выполнения, чтобы программа немедленно вызвала `std::terminate` в случае некорректного маршалинга. В Visual Studio 2017 версии 15.3 следующий код вызовет предупреждение C4606: "'A': для передачи аргумента по значению через границу собственных и управляемых функций требуется допустимый конструктор копии. В противном случае поведение в среде выполнения будет неопределенным".

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
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

Чтобы устранить такую ошибку, удалите директиву `#pragma managed`, чтобы вызывающая функция стала собственной. Это позволит избежать маршалинга.

### <a name="experimental-api-warning-for-winrt"></a>Экспериментальные предупреждения API для WinRT

API-интерфейсы WinRT, выпускаемые для экспериментов и обратной связи, обозначаются атрибутом `Windows.Foundation.Metadata.ExperimentalAttribute`. В Visual Studio 2017 версии 15.3 при обнаружении этого атрибута компилятор выдает предупреждение C4698. Некоторые API-интерфейсы в предыдущих версиях Windows SDK уже помечены этим атрибутом, поэтому обращения к этим API теперь вызывают указанное выше предупреждение. В новых Windows SDK атрибут удален из всех поставляемых типов, но если вы используете старые версии SDK, эти предупреждения нужно скрывать для всех вызовов поставляемых типов.

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

Visual Studio 2017 версии 15.3 выводит сообщение об ошибке, если встречает вне строки определения функции элемента шаблона, не объявленной в классе. Для следующего кода создается ошибка C2039: элемент 'f': не является членом элемента 'S':

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

### <a name="attempting-to-take-the-address-of-this-pointer"></a>Попытка получить адрес указателя "this"

В C++ `this` является значением prvalue с типом указателя для X. Вы не можете получить адрес `this` или привязать его к ссылке на lvalue. В предыдущих версиях Visual Studio компилятор позволял обойти это ограничение, выполнив приведение. В Visual Studio 2017 версии 15.3 компилятор выдает ошибку C2664.

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

### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>Аргументы по умолчанию не допускаются в определениях функций-членов вне строки

Аргументы по умолчанию запрещено использовать в невстроенных определениях функций-членов в классах шаблонов. Компилятор выдаст предупреждение при использовании параметра **/permissive** и критическую ошибку при использовании **/permissive-**.

В предыдущих версиях Visual Studio следующий некорректный код может вызвать сбой среды выполнения. Visual Studio 2017 версии 15.3 выводит предупреждение C5034 "'A\<T>:: f': невстроенное определение члена в шаблоне класса не может использовать аргументы по умолчанию":

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

### <a name="use-of-offsetof-with-compound-member-designator"></a>Использование offsetof с обозначением составного члена

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

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Использование offsetof со статическими данными-членом или функцией-членом

Если используется `offsetof(T, m)`, где *m* ссылается на статические данные-член или на функцию-член, Visual Studio 2017 версии 15.3 выдает ошибку. Для следующего примера кода создается "ошибка C4597: неопределенное поведение: offsetof применяется к функции-члену 'foo'" и "ошибка C4597: неопределенное поведение: offsetof применяется к данным-члену 'bar'" :

```cpp
#include <cstddef>

struct A {
   int foo() { return 10; }
   static constexpr int bar = 0;
};

constexpr auto off = offsetof(A, foo);
constexpr auto off2 = offsetof(A, bar);
```

Этот код является некорректным и может привести к сбою во время выполнения. Чтобы устранить такую ошибку, измените код так, чтобы он не создавал неопределенное поведение. Это код не является переносимым и запрещен стандартом C++.

### <a name="declspec"></a> Новое предупреждение для атрибутов declspec

В Visual Studio 2017 версии 15.3 компилятор больше не игнорирует атрибуты, если `__declspec(...)` применяется перед спецификацией компоновки `extern "C"`. В прошлом компилятор игнорировал такой атрибут, что могло повлиять на работу в среде выполнения. Если заданы параметры **/Wall** и **/WX**, для следующего кода выдается "предупреждение C4768: атрибуты __declspec перед спецификацией компоновки игнорируются":

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Чтобы устранить это предупреждение, переместите extern "C" вперед:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

В версии 15.3 это предупреждение по умолчанию отключено, а в 15.5 — включено. Оно влияет только на код, скомпилированный с параметрами **/Wall** **/WX**.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype и вызовы удаленных деструкторов

В предыдущих версиях Visual Studio компилятор не отслеживал возникновение вызовов удаленных деструкторов в контексте выражений, связанных с "decltype". В Visual Studio 2017 версии 15.3 для приведенного ниже кода выдается ошибка C2280: "'A\<T>::~A(void)': попытка ссылки на удаленную функцию":

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

В выпуске Visual Studio 2017 RTW была допущена регрессия, из-за которой компилятор C++ не выдавал диагностических сообщений о том, что переменная "const" не инициализирована. Эта регрессия была устранена в Visual Studio 2017 версии 15.3. Для следующего примера кода теперь выдается "предупреждение C4132: 'Значение': объект const необходимо инициализировать":

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

### <a name="stdisconvertible-for-array-types"></a>std::is_convertible для типов массива

В предыдущих версиях компилятора класс [std::is_convertible](standard-library/is-convertible-class.md) выдавал неверные результаты для типов массива. Из-за этого разработчикам библиотек необходимо было особым образом обрабатывать в компиляторе Microsoft Visual C++ признаки типа `std::is_convertible<...>`. В следующем примере статические функции assert успешно срабатывают в предыдущих версиях Visual Studio, но в Visual Studio 2017 версии 15.3 завершаются ошибкой:

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

### <a name="private-destructors-and-stdisconstructible"></a>Закрытые деструкторы и std::is_constructible

Предыдущие версии компилятора не проверяли, является ли деструктор закрытым, при получении результата [std::is_constructible](standard-library/is-constructible-class.md). Теперь это принимается во внимание. В следующем примере статические функции assert успешно срабатывают в предыдущих версиях Visual Studio, но в Visual Studio 2017 версии 15.3 завершаются ошибкой:

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

Предыдущим версиям компилятора иногда не удавалось обнаружить неоднозначность, когда при использовании объявлений и при поиске функций по аргументам выявлялись различные кандидаты. Это может привести к некорректному выбору перегрузки и непредсказуемому поведению в среде выполнения. В следующем примере Visual Studio 2017 версии 15.3 корректно выдает ошибку C2668, неоднозначный вызов перегруженной функции "f":

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

При локальном объявлении функции скрываются внутри области, поэтому поиск по аргументам не осуществляется. Но предыдущие версии компилятора в этом случае выполняли поиск функции по аргументам, что могло привести к некорректному выбору перегрузки и непредсказуемому поведению в среде выполнения. Как правило, ошибка возникает из-за неправильной сигнатуры в локальном объявлении функции. В следующем примере Visual Studio 2017 версии 15.3 корректно выдает ошибку C2660, функция "f" не принимает 2 аргумента.

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

Члены класса инициализируются в порядке их объявления, а не порядке их отображения в списках инициализаторов. В предыдущих версиях компилятора, когда порядок списка инициализаторов отличался от порядка объявления, никакого предупреждения не выводилось. Это могло приводить к неопределенному поведению во время выполнения, если инициализация одного члена зависела от другого уже инициализированного члена в списке. В следующем примере Visual Studio 2017 версии 15.3 (с параметром **/Wall**) выдает "предупреждение C5038: данные-член 'A::y' будет инициализирован после данных-члена 'A::x'":

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Чтобы устранить проблему, список инициализатора должен иметь тот же порядок, что и объявления. Похожее предупреждение возникает, когда один инициализатор или оба ссылаются на члены базового класса.

Обратите внимание, что это предупреждение по умолчанию отключено и относится только к коду, скомпилированному с параметром **/Wall**.

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

### <a name="tr1"></a>Пространство имен std::TR1 является нерекомендуемым

Нестандартное пространство имен `std::tr1` помечено как нерекомендуемое в режимах C++14 и C++17. В Visual Studio 2017 версии 15.5 приведенный ниже код вызывает предупреждение C4996:

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
warning C4996: 'std::tr1': warning STL4002: The non-Standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
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

### <a name="annex_d"></a>Функции стандартной библиотеки в приложении D помечены как нерекомендуемые

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
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ Standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
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

В Visual Studio 2017 версии 15.5 компилятор C больше не создает предупреждения C4001 и C4179. Ранее они создавались только при использовании параметра компилятора **/Za**.  Предупреждения больше не нужны, так как однострочные комментарии являлись частью стандарта C с момента выхода C99.

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

Если код не должен поддерживать обратную совместимость, можно избежать появления предупреждений, удалив подавление предупреждений C4001/C4179. Если код должен поддерживать обратную совместимость, подавите вывод только предупреждения C4619.

```C
/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="declspec-attributes-with-extern-c-linkage"></a>Атрибуты __declspec с компоновкой extern "C" 

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

Это новое предупреждение C4768 выдается для некоторых заголовков Windows SDK, которые поставлялись с Visual Studio 2017 15.3 или более ранними версиями (например, с версией 10.0.15063.0, также известной как пакет SDK для RS2). Однако в более поздних версиях заголовков Windows SDK (в частности, ShlObj.h и ShlObj_core.h) ошибка была исправлена, поэтому это предупреждение не создается. При появлении этого предупреждения от заголовков Windows SDK можно выполнить следующие действия:

1. Переключитесь на последнюю версию Windows SDK, поставляемую вместе с выпуском Visual Studio 2017 версии 15.5.
2. Отключите предупреждение вокруг #include инструкции заголовка пакета Windows SDK:

   ```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>Компоновка extern constexpr 

В более ранних версиях Visual Studio компилятор всегда обеспечивал переменной `constexpr` внутреннюю компоновку даже в том случае, когда переменная была помечена как `extern`. В Visual Studio 2017 версии 15.5 новый параметр компилятора (**/Zc:externConstexpr**) обеспечивает корректное поведение, соответствующее стандартам. В конечном счете это будет поведением по умолчанию.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Если файл заголовка содержит переменную, объявленную `extern constexpr`, она должна быть помечена как `__declspec(selectany)` для правильного объединения повторяющихся объявлений:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>typeid нельзя использовать с неполным типом класса

В более ранних версиях Visual Studio компилятор неправильно разрешал выполнение следующего кода, что приводило к выводу потенциально неверных сведений о типе. В Visual Studio 2017 версии 15.5 компилятор правильно выдает сообщение об ошибке:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdisconvertible-target-type"></a>Целевой тип std::is_convertible

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

### <a name="noexcept_removal"></a> Удаление спецификации динамических исключений и noexcept

В C++17 `throw()` является псевдонимом для `noexcept`, `throw(<type list>)` и `throw(...)` удалены, а определенные типы могут включать `noexcept`. Это может привести к проблемам совместимости источника с кодом, который соответствует C++14 или более ранней версии. Параметр **/Zc:noexceptTypes-** можно использовать для возврата к версии C++14 `noexcept` при использовании режима C++17 в целом. Это позволяет обновить исходный код для соответствия C++17, не переписывая весь код `throw()`.

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

Статические члены данных constexpr теперь являются неявно встроенными. Это означает, что их объявления в пределах класса теперь являются определениями. Использование внешних определений для статических членов данных constexpr избыточно и не рекомендуется. Если в Visual Studio 2017 версии 15.5 использовать параметр **/std:c++17**, следующий код теперь выдает предупреждение C5041: *'size': невстроенное определение статических данных-члена constexpr не требуется и является нерекомендуемым в C++17*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>Теперь предупреждение C4768 extern "C" __declspec(...) включено по умолчанию

Это предупреждение было добавлено в Visual Studio 2017 версии 15.3, но было отключено по умолчанию. В Visual Studio 2017 версии 15.5 оно включено по умолчанию. Дополнительные сведения см. в разделе [Новое предупреждение для атрибутов declspec](#declspec).

### <a name="defaulted-functions-and-declspecnothrow"></a>Функции по умолчанию и __declspec(nothrow)

Компилятор ранее разрешал объявление установленных по умолчанию функций с `__declspec(nothrow)`, если соответствующие базовые функции или функции-члены разрешали исключения. Это противоречит стандарту C++ и может привести к неопределенному поведению во время выполнения. Согласно стандарту такие функции должны быть определены как удаленные, если имеется несовпадение спецификации исключений.  Если указан параметр **/std:c++17**, приведенный ниже код выдает ошибку C2280: *попытка ссылки на удаленную функцию. Функция была неявно удалена из-за несовместимости спецификации явного исключения со спецификацией неявного объявления.*:


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
### <a name="noexcept-and-partial-specializations"></a>noexcept и частичные специализации
С noexcept в системе типов частичные специализации для сопоставления отдельных "вызываемых" типов могут не пройти компиляцию или выбор основного шаблона из-за отсутствующей частичной специализации для указателей на функции noexcept.

В таких случаях может потребоваться добавить дополнительные частичные специализации для обработки указателей на функции noexcept и указателей noexcept на функции-члены. Эти перегрузки допустимы только в режиме **/std:c++17**. Если необходимо обеспечивать обратную совместимость с C++14 и вы создаете код, который будут использовать другие пользователи, следует защитить эти новые перегрузки внутри директив `#ifdef`. Если вы работаете в автономном модуле, то вместо использования защиты `#ifdef` можно просто выполнить компиляцию с параметром **/Zc:noexceptTypes-**.

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

## <a name="see-also"></a>См. также

[Соответствие стандартам языка Visual C++](visual-cpp-language-conformance.md)  
