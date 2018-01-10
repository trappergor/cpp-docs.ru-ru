---
title: "Новые возможности Visual C++ 2003–2015 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 512665a243a0c24c143242084a51f6b3025c1a19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Новые возможности Visual C++ 2003–2015

**Примечание.** Сведения о Visual Studio 2017 см. в статьях [Новые возможности Visual C++ в Visual Studio 2017](../what-s-new-for-visual-cpp-in-visual-studio.md) и [Улучшения соответствия в Visual C++ в Visual Studio 2017](../cpp-conformance-improvements-2017.md).

В Visual C++ 2015 и более поздних версиях постоянные улучшения соответствия компилятора иногда могут изменить то, как компилятор распознает существующий исходный код. В этом случае во время сборки могут возникнуть новые или другие ошибки или даже поведенческие различия в коде, который был построен ранее и, казалось, работал правильно.  
  
 К счастью, эти различия имеют минимальное влияние или совсем не затрагивают большую часть исходного кода. Если же требуется внести изменения в исходный код, чтобы устранить эти различия, как правило, применяются незначительные исправления. Мы включили много примеров ранее допустимого исходного кода, который может потребоваться изменить *(раньше)*, и исправлений *(теперь)*.  
  
 Несмотря на то, что эти различия могут повлиять на исходный код и другие артефакты сборки, они не влияют на совместимость двоичных файлов между обновлениями версий Visual C++. На совместимость двоичных файлов может повлиять более серьезный тип изменений (*критическое изменение*), но нарушения совместимости происходят только между основными версиями Visual C++. Например, между Visual C++ 2013 и Visual C++ 2015. Сведения о критических изменениях, введенных со времени выпуска Visual C++ 2013 до выпуска Visual C++ 2015, см. в статье [Журнал изменений Visual C++ 2003–2015](../porting/visual-cpp-change-history-2003-2015.md).  
  
