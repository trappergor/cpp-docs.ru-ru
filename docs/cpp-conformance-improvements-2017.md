---
title: "Улучшения соответствия компилятора C++ | Документы Майкрософт"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: BrianPeek
ms.author: brpeek
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
translationtype: Human Translation
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: b26df320266a1465e214c70c29c7077d04ffb4b9
ms.lasthandoff: 03/06/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Улучшения соответствия C++ в [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]

## <a name="new-language-features"></a>Новые возможности языка  
Благодаря поддержке обобщенного constexpr и NSDMI для статистических выражений теперь компилятор готов к использованию функций, добавленных в стандарте C++14. Обратите внимание, что в компиляторе по-прежнему отсутствует несколько функций из стандартов C++11 и C++98.

### <a name="c11"></a>C++11
**Поддержка выражения SFINAE в дополнительных библиотеках**. В компиляторе Visual C++ улучшена поддержка выражения SFINAE, которое необходимо для вычета аргумента шаблона и подстановки, где выражения decltype и constexpr могут отображаться в виде параметров шаблона. Дополнительные сведения см. в разделе [Усовершенствования выражения SFINAE в версии-кандидате Visual Studio 2017](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3). 


### <a name="c-14"></a>C++ 14
**NSDMI для статистических выражений**. Статистическое выражение является массивом или классом без предоставленного пользователем конструктора, без закрытых или защищенных нестатических данных-членов, без базовых классов и виртуальных функций. Начиная с версии C++14, статистические выражения могут содержать инициализаторы членов. Дополнительные сведения см. в разделе [Инициализаторы членов и статистические выражения](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

**Расширенный constexpr**. Выражения, объявленные как constexpr, теперь могут содержать определенные виды объявлений, операторы if и switch, операторы циклов и изменения объектов, время жизни которых началось в вычислении выражения constexpr. Кроме того, больше не требуется, чтобы нестатическая функция-член была явной константой. Дополнительные сведения см. в статье [Нестрогие ограничения для функций constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html). 

### <a name="c17"></a>C++17
**Сжатый static_assert** (доступен с /std:c++latest). В C++17 параметр сообщения для static_assert является необязательным. Дополнительные сведения см. в разделе [Расширение static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf). 

**атрибут [[fallthrough]]** (доступен с /std:c++latest) Атрибут [[fallthrough]] можно использовать в контексте операторов switch как подсказку для компилятора о том, что требуется поведение проваливания. Это позволит избежать вывода предупреждений компилятора. Дополнительные сведения см. в разделе [Формулировка для атрибута [[fallthrough]]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf). 

**Обобщенные циклы for на основе диапазона** (параметр компилятора не требуется). Для циклов for на основе диапазона больше не требуется, чтобы функции begin() и end() возвращали объекты одного типа. Это позволяет функции end() возвращать объект sentinel, используемый, например, диапазонами, как определено в предложении Ranges-V3. Дополнительные сведения см. в разделе [Обобщение цикла For на основе диапазона](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) и в документе о [библиотеке range-v3 на сайте GitHub](https://github.com/ericniebler/range-v3). 


Полный список улучшений соответствия вплоть до Visual Studio 2015 с обновлением 3 см. в разделе [Новые возможности Visual C++ 2003–2015](https://msdn.microsoft.com/en-us/library/mt723604.aspx).

## <a name="bug-fixes"></a>Исправления ошибок
### <a name="copy-list-initialization"></a>Инициализация копии списка
Visual Studio 2017 правильно вызывает ошибки компилятора, связанные с созданием объектов с использованием списков инициализаторов, которые не обнаруживались в Visual Studio 2015 и могли приводить к сбоям или неопределенному поведению во время выполнения.  Согласно N4594 13.3.1.7p1 в инициализации копии списка компилятор должен учитывать явный конструктор для разрешения перегрузки, но должен выдавать ошибку, если эта перегрузка выбирается на самом деле. 

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
struct MyList {
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
Visual Studio 2017 правильно выдает ошибку, если левый операнд в операции условного вычисления является недопустимым в контексте constexpr. Следующий код компилируется в Visual Studio 2015, но не в Visual Studio 2017:

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // error starting in Visual Studio 2017
}
```
Чтобы исправить эту ошибку, объявите функцию array::size() как constexpr или удалите квалификатор constexpr из f. 

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
                        // as an argument to a variadic function
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
Для строк, созданных и управляемых с помощью CStringW, следует использовать предоставленный "оператор LPCWSTR()" для приведения объекта CStringW в указателю C, ожидаемому строкой формата.

```cpp  
CStringW str1;
CStringW str2;
str1.Format(… , static_cast<LPCWSTR>(str2));
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
Чтобы исправить эту ошибку, объявите оператор int() как константу. 

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
template <class T, class ReturnT, class... ArgsT> class IsCallable
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

### <a name="default-initializers-for-value-class-members-ccli"></a>Инициализаторы по умолчанию для членов класса значения (C++/CLI)
В Visual Studio 2015 и более ранних версиях компилятор допускал (но игнорировал) инициализатор членов по умолчанию для члена класса значений.  Инициализатор по умолчанию для класса значений всегда инициализирует члены нулевым значением. Конструктор по умолчанию не допускается.  В Visual Studio 2017 инициализаторы членов по умолчанию вызывают ошибку компилятора, как показано в следующем примере:

```cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Индексаторы по умолчанию (C++/CLI)
В Visual Studio 2015 и более ранних версиях в некоторых случаях компилятор неправильно определял свойство по умолчанию как индексатор по умолчанию. Эту проблему удалось решить с использованием значения по умолчанию идентификатора для доступа к свойству. Возможное решение само по себе стало создавать проблемы после того, как значение умолчанию было представлено как ключевое слово в C++&11;. Поэтому в Visual Studio 2017 были исправлены ошибки, требующие обходного решения. Теперь компилятор выдает ошибку, когда значение по умолчанию используется для доступа к свойству по умолчанию для класса.

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

## <a name="see-also"></a>См. также  
[Соответствие стандартам языка Visual C++](visual-cpp-language-conformance.md)  

