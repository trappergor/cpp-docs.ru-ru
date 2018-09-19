---
title: Файлы заголовков (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 04/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- header files [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d1e477b04421f7e8920bba47b2eba4e73df34cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028536"
---
# <a name="header-files-c"></a>Файлы заголовков (C++)

Имена элементов программы, такие как переменные, функции, классы и т. д. должна быть объявлена, прежде чем они могут использоваться. Например, нельзя просто написать `x = 42` без предварительного объявления «x».

```cpp
int x; // declaration
x = 42; // use x
```

Объявление сообщает компилятору, является ли является **int**, **двойные**, **функция**, **класс** или некоторые другие вещь.  Кроме того каждое имя должны объявляться (прямо или косвенно) в каждом CPP-файле, в котором он используется. При компиляции программы, каждый CPP-файл компилируется независимо друг от друга в единице компиляции. Компилятор не имеет сведений о имен, которые объявляются в другие единицы компиляции. Это означает, что при определении класса или функции или глобальной переменной, должен предоставить объявление была проблема в каждый дополнительный CPP-файл, который его использует. Каждое объявление от этого должна точно совпадать во всех файлах. Несоответствие небольшая будет привести к ошибкам, или некорректное поведение программ, когда компоновщик пытается объединить все единицы компиляции в одной программе.

Чтобы свести к минимуму вероятность ошибок, C++ была внедрена соглашению об использовании *файлы заголовков* должен содержать объявления. Можно сделать объявления в файле заголовка, а затем #include в каждом CPP-файле или другого файла заголовка требует этого объявления. #Include копию файла заголовка директив операции вставки непосредственно в CPP-файл перед компиляцией.

## <a name="example"></a>Пример

В следующем примере распространенный способ объявления класса, а затем использовать ее в другом файле исходного кода. Мы начнем с файлом заголовка `my_class.h`. Он содержит определение класса, но Обратите внимание, что определение является неполным; функция-член `do_something` не определен:

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

Создайте файл реализации (обычно с CPP или аналогичное расширение). Мы вызовите my_class.cpp файл и предоставьте определение в объявлении члена. Мы добавляем `#include` директив для файла «my_class.h», чтобы иметь объявление my_class вставлены на этом этапе в .cpp файл и мы содержат `<iostream>` для работы на объявление `std::cout`. Обратите внимание, что кавычки используются для файлов заголовков, в том же каталоге, что и исходный файл, а угловые скобки используются для заголовки стандартной библиотеки. Кроме того многие заголовки стандартной библиотеки нет h- или любое другое расширение файла.

В файле реализации при необходимости можно использовать **с помощью** инструкцию, чтобы избежать необходимости квалификации каждого отдельного упоминания «my_class» или «cout» с «N::» или «std::».  Не помещайте **с помощью** инструкций в файлах заголовка!

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

Теперь мы можем использовать `my_class` в другой CPP-файле. Мы #include файл заголовка, чтобы компилятор запрашивает в объявлении. Все потребности компилятора знать, является, my_class является классом, имеющим Общая функция-член вызывается `do_something()`.

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

После завершения компиляции каждый CPP-файл в OBJ-файлов компилятор передачей компоновщик OBJ-файлов. Когда компоновщик объединяет файлы объект находит только одно определение для my_class; он находится в OBJ-файл, созданный для my_class.cpp и его сборка завершилась успешно.

## <a name="include-guards"></a>Защита включения

Как правило, содержат файлы заголовков *включают guard* или `#pragma once` директиву, чтобы убедиться, что они не вставлены несколько раз в одном CPP-файла.

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

## <a name="what-to-put-in-a-header-file"></a>Что следует поместить в файл заголовка

Так как файл заголовка, потенциально могут быть включены в несколько файлов, он не может содержать определения, которые может выдавать несколько определений с тем же именем. Следующее не допускаются или считаются очень нарушением рекомендаций:

- определения встроенных типов в пространстве имен или глобальной области
- невстроенных определениях функций
- определения переменных неконстантной
- Агрегатные определений
- безымянные пространства имен
- Директивы using

Использование **с помощью** директива не обязательно вызывает ошибку, но потенциально может вызвать проблему, так как он переводит пространства имен в область действия в каждом CPP-файле, прямо или косвенно, содержащий этот заголовок.

## <a name="sample-header-file"></a>Пример заголовка файла

В следующем примере показано различные типы объявлений и определений, которые допускаются в файле заголовка:

```cpp
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