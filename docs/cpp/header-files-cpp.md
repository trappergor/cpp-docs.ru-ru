---
title: Файлы заголовков (C++) | Документы Microsoft
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b571cd2836e66ebef21898af27cf2a6d7082e0e5
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261070"
---
# <a name="header-files-c"></a>Файлы заголовков (C++)

Прежде чем можно будет использовать, должны быть объявлены имена элементов программы, такие как переменные, функции, классы и т. д. Например, невозможно просто написать `x = 42` без предварительного объявления «x». 

```cpp
int x; // declaration
x = 42; // use x
```

 Объявление сообщает компилятору, является ли является **int**, **двойные**, **функция**, **класса** или некоторые другие вещь.  Кроме того каждое имя должны объявляться (прямо или косвенно) в каждый CPP-файле, в котором он используется. При компиляции программы каждый CPP-файл компилируется в единице компиляции независимо друг от друга. Компилятор не имеет сведений о какие имена объявляются в другие единицы компиляции. Это означает, что, если определить класс или функцию или глобальную переменную, должен предоставить объявление, что в каждый дополнительный CPP-файл, который его использует. Каждое объявление, что необходимо точно совпадать во всех файлах. Несоответствие небольшие вызовет ошибки или непредвиденным последствиям, когда компоновщик пытается объединить всех блоков компиляции в одной программе.

Чтобы свести к минимуму вероятность ошибок, C++ была внедрена соглашению об использовании *файлы заголовка* содержит объявления. Можно сделать объявления в файле заголовка, а затем #include в каждый CPP-файле или другого файла заголовка требует объявления этого. #Include директив копии файла заголовка непосредственно в CPP-файл перед компиляцией. 

## <a name="example"></a>Пример

В примере показан обычный способ объявления класса, а затем использовать его в другом файле исходного кода. Мы начнем с файлом заголовка **my_class.h**. Он содержит определение класса, но Обратите внимание, что определение является неполным; функция-член `do_something` не определен:

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

Создайте файл реализации (обычно с CPP или аналогичные расширения). Мы вызовите my_class.cpp файл и предоставьте определение для объявления члена. Мы добавляем `#include` директив для файла «my_class.h» для вставки объявления my_class на этом этапе в .cpp файла и мы содержат  **\<iostream >** по запросу в объявлении `std::cout`. Обратите внимание, что кавычки используются для файлов заголовков, в том же каталоге, что и исходный файл угловые скобки используются для заголовков стандартной библиотеки. Кроме того многие заголовков стандартной библиотеки нет h- или любое другое расширение файла.

В файле реализации при необходимости можно использовать **с помощью** оператор, чтобы избежать необходимости квалификации каждого упоминание «my_class» или «cout» с «N::» или «std::».  Не следует размещать **с помощью** инструкций в файлах заголовка.

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

Теперь мы можем использовать `my_class` в другой CPP-файле. Мы #include в файле заголовка, чтобы компилятор запрашивает в объявлении. Является всех компилятора необходимо знать, что my_class является классом, имеющим Общая функция-член вызывается `do_something()`.

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

По окончании компиляции каждый CPP-файл в OBJ-файлы компилятора компоновщик передает OBJ-файлов. Когда компоновщик объединяет файлы объектов находит только одно определение для my_class; он находится в OBJ-файле для my_class.cpp и сборка прошла успешно.

## <a name="include-guards"></a>Защита включения

Как правило, имеют файлы заголовков *включают guard* или **#pragma один раз** директиву, чтобы убедиться, что они не вставляются несколько раз в одной CPP-файла. 

my_class.h
#<a name="ifndef-myclassh--include-guard"></a>MY_CLASS_H ifndef: / / include guard
#<a name="define-myclassh"></a>Определение MY_CLASS_H


пространство имен N {класса my_class {открытые: void do_something();};

}

#<a name="endif--myclassh-"></a>ENDIF / * MY_CLASS_H * /

## <a name="what-to-put-in-a-header-file"></a>Что следует поместить в файл заголовка

Поскольку файл заголовка потенциально могут быть включены в несколько файлов, он не может содержать определения, которые может создать несколько определений с тем же именем. Следующие недопустимы или считаются очень плохо рекомендаций:

- определения встроенных типов в пространстве имен или глобальной области
- не являющиеся встроенными определения функций 
- определения переменных неконстантной
- Агрегатные определения
- безымянные пространства имен
- Директивы using

Использование **с помощью** директива будет создавать ошибку, но могут вызвать проблемы, так как он переводит пространства имен в область видимости в каждый CPP-файле, прямо или косвенно, содержащий этот заголовок. 

## <a name="sample-header-file"></a>Пример заголовка файла

Ниже приведен пример различных типов объявлений и определений, которые разрешены в файле заголовка.

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