-   [Улучшения соответствия в Visual C++ 2015](#VS_RTM)  
  
-   [Улучшения соответствия в обновлении 1](#VS_Update1)  
  
-   [Улучшения соответствия в обновлении 2](#VS_Update2)  
  
-   [Улучшения соответствия в обновлении 3](#VS_Update3)  
  
##  <a name="VS_RTM"></a> Улучшения соответствия в Visual C++ 2015  
  
-   Параметр /Zc:forScope-  
  
     Параметр компилятора **/Zc:forScope-** является нерекомендуемым и будет удален в будущем выпуске.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Этот параметр обычно использовался, чтобы разрешить нестандартный код, использующий переменные цикла после того момента, когда, согласно стандарту, они должны выйти из области действия. Это требовалось только при компиляции с параметром /Za, поскольку без него использование переменной цикла for после конца цикла всегда разрешено. Если вас не интересует соответствие стандартам (например, если код не предназначен для переноса в другие компиляторы), можно отключить параметр /Za (или задать для свойства "Отключить расширения языка" значение "Нет"). Если вам требуется написать переносимый и совместимый со стандартами код, следует переписать его в соответствии со стандартом, переместив объявления таких переменных в точку за пределами цикла.  
  
    ```  
    // zc_forScope.cpp  
    // compile with: /Zc:forScope- /Za  
    // C2065 expected  
    int main() {  
       // Uncomment the following line to resolve.  
       // int i;  
       for (int i =0; i < 1; i++)  
          ;  
       i = 20;   // i has already gone out of scope under /Za  
    }  
    ```  
  
-   **Параметр компилятора /Zg**  
  
     Параметр компилятора /Zg (создать прототипы функций) больше не доступен. Ранее этот параметр компилятора был признан нерекомендуемым.  
  
-   Вы больше не сможете выполнять модульные тесты с использованием C++/CLI из командной строки с помощью mstest.exe. Вместо этого используйте vstest.console.exe. См. раздел [VSTest.Console.exe command-line options](/devops-test-docs/test/vstest-console-exe-command-line-options) (Параметры командной строки для VSTest.Console.exe).  
  
-   **Ключевое слово mutable**  
  
     Описатель класса хранения `mutable` больше нельзя использовать в местах, где ранее он компилировался без ошибок. Теперь компилятор выдает ошибку C2071 (недопустимый класс хранения). Согласно стандарту, описатель mutable может применяться только к именам членов класса данных и не может применяться к именам, объявленным постоянными или статическими, а также не может применяться к элементам ссылки.  
  
     Рассмотрим следующий пример кода:  
  
    ```  
    struct S {  
        mutable int &r;  
    };  
    ```  
  
     Предыдущие версии компилятора Visual C++ принимали его, но теперь компилятор выдает следующую ошибку:  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     Чтобы исправить ошибку, просто удалите избыточное ключевое слово mutable.  
  
-   **char_16_t и char32_t**  
  
     `char16_t` или `char32_t` больше нельзя использовать в качестве псевдонимов в typedef, поскольку теперь эти типы считаются встроенными. Пользователи и разработчики библиотек повсеместно определяли char16_t и char32_t как псевдонимы uint16_t и uint32_t, соответственно.  
  
    ```  
    #include <cstdint>  
  
    typedef uint16_t char16_t; //C2628  
    typedef uint32_t char32_t; //C2628  
  
    int main(int argc, char* argv[])  
    {  
    uint16_t x = 1; uint32_t y = 2;  
    char16_t a = x;   
    char32_t b = y;   
    return 0;  
    }  
    ```  
  
     Чтобы обновить код, удалите объявления typedef и переименуйте другие идентификаторы, которые конфликтуют с этими именами.  
  
-   **Параметры шаблона, не являющиеся типами**  
  
     Определенный код с параметрами шаблона, не являющимися типами, теперь правильно проверяется на совместимость типов при предоставлении явно заданных аргументов шаблона. Например, следующий код компилировался без ошибок в предыдущих версиях Visual C++.  
  
    ```  
    struct S1  
    {  
    void f(int);  
    void f(int, int);  
    };  
  
    struct S2  
    {  
    template <class C, void (C::*Function)(int) const> void f() {}  
    };  
  
    void f()  
    {  
    S2 s2;  
    s2.f<S1, &S1::f>();  
    }  
  
    ```  
  
     Текущий компилятор правильно выдает ошибку, поскольку тип параметра шаблона не соответствует аргументу шаблона (параметр является указателем на член-константу, но функция f не является константной):  
  
    ```Output  
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'  
    ```  
  
     Чтобы устранить эту ошибку в коде, убедитесь, что используемый тип аргумента шаблона соответствует объявленному типу параметра шаблона.  
  
-   **__declspec(align)**  
  
     Компилятор больше не принимает `__declspec(align)` для функций. Оно всегда игнорировалось, но теперь вызывает ошибку компилятора.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Чтобы устранить эту проблему, удалите `__declspec(align)` из объявления функции. Поскольку оно не оказывает никакого влияния, его удаление ничего не меняет.  
  
-   **Обработка исключений**  
  
     Существует несколько изменений в обработке исключений. Во-первых, объекты исключений должны быть доступны для перемещения или копирования. Следующий код компилировался в [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], но не компилируется в [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:  
  
    ```  
    struct S {  
    public:  
        S();  
    private:  
        S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     Проблема заключается в том, что конструктор копии является закрытым, поэтому нельзя скопировать объект так, как это происходит во время обычной обработки исключения. То же самое происходит, когда конструктор копии объявлен `explicit`.  
  
    ```  
    struct S {  
        S();  
        explicit S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     Для обновления кода убедитесь в том, конструктор копии для объекта исключения является открытым и не отмечен как `explicit`.  
  
     Перехват исключения по значению также требует, чтобы объект исключения был доступен для копирования. Следующий код компилировался в [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], но не компилируется в [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:  
  
    ```  
    struct B {  
    public:  
        B();  
    private:  
        B(const B &);  
    };  
  
    struct D : public B {  
    };  
  
    int main()  
    {  
        try  
        {  
        }  
        catch (D d) // error  
        {  
        }  
    }  
  
    ```  
  
     Эту проблему можно устранить, изменив тип параметра для `catch` на ссылку.  
  
    ```  
    catch(D& d)  
    {  
    }  
    ```  
  
-   **Строковые литералы с последующими макросами**  
  
     Компилятор теперь поддерживает определенные пользователем литералы. В результате строковые литералы, за которыми следуют макросы без промежуточных пробелов, интерпретируются как определенные пользователем литералы, которые могут вызывать ошибки или приводить к непредвиденным результатам. Например, в предыдущих компиляторах следующий код компилируется успешно:  
  
    ```  
    #define _x "there"  
    char* func() {  
        return "hello"_x;  
    }  
    int main()  
    {  
        char * p = func();  
        return 0;  
    }  
    ```  
  
     Компилятор интерпретировал этот код как строковый литерал hello с последующим макросом, который представляет собой расширяющийся there, после чего два строковых литерала были объединены в один. В [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] компилятор интерпретирует этот код как определенный пользователем литерал, но поскольку соответствующий определяемый пользователем литерал _x не определен, он выдает ошибку.  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     Чтобы устранить эту проблему, добавьте пробел между строковым литералом и макросом.  
  
-   **Смежные строковые литералы**  
  
     Аналогично предыдущему случаю, из-за соответствующих изменений в синтаксическом анализе строк смежные строковые литералы (с широкими или узкими символами) без пробела интерпретировались в предыдущих версиях Visual C++ как одна объединенная строка. Теперь в [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] необходимо добавлять пробелы между двумя строками. Например, необходимо изменить следующий код:  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     Просто добавьте пробел между двумя строками.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Размещаемые операторы new и delete**  
  
     В оператор delete были внесены изменения, чтобы привести его в соответствие со стандартом C++14. Сведения об изменении стандартов можно найти на странице [Освобождение с размером в C++](http://isocpp.org/files/papers/n3778.html). Эти изменения добавляют форму глобального оператора delete, принимающего параметр размера. Критическое изменение заключается в том, что если ранее использовался оператор delete с такой же сигнатурой (для соответствия размещаемому оператору new), вы получите ошибку компилятора (C2956, которая возникает в точке, где используется размещаемый оператор new, поскольку это именно та позиции в коде, где компилятор пытается определить соответствующий оператор delete).  
  
     Функция `void operator delete(void *, size_t)` была размещаемым оператором delete, соответствующим размещаемой функции new "void \* operator new(size_t, size_t)" в C++11. С появлением освобождения с размером в C++14 эта функция delete теперь является *функцией обычного освобождения* (глобальный оператор delete). Согласно стандарту, если использование размещаемого оператора new ищет соответствующую функцию delete и находит функции обычного освобождения, программа сформирована некорректно.  
  
     Например, предположим, что код определяет как размещаемый оператор new, так и размещаемый оператор delete:  
  
    ```  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     Проблема возникает из-за совпадения сигнатур функций между определенным вами размещаемым оператором new и новым глобальным оператором delete с размером. Рассмотрим, можно ли использовать другой тип, отличный от size_t, для любых размещаемых операторов new и delete.  Обратите внимание, что тип size_t typedef зависит от компилятора; для unsigned int в Visual C++ используется typedef. Хорошим решением является использование перечисляемого типа, например:  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     Затем измените определение размещаемых операторов new и delete, чтобы использовать этот тип в качестве второго аргумента вместо size_t. Также потребуется обновить вызовы размещаемого оператора new для передачи нового типа (например, с помощью `static_cast<my_type>` для преобразования из целого числа) и обновить определение операторов new и delete для приведения к типу integer. Не нужно использовать для этого перечисление; тип класса с членом size_t также будет работать.  
  
     Альтернативным решением является возможность полного удаления размещаемого оператора new. Если ваш код использует размещаемый оператор new для реализации пула памяти, где аргументом размещения является размер выделяемого или удаляемого объекта, функция освобождения с размером может подойти для замены кода пула памяти, что позволит избавиться от функций размещения и просто использовать собственный оператор delete с двумя аргументами вместо функции размещения.  
  
     Если вы не хотите немедленно обновлять код, можно вернуться к старому поведению с помощью параметра компилятора /Zc:sizedDealloc-. При использовании этого параметра функции delete с двумя аргументами не существуют и не конфликтуют с вашим размещаемым оператором delete.  
  
-   **Элементы данных объединений**  
  
     Элементы данных объединений больше не могут иметь ссылочные типы. Следующий код успешно компилировался в [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], но приводит к ошибке в [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
    ```  
    union U1 {  
        const int i;  
    };  
    union U2 {  
       int &i;  
    };  
    union U3 {  
        struct {int &i;};  
    };  
    ```  
  
     Предыдущий код вызывает следующие ошибки:  
  
    ```Output  
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type  
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type  
    ```  
  
     Чтобы устранить эту проблему, измените ссылочные типы на указатель или значение. Для изменения типа на указатель требуется внести изменения в код, который использует поле объединения. При изменении кода на значение будут изменены данные, хранящиеся в объединении, что повлияет на другие поля, поскольку поля в типах объединений имеют общую память. В зависимости от величины значения оно также может изменить размер объединения.  
  
-   Анонимные объединения стали более полно соответствовать требованиям стандарта. Компилятор предыдущей версии создавал для анонимных объединений явный конструктор и деструктор. В [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] они удалены.  
  
    ```  
    struct S {  
      S();  
     };  
  
     union {  
      struct {  
       S s;  
      };  
     } u; // C2280  
    ```  
  
     Предыдущий код вызывает следующие ошибки в [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     Чтобы устранить эту проблему, предоставьте собственные определения конструктора и/или деструктора.  
  
    ```  
    struct S {  
    // Provide a default constructor by adding an empty function body.  
    S() {}   
    };  
  
    union {  
    struct {  
    S s;  
    };  
    } u;  
    ```  
  
-   **Объединения с анонимными структурами**  
  
     В целях обеспечения соответствия стандарту было изменено поведение для членов анонимных структур в объединениях. Конструктор для членов анонимных структур в объединении больше не вызывается неявно при создании такого объединения. Кроме того, деструктор для членов анонимных структур в объединении больше не вызывается неявно при выходе такого объединения из области действия. Рассмотрим следующий код, в котором объединение U содержит анонимную структуру, содержащую элемент, представляющий собой именованную структуру S с деструктором.  
  
    ```  
    #include <stdio.h>  
    struct S {  
        S() { printf("Creating S\n"); }  
        ~S(){ printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
        S s;  
    };  
        U() {}  
        ~U(){}  
    };  
  
    void f()  
    {  
        U u;  
        // Destructor implicitly called here.  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     В [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] конструктор для S вызывается при создании объединения, а деструктор для S вызывается при очистке стека для функции f. Однако в [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] конструктор и деструктор не вызываются. Компилятор выдает предупреждение об изменении этого поведения.  
  
    ```Output  
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called  
    ```  
  
     Чтобы восстановить первоначальное поведение, присвойте анонимной структуре имя. Поведение неанонимных структур во время выполнения остается прежним независимо от версии компилятора.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        S() { printf("Creating S.\n"); }  
        ~S() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        } namedStruct;  
        U() {}  
        ~U() {}  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     Кроме того, попробуйте переместить код конструктора и деструктора в новые функции и добавьте вызовы этих функций из конструктора и деструктора для объединения.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        void Create() { printf("Creating S.\n"); }  
        void Destroy() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        };  
        U() { s.Create();  }  
        ~U() { s.Destroy(); }  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
    char s[1024];  
    printf("Press any key.\n");  
    gets_s(s);  
    return 0;  
    }  
    ```  
  
-   **Разрешение шаблонов**  
  
     В разрешение имен для шаблонов были внесены изменения. При рассмотрении кандидатов для разрешения имени d C++ может возникнуть ситуация, когда одно или несколько рассматриваемых имен приводят к созданию недопустимого экземпляра шаблона. Эти недопустимые экземпляры обычно не вызывают ошибки компилятора, данный принцип известен как SFINAE (сбой подстановки не является ошибкой).  
  
     Если принцип SFINAE требует от компилятора создать экземпляр специализации шаблона класса, то любые ошибки, возникающие во время этого процесса, являются ошибками компилятора. В предыдущих версиях компилятор игнорирует такие ошибки. Рассмотрим следующий пример кода:  
  
    ```  
    #include <type_traits>  
  
    template<typename T>  
    struct S  
    {  
    S() = default;  
    S(const S&);  
    S(S&&);  
  
    template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type>  
    S(S<U>&&);  
    };  
  
    struct D;  
  
    void f1()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    struct B  
    {  
    };  
  
    struct D : public B  
    {  
    };  
  
    void f2()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    ```  
  
     При компиляции с помощью текущего компилятора появляется следующая ошибка:  
  
    ```Output  
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'  
    ..\t331.cpp(14): note: see declaration of 'D'  
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled  
            with  
            [  
                T=D,  
                U=D  
            ]  
    ```  
  
     Это происходит из-за того, что при первом вызове is_base_of класс "D" еще не был определен.  
  
     В этом случае исправление заключается в том, чтобы не использовать такие характеристики типов, пока не будет определен класс. При перемещении определений B и D в начало файла с кодом ошибка будет устранена. Если определения указаны в файлах заголовков, проверьте порядок операторов include для этих файлов заголовков, чтобы убедиться в том, что все определения классов компилируются до использования проблемных шаблонов.  
  
-   **Конструкторы копии**  
  
     Как в [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)], так и в Visual Studio 2015, если пользователь создал в классе конструктор перемещения, но не создал конструктор копии, конструктор копии будет создан компилятором. В Dev14 этот неявно создаваемый конструктор копии также помечается как "= delete".  
  
##  <a name="VS_Update1"></a> Улучшения соответствия в обновлении 1  
  
-   **Закрытые виртуальные базовые классы и косвенное наследование**  
  
     В предыдущих версиях компилятора производному классу разрешалось вызывать функции-члены *косвенных*`private virtual` базовых классов. Это поведение было неправильным и не соответствовало стандарту языка C++. Компилятор больше не принимает код, написанный таким образом, и выдает в результате ошибку C2280.  
  
    ```Output  
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    class base  
    {  
    protected:  
        base();  
        ~base();  
    };  
  
    class middle: private virtual base {};class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  //   
    }  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    class base;  // as above  
  
    class middle: protected virtual base {};  
    class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
     - или -  
  
    ```  
    class base;  // as above  
  
    class middle: private virtual base {};  
    class top: public virtual middle, private virtual bottom {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
-   **Перегруженный оператор new и оператор delete**  
  
     В предыдущих версиях компилятора можно было объявлять `operator new` , не являющийся членом, и `operator delete` , не являющийся членом, статически и в пространствах имен, отличных от глобального пространства имен.  При этом создавался риск того, что программа вызовет не ту реализацию оператора `new` или `delete` , которую планировал программист, результатом чего будет неправильное поведение во время выполнения. Компилятор больше не принимает код, написанный таким образом, и выдает вместо этого ошибку C2323.  
  
    ```Output  
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'  
    ```  
  
     Кроме того, хотя компилятор не выдает соответствующего диагностического сообщения, встроенный оператор new считается некорректным.  
  
-   **Вызов "operator *тип*()" (пользовательское преобразование) для типов, не являющихся классами**  
  
     В предыдущих версиях компилятора допускался вызов "operator *тип*()" для типов, не являющихся классами, при этом он игнорировался без вывода предупреждения. Это создавало риск создания некорректного кода и непредсказуемого поведения во время выполнения. Компилятор больше не принимает код, написанный таким образом, и выдает вместо этого ошибку C2228.  
  
    ```Output  
    error C2228: left of '.operator type' must have class/struct/union  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column.operator index_t());  // error C2228  
    }  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'  
    }  
    ```  
  
-   **Избыточное ключевое слово typename в сложных спецификаторах типов**  
  
     В предыдущих версиях компилятора допускалось ключевое слово `typename` в сложных спецификаторах типов. Код, написанный таким образом, семантически неправилен. Компилятор больше не принимает код, написанный таким образом, и выдает вместо этого ошибку C3406.  
  
    ```Output  
    error C3406: 'typename' cannot be used in an elaborated type specifier  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    template <typename class T>  
    class container;  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case  
    class container;  
    ```  
  
-   **Выведение типов массивов из списка инициализаторов**  
  
     В предыдущих версиях компилятора не поддерживалось выведение типов массивов из списка инициализаторов. Теперь компилятор поддерживает подобное выведение типов, и в результате вызовы шаблонов функций с помощью списков инициализаторов теперь могут быть неоднозначными либо может выбираться не та перегрузка, что в предыдущих версиях компилятора. Для устранения этой проблемы теперь необходимо явно указывать в программе требуемую перегрузку.  
  
     Если в результате этого нового поведения при разрешении перегрузки дополнительный кандидат считается равноценным ранее существовавшему, вызов становится неоднозначным, и компилятор выдает ошибку C2668.  
  
    ```Output  
    error C2668: 'function' : ambiguous call to overloaded function.  
    ```  
  
     Пример 1. Неоднозначный вызов перегруженной функции (раньше)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now considers this call ambiguous, and issues a compiler error  
        f({3});  error C2668: 'f' ambiguous call to overloaded function  
    }  
    ```  
  
     Пример 1. Неоднозначный вызов перегруженной функции (теперь)  
  
    ```cpp  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.  
        f(3);  
    }  
    ```  
  
     Если в результате этого нового поведения при разрешении перегрузки дополнительный кандидат считается лучше ранее существовавшего, вызов разрешается однозначно в нового кандидата, что приводит к изменению поведения программы, которое, возможно, не планировалось программистом.  
  
     Пример 2. Изменение в разрешении перегрузки (раньше)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)  
    struct S  
    {  
        int i;  
        int j;  
    };  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead  
        f({1, 2});  
    }  
    ```  
  
     Пример 2. Изменение в разрешении перегрузки (теперь)  
  
    ```cpp  
    struct S;  // as before  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.  
        f(S{1, 2});  
    }  
    ```  
  
-   **Восстановление предупреждений, касающихся оператора switch**  
  
     В предыдущей версии компилятора были удалены ранее существовавшие предупреждения, касающиеся операторов `switch` . Теперь эти предупреждения восстановлены. Компилятор теперь выдает эти предупреждения. Предупреждения, связанные с определенными вариантами (включая вариант по умолчанию), теперь выдаются в строке, содержащей неправильный вариант, а не в последней строке оператора switch. В результате того, что теперь предупреждения выдаются не в тех строках, что раньше, предупреждения, которые ранее подавлялись с помощью `#pragma warning(disable:####)` , могут больше не подавляться, как планировалось. Для правильного подавления этих предупреждений может потребоваться перенести директиву `#pragma warning(disable:####)` в строку перед первым потенциально неправильным вариантом. Ниже приведены восстановленные предупреждения.  
  
    ```Output  
    warning C4060: switch statement contains no 'case' or 'default' labels  
    ```  
  
    ```Output  
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label  
    ```  
  
    ```Output  
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled  
    ```  
  
    ```Output  
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'  
    ```  
  
    ```Output  
    warning C4064: switch of incomplete enum 'flags'  
    ```  
  
    ```Output  
    warning C4065: switch statement contains 'default' but no 'case' labels  
    ```  
  
    ```Output  
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'  
    ```  
  
    ```Output  
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given  
    ```  
  
     Пример предупреждения C4063 (раньше)  
  
    ```cpp  
    class settings  
    {  
    public:  
        enum flags  
        {  
            bit0 = 0x1,  
            bit1 = 0x2,  
            ...  
        };  
        ...  
    };  
  
    int main()  
    {  
        auto val = settings::bit1;  
  
        switch (val)  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // warning C4063  
            break;  
        }  
    };  
    ```  
  
     Пример предупреждения C4063 (теперь)  
  
    ```cpp  
    class settings {...};  // as above  
  
    int main()  
    {  
        // since C++11, use std::underlying_type to determine the underlying type of an enum  
        typedef std::underlying_type<settings::flags>::type flags_t;  
  
        auto val = settings::bit1;  
  
        switch (static_cast<flags_t>(val))  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // ok  
            break;  
        }  
    };  
    ```  
  
     Примеры других восстановленных предупреждений приведены в соответствующей документации.  
  
