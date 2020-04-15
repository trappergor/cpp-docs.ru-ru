---
title: Заголовок файлов (КЗ)
ms.date: 12/11/2019
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: 4ab6a2b2626cde94f35678bc9ec789b80d493b8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367233"
---
# <a name="header-files-c"></a>Заголовок файлов (КЗ)

Имена элементов программы, таких как переменные, функции, классы и так далее, должны быть объявлены до того, как они могут быть использованы. Например, вы не можете `x = 42` просто написать без предварительного объявления 'x'.

```cpp
int x; // declaration
x = 42; // use x
```

Декларация сообщает компилятору, является ли элемент **int,** **двойным,** **функцией,** **классом** или какой-либо другой вещью.  Кроме того, каждое имя должно быть задекларировано (прямо или косвенно) в каждом файле .cpp, в котором оно используется. При компилировании программы каждый файл .cpp компилируется независимо в единицу компиляции. Компилятор не знает, какие имена заявлены в других единицах компиляции. Это означает, что если вы определяете класс или функцию или глобальную переменную, вы должны предоставить декларацию этой вещи в каждом дополнительном файле .cpp, который использует его. Каждая декларация этой вещи должна быть точно идентична во всех файлах. Небольшая несогласованность приведет к ошибкам или непреднамеренному поведению, когда связующий пытается объединить все единицы компиляции в единую программу.

Чтобы свести к минимуму вероятность ошибок, СЗ принял конвенцию об использовании *файлов заголовков* для содержания деклараций. Вы делаете заявления в файле заголовка, а затем используете директиву #include в каждом файле .cpp или другом файле заголовка, который требует этого заявления. Директива #include вставляет копию файла заголовка непосредственно в файл .cpp перед компиляцией.

> [!NOTE]
> В Visual Studio 2019 функция *модулей* СЗ20 представлена как усовершенствование и возможная замена файлов заголовка. Для получения дополнительной [информации см.](modules-cpp.md)

## <a name="example"></a>Пример

Следующий пример показывает общий способ декларировать класс, а затем использовать его в другом исходном файле. Начнем с файла заголовка, `my_class.h`. Он содержит определение класса, но обратите внимание, что определение является неполным; функция `do_something` участника не определена:

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

Затем создайте файл реализации (обычно с помощью .cpp или аналогичного расширения). Мы вызовем файл my_class.cpp и предоставим определение для декларации участника. Мы добавляем директиву `#include` для файла "my_class.h" для того, чтобы my_class декларацию вставлена на данном этапе в файл .cpp, и мы включаем, `<iostream>` чтобы вытянуть в декларацию для `std::cout`. Обратите внимание, что котировки используются для заголовков в том же каталоге, что и исходный файл, а угловые скобки используются для стандартных заголовков библиотек. Кроме того, многие стандартные заголовки библиотек не имеют .h или любого другого расширения файла.

В файле реализации мы можем использовать **заявление** по желанию, чтобы избежать необходимости квалифицировать каждое упоминание "my_class" или "cout" с "N::" или "std::".  Не **помещайте операторы** с помощью в файлы заголовка!

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

Теперь мы `my_class` можем использовать в другом файле .cpp. Мы #include файл заголовка, чтобы компилятор втягивал в декларацию. Все, что компилятор должен знать, что my_class это `do_something()`класс, который имеет функцию публичного члена называется .

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

После завершения компилятора компиляции каждого файла .cpp в файлы .obj он передает файлы .obj связующего. Когда связующее соединение объединяет файлы объекта, он находит точно одно определение для my_class; он находится в файле .obj, подготовленном для my_class.cpp, и сборка удалась.

## <a name="include-guards"></a>Включить охранников

Как правило, файлы заголовка `#pragma once` *включают охранникили* или директивы, чтобы гарантировать, что они не вставляются несколько раз в один файл .cpp.

```cpp
// my_class.h
#ifndef MY_CLASS_H // include guard
#define MY_CLASS_H

namespace N
{
    class my_class
    {
    public:
        void do_something();
    };
}

#endif /* MY_CLASS_H */
```

## <a name="what-to-put-in-a-header-file"></a>Что положить в файл заголовка

Поскольку файл заголовка потенциально может быть включен несколькими файлами, он не может содержать определения, которые могут привести к нескольким определениям одного и того же имени. Следующие не допускаются, или считаются очень плохой практикой:

- встроенные определения типов в пространстве имен или глобальной области
- не-влиневые определения функций
- неконст переменных определений
- агрегированные определения
- безымянные пространства имен
- Директивы using

Использование **директивы** использования не обязательно вызовет ошибку, но потенциально может вызвать проблему, поскольку оно приводит пространство имен в область в каждый файл .cpp, который прямо или косвенно включает этот заголовок.

## <a name="sample-header-file"></a>Пример файла заголовка

Ниже приводится различные виды деклараций и определений, которые разрешены в файле заголовка:

```cpp
// sample.h
#pragma once
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{
    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };

    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif

    class my_class   // regular class definition,
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;
}
```