-   **#include: использование спецификатора parent-directory ".." в пути** (касается только /Wall /WX)  
  
     В предыдущих версиях компилятора не определялись случаи использования спецификатора parent-directory ".." в пути директив  `#include` . Код, написанный таким образом, обычно предназначен для включения заголовков, находящихся за пределами проекта, путем неправильного использования относительных путей к проектам. Это прежнее поведение создавало риск того, что при компиляции программы мог включаться не тот файл исходного кода, который планировал программист, или что эти относительные пути невозможно было бы перенести в другие среды сборки. Компилятор теперь обнаруживает код, написанный таким образом, уведомляет о нем программиста и выдает необязательное предупреждение C4464, если оно включено.  
  
    ```Output  
    warning C4464: relative include path contains '..'  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    #include "..\headers\C4426.h"  // emits warning C4464  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories  
    ```  
  
     Кроме того, хотя компилятор не выдает соответствующего диагностического сообщения, мы также рекомендуем не использовать спецификатор parent-directory ".." для указания включаемых в проект каталогов.  
  
-   **#pragma optimize() выходит за пределы файла заголовка** (касается только /Wall /WX)  
  
     В предыдущих версиях компилятора не определялись изменения в параметрах флагов оптимизации за пределами файла заголовка, включенного в запись преобразования. Компилятор теперь обнаруживает код, написанный таким образом, уведомляет о нем программиста и выдает необязательное предупреждение C4426 в месте нахождения неправильного `#include`, если оно включено. Это предупреждение выдается только в том случае, если изменения конфликтуют с флагами оптимизации, установленными аргументами командной строки, переданными в компилятор.  
  
    ```Output  
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  // warning C4426  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  
    ```  
  
-   **Несоответствие #pragma warning(push)** и **#pragma warning(pop)** (касается только /Wall /WX)  
  
     В предыдущих версиях компилятора не обнаруживалось сопоставление изменений состояния `#pragma warning(push)` с изменениями состояния `#pragma warning(pop)` в другом файле исходного кода, которое редко бывает намеренным. Это создавало риск компиляции программы с набором включенных предупреждений, отличным от того, которое запланировал программист, что могло приводить к неправильному поведению во время выполнения. Компилятор теперь обнаруживает код, написанный таким образом, уведомляет о нем программиста и выдает необязательное предупреждение C5031 в месте нахождения соответствующего `#pragma warning(pop)`, если это предупреждение включено. Это предупреждение включает примечание, ссылающееся на расположение соответствующего #pragma warning(push).  
  
    ```Output  
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    ...  
    #pragma warning(pop)  // pops a warning state not pushed in this source file   
    ...  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'  
    ...  
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031  
    ...  
  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  // pops the warning state pushed in this source file  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    #pragma warning(push)  // pushes the warning state pushed in this source file  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.  
    ...  
    #include "C5031_part2.h"  
    ...  
  
    ```  
  
     Хотя и редко, иногда код намеренно пишется таким образом. Такой код зависит от изменений в порядке `#include`. Мы рекомендуем, чтобы по возможности файлы исходного кода самостоятельно управляли состояниями предупреждений.  
  
-   **Несоответствие #pragma warning(push)** (касается только /Wall /WX)  
  
     В предыдущих версиях компилятора не определялось несоответствие изменений состояния `#pragma warning(push)` в конце записи преобразования. Теперь компилятор обнаруживает код, написанный таким образом, уведомляет о нем программиста и выдает необязательное предупреждение C5032 в месте нахождения несоответствующего выражения #pragma warning(push), если это предупреждение включено. Это предупреждение выдается только в том случае, если в записи преобразования нет ошибок компиляции.  
  
    ```Output  
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5032.h ends without #pragma warning(pop)  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop) // matches #pragma warning (push) on line 1  
    // C5032.h ends  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)  
    ```  
  
-   **В результате усовершенствования отслеживания состояния #pragma warning могут выдаваться дополнительные предупреждения**  
  
     В предыдущей версии компилятора изменения состояния #pragma warning отслеживались недостаточно хорошо для того, чтобы выдавались все необходимые предупреждения. В результате возникал риск того, что некоторые предупреждения могли подавляться в ситуациях, не предусмотренных программистом. Теперь компилятор более тщательно отслеживает состояние #pragma, а особенно изменения состояния #pragma warning внутри шаблонов. При необходимости он также выдает новые предупреждения C5031 и C5032, которые призваны помочь программисту в определении случаев непредусмотренного использования `#pragma warning(push)` и `#pragma warning(pop)`.  
  
     В результате усовершенствованного отслеживания изменения состояния #pragma warning теперь могут выдаваться предупреждения, которые раньше некорректно подавлялись, или предупреждения о проблемах, которые ранее диагностировались неправильно.  
  
-   **Улучшенное определение недостижимого кода**  
  
     Изменения, внесенные в стандартную библиотеку C++, и улучшенная возможность встраивания вызовов функций по сравнению с предыдущими версиями компилятора позволяют компилятору определять недостижимость определенного кода. Это может привести к тому, что предупреждение C4720 будет выдаваться чаще.  
  
    ```Output  
    warning C4720: unreachable code  
    ```  
  
     Зачастую это предупреждение выдается только при компиляции с включенными оптимизациями, так как при этом может встраиваться больше вызовов функций, удаляться избыточный код или могут производиться другие действия, позволяющие определить недостижимость определенного кода. По нашим наблюдениям, предупреждение C4720 начало часто появляться в блоках try/catch, особенно в связи с использованием [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True).  
  
     Пример (раньше)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // ok   
    }  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // warning C4702: unreachable code  
    }  
    ```  
  
##  <a name="VS_Update2"></a> Улучшения соответствия в обновлении 2  
  
-   **В результате частичной поддержки правила SFINAE для выражений могут возникать дополнительные предупреждения и ошибки**  
  
     В предыдущих версиях компилятора из-за отсутствия поддержки правила SFINAE для выражений не анализировались некоторые типы выражений внутри описателей `decltype`. Это поведение было неправильным и не соответствовало стандарту языка C++. В результате непрерывной оптимизации соответствия компилятор теперь анализирует эти выражения и частично поддерживает правило SFINAE для выражений. Поэтому компилятор теперь выдает предупреждения и сообщения об ошибках, найденных в выражениях, которые в предыдущих версиях компилятора не анализировались.  
  
     Если в новой версии анализируется выражение `decltype`, включающее тип, который еще не был объявлен, выдается ошибка компилятора C2039.  
  
    ```Output  
    error C2039: 'type': is not a member of '`global namespace''  
    ```  
  
     Пример 1. Использование необъявленного типа в предыдущих версиях  
  
    ```cpp  
    struct s1  
    {  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  // error C2039  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     Пример 1 в текущей версии  
  
    ```cpp  
    struct s1  
    {  
      template <typename>  // forward declare s2struct s2;  
  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     Если в новой версии анализируется выражение `decltype`, в котором не используется обязательное ключевое слово `typename` для указания на то, что зависимое имя представляет собой тип, выдается предупреждение компилятора C4346, а также ошибка компилятора C2923.  
  
    ```Output  
    warning C4346: 'S2<T>::Type': dependent name is not a type  
    ```  
  
    ```Output  
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'  
    ```  
  
     Пример 2. Зависимое имя не является типом (в предыдущих версиях)  
  
    ```cpp  
    template <typename T>  
    struct s1  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    struct s2  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<S2<T>::type>::type>()));  // warning C4346, error C2923  
    };  
    ```  
  
     Пример 2 в текущей версии  
  
    ```cpp  
    template <typename T> struct s1 {...};  // as above  
    template <typename T> struct s2 {...};  // as above  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<typename S2<T>::type>::type>()));  
    };  
    ```  
  
-   `volatile`Переменные-члены  **не допускают неявно определенных конструкторов и операторов присваивания**  
  
     В предыдущих версиях компилятора допускалось автоматическое создание конструкторов копирования и перемещения по умолчанию, а также операторов присваивания копирования и перемещения по умолчанию для класса, содержащего переменные-члены `volatile`. Это поведение было неправильным и не соответствовало стандарту языка C++. Теперь компилятор рассматривает класс с переменными-членами volatile как имеющий нетривиальные конструкторы и операторы присваивания, что делает невозможным автоматическую реализацию этих операторов по умолчанию.  Если такой класс является членом объединения (или анонимного объединения внутри класса), конструкторы копирования и перемещения и операторы присваивания копирования и перемещения объединения (или класса, содержащего анонимное объединение) будут неявно определены как удаленные. Попытка создать или скопировать объединение (или класс, содержащий анонимное объединение), не объявляя их явно, будет являться ошибкой. В результате будет выдана ошибка компилятора C2280.  
  
    ```Output  
    error C2280: 'B::B(const B &)': attempting to reference a deleted function  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    struct A  
    {  
      volatile int i;  
      volatile int j;  
    };  
  
    extern A* pa;  
  
    struct B  
    {  
      union  
      {  
        A a;  
        int i;  
      };  
    };  
  
    B b1 {*pa};  
    B b2 (b1);  // error C2280  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    struct A  
    {  
      int i;int j;  
    };  
  
    extern volatile A* pa;  
  
    A getA()  // returns an A instance copied from contents of pa  
    {  
      A a;  
      a.i = pa->i;  
      a.j = pa->j;  
      return a;  
    }  
  
    struct B;  // as above  
  
    B b1 {GetA()};  
    B b2 (b1);  // error C2280  
    ```  
  
-   **Статические функции-члены не поддерживают CV-квалификаторы.**  
  
     В предыдущих версиях Visual C++ 2015 допускалось наличие CV-квалификаторов у статических функций-членов. Это поведение связано с регрессией в Visual C++ 2015 и Visual C++ 2015 с обновлением 1. В Visual C++ 2013 и более ранних версиях Visual C++ код, написанный таким образом, отклонялся. Такое поведение Visual C++ 2015 и Visual C++ 2015 с обновлением 1 является неправильным и не соответствует стандарту C++.  Среда Visual Studio 2015 с обновлением 2 отклоняет код, написанный таким образом, и выдает вместо этого ошибку компилятора C2511.  
  
    ```Output  
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'  
    ```  
  
     Пример (раньше)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() const {}  // C2511  
  
    ```  
  
     Пример (теперь)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() {}  // removed const  
  
    ```  
  
-   **Опережающее объявление перечисления недопустимо в коде WinRT** (влияет только на параметр /ZW)  
  
     Код, скомпилированный для среды выполнения Windows (WinRT), не допускает опережающего объявления типов `enum`. Это аналогично случаю, когда управляемый код C++ компилируется для платформы .Net Framework с помощью параметра компилятора /clr. Таким образом гарантируется, что размер перечисления всегда известен и может быть правильно спрогнозирован для системы типов WinRT. Компилятор отклоняет код, написанный таким образом, и выдает ошибку компилятора C2599, а также ошибку компилятора C3197.  
  
    ```Output  
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed  
    ```  
  
    ```Output  
    error C3197: 'public': can only be used in definitions  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    namespace A {  
      public enum class CustomEnum: int32;  // forward declaration; error C2599, error C3197  
    }  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
              // forward declaration of CustomEnum removed  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
-   **Встроенное объявление перегруженных операторов new и delete, не являющихся членами, невозможно** (уровень 1 (/W1) включен по умолчанию)  
  
     При встроенном объявлении функций с операторами new и delete, не являющимися членами, в предыдущих версиях компилятора не выводилось предупреждение. Код, написанный таким образом, является неверно сформированным (диагностика не требуется) и может приводить к проблемам с памятью, которые возникают в результате несоответствия операторов new и delete (особенно при совместном использовании в размерных функциях удаления) и которые может быть трудно диагностировать.   Для выявления кода, написанного таким образом, компилятор теперь выдает предупреждение C4595.  
  
    ```Output  
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
              inline void* operator new(size_t sz)  // warning C4595  
    {  
      ...  
    }  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
              void* operator new(size_t sz)  // removed inline  
    {  
      ...  
    }  
    ```  
  
     Для исправления кода, написанного таким образом, может потребоваться перенести определения операторов из файла заголовка в соответствующий исходный файл.  
  
##  <a name="VS_Update3"></a> Улучшения соответствия в обновлении 3  
  
-   **std::is_convertable теперь обнаруживает присваивания самому себе** (стандартная библиотека)  
  
     Предыдущие версии признака типа `std::is_convertable` некорректно обнаруживали присваивание типа класса самому себе, когда конструктор копии удален или является закрытым. Теперь для `std::is_convertable<>::value` правильно задано `false` при применении к типу класса с удаленным или закрытым конструктором копии.  
  
     Диагностические данные компилятора, связанные с этим изменением, отсутствуют.  
  
     Пример  
  
    ```cpp  
    #include <type_traits>  
  
    class X1  
    {  
    public:  
        X1(const X1&) = delete;  
    };  
  
    class X2  
    {  
    private:  
        X2(const X2&);  
    };  
  
    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");  
    ```  
  
     В предыдущих версиях Visual C++ статические утверждения в нижней части этого примера выполнялись, так как для `std::is_convertable<>::value` было неправильно задано `true`. Теперь `std::is_convertable<>::value` правильно задано `false`, что приводит к ошибкам статических утверждений.  
  
-   **Заданные по умолчанию или удаленные упрощенные конструкторы копии и перемещения поддерживают описатели доступа**  
  
     Предыдущие версии компилятора не проверяли описатель доступа заданных по умолчанию или удаленных упрощенных конструкторов копии и перемещения перед предоставлением им возможности получать вызовы. Это поведение было неправильным и не соответствовало стандарту языка C++. В некоторых случаях это создавало риск формирования некорректного кода и непредсказуемого поведения во время выполнения. Теперь компилятор проверяет описатель доступа заданных по умолчанию или удаленных упрощенных конструкторов копии и перемещения, чтобы определить, могут ли они быть вызваны, и если нет, выдает предупреждение компилятора C2248.  
  
    ```Output  
    error C2248: 'S::S' cannot access private member declared in class 'S'  
    ```  
  
     Пример (раньше)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(S);  // pass S by value  
  
    int main()  
    {  
        S s;  
        f(s);  // error C2248, can't invoke private copy constructor  
    }  
    ```  
  
     Пример (теперь)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(const S&);  // pass S by reference  
  
    int main()  
    {  
        S s;  
        f(s);  
    }  
    ```  
  
-   **Недопустимость поддержки атрибутивного кода ATL** (уровень 1 (/ W1) включен по умолчанию)  
  
     Предыдущие версии компилятора поддерживали атрибутивный код ATL. На следующем этапе процесса отмены поддержки атрибутивного кода ATL, который [начался в Visual C++ 2008](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx), атрибутивный код ATL выведен из эксплуатации. Для выявления такого нерекомендуемого кода компилятор теперь выдает предупреждение C4467.  
  
    ```Output  
    warning C4467: Usage of ATL attributes is deprecated  
    ```  
  
     Если вы хотите продолжить использование атрибутивного кода ATL вплоть до отмены поддержки в компиляторе, это предупреждение можно отключить, передав аргументы командной строки `/Wv:18` или `/wd4467` в компилятор или добавив `#pragma warning(disable:4467)` в исходный код.  
  
     Пример 1 (раньше)  
  
    ```cpp  
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]  
    class A {};  
    ```  
  
     Пример 1 в текущей версии  
  
    ```cpp  
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};  
  
    ```  
  
     Иногда может потребоваться создать IDL-файл, чтобы избежать использования нерекомендуемых атрибутов ATL, как показано в следующем примере кода.  
  
     Пример 2 (раньше)  
  
    ```cpp  
    [emitidl];  
    [module(name="Foo")];  
  
    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
    __interface ICustom {  
        HRESULT Custom([in] long l, [out, retval] long *pLong);  
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);  
    };  
  
    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
    class CFoo : public ICustom  
    {  
        // ...  
    };  
    ```  
  
     Сначала создайте *.idl-файл. Созданный файл vc140.idl можно использовать для получения файла \*.idl, содержащий интерфейсы и заметки.  
  
     Затем добавьте в сборку шаг MIDL, чтобы убедиться в создании определений интерфейса C++.  
  
     Пример 2. IDL (теперь)  
  
    ```cpp  
    import "docobj.idl";  
  
    [  
        object,local,uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)  
    ]  
  
    interface ICustom : IUnknown {  
        HRESULT  Custom([in] long l, [out,retval] long *pLong);  
        [local] HRESULT  CustomLocal([in] long l, [out,retval] long *pLong);  
    };  
  
    [ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]  
    library Foo  
    {  
        importlib("stdole2.tlb");  
        importlib("olepro32.dll");  
            [  
                version(1.0),  
                appobject,uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)  
            ]  
  
        coclass CFoo {  
            interface ICustom;  
        };  
    }  
    ```  
  
     Затем используйте ATL непосредственно в файле реализации, как показано в следующем примере кода.  
  
     Пример 2. Реализация (теперь)  
  
    ```cpp  
    #include <idl.header.h>  
    #include <atlbase.h>  
  
    class ATL_NO_VTABLE CFooImpl :  
        public ICustom,  
        public ATL::CComObjectRootEx<CComMultiThreadModel>  
    {  
    public:  
        BEGIN_COM_MAP(CFooImpl)  
        COM_INTERFACE_ENTRY(ICustom)  
        END_COM_MAP()  
    };  
    ```  
  
-   **Файлы предкомпилированных заголовков (PCH) и несовпадающие директивы #include** (влияет только на /WX/Wall)  
  
     Предыдущие версии компилятора принимали несовпадающие директивы `#include` в файлах исходного кода между компиляциями `-Yc` и `-Yu` при использовании файлов предкомпилированных заголовков (PCH). Компилятор больше не принимает код, написанный таким образом.   Теперь для выявления несовпадающих директив `#include` при использовании PCH-файлов компилятор выдает предупреждение CC4598.  
  
    ```Output  
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position  
    ```  
  
     Пример (раньше)  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"  
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "b.h"  
    #include "a.h"  // mismatched order relative to X.cpp  
    #include "c.h"  
    ```  
  
     Пример (теперь)  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"   
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h" // matched order relative to X.cpp  
    #include "c.h"  
    ```  
  
-   **Файлы предкомпилированных заголовков (PCH) и несовпадающие каталоги включаемых файлов** (влияет только на /Wall /WX)  
  
     Предыдущие версии компилятора принимали аргументы командной строки несовпадающего каталога включаемых файлов (`-I`) в компиляторе между компиляциями `-Yc` и `-Yu` при использовании файлов предкомпилированных заголовков (PCH). Компилятор больше не принимает код, написанный таким образом.   Теперь для выявления аргументов командной строки несовпадающего каталога включаемых файлов (`-I`) при использовании PCH-файлов компилятор выдает предупреждение CC4599.  
  
    ```Output  
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position  
    ```  
  
     Пример (раньше)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h Z.cpp  
    ```  
  
     Пример (теперь)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h -I.. Z.cpp  
    ```