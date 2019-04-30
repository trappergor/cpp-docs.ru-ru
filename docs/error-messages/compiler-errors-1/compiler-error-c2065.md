---
title: Ошибка компилятора C2065
ms.date: 09/01/2017
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: 3daf2cd532cd07225b822c80b46fc28274d4e2a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408619"
---
# <a name="compiler-error-c2065"></a>Ошибка компилятора C2065

> "*идентификатор*": необъявленный идентификатор

Компилятору не удается найти объявление идентификатора. Существует несколько возможных причин этой ошибки. Наиболее распространенные причины C2065, что идентификатор не был объявлен, правильность написания идентификатор, заголовок, где объявлен идентификатор не включен в файле или идентификатор отсутствует квалификатор области, например, `cout` вместо `std::cout`. Дополнительные сведения о объявления в C++, см. в разделе [объявления и определения (C++)](../../cpp/declarations-and-definitions-cpp.md).

Ниже приведены некоторые распространенные проблемы и решения более подробно.

## <a name="the-identifier-is-undeclared"></a>Необъявленный идентификатор

Если идентификатор является переменной или имени функции, необходимо объявить ее, прежде чем можно будет использовать. Прежде чем можно будет использовать функцию объявление функции должно содержать типы его параметров. Если переменная объявлена с помощью `auto`, компилятор должен иметь возможность определить тип из ее инициализатора.

Если идентификатор является членом класса или структуры или объявлен в пространстве имен, оно должно быть дополнено именем класса или структуры или имя пространства имен при использовании вне структуры, класса или пространства имен. Кроме того, необходимо перевести пространство имен в области путем `using` директивы, такие как `using namespace std;`, или имя члена, которые следует включить в область действия `using` объявления, такие как `using std::string;`. В противном случае — неполное имя считается необъявленный идентификатор в текущей области.

Если идентификатор является тег для определяемого пользователем типа, например, `class` или `struct`, должен быть объявлен тип тега, прежде чем можно будет использовать. Например, объявление `struct SomeStruct { /*...*/ };` должен существовать прежде, чем можно объявить переменную `SomeStruct myStruct;` в коде.

Если идентификатор является псевдонимом типа, тип должен объявляться с помощью `using` объявление или `typedef` прежде чем можно будет использовать. Например, необходимо объявить `using my_flags = std::ios_base::fmtflags;` перед использованием `my_flags` как псевдоним для `std::ios_base::fmtflags`.

## <a name="example-misspelled-identifier"></a>Пример: идентификатор с ошибками

Эта ошибка обычно происходит, когда имя идентификатора содержит ошибки, или для идентификатора используется неправильный прописных и строчных букв. Имя в объявлении должен точно соответствовать имени, используемого.

```cpp
// C2065_spell.cpp
// compile with: cl /EHsc C2065_spell.cpp
#include <iostream>
using namespace std;
int main() {
    int someIdentifier = 42;
    cout << "Some Identifier: " << SomeIdentifier << endl;
    // C2065: 'SomeIdentifier': undeclared identifier
    // To fix, correct the spelling:
    // cout << "Some Identifier: " << someIdentifier << endl;
}
```

## <a name="example-use-an-unscoped-identifier"></a>Пример: использование неограниченного идентификатор

Эта ошибка может возникать, если ваш идентификатор не масштабируется должным образом. Если вы видите C2065 при использовании `cout`, это причина. При стандартной библиотеки C++ функций и операторов, не уточняются полностью пространства имен, или не перевести в режим `std` пространства имен в текущей области с помощью `using` директив, компилятор не может найти их. Чтобы устранить эту проблему, необходимо полностью уточнить имена идентификаторов, либо укажите пространство имен с `using` директива.

В этом примере не сможет выполнить компиляцию, поскольку `cout` и `endl` определяются в `std` пространство имен:

```cpp
// C2065_scope.cpp
// compile with: cl /EHsc C2065_scope.cpp
#include <iostream>
// using namespace std;   // Uncomment this line to fix

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead
    std::cout << "Hello" << std::endl;
}
```

Идентификаторы, объявленные внутри элемента `class`, `struct`, или `enum class` типы также должно уточняться именем своей внешней области видимости, при их использовании вне этой области.

## <a name="example-precompiled-header-isnt-first"></a>Пример: не первый предкомпилированного заголовка

Эта ошибка может возникать, если разместить все директивы препроцессора, таких как #include, #define, или #pragma, прежде чем #include файла предкомпилированного заголовка. Если в файле исходного кода использует файл предкомпилированного заголовка (то есть, в том случае, если он компилируется с помощью **/Yu** параметр компилятора) игнорируются все директивы препроцессора, прежде чем файл предкомпилированного заголовка.

В этом примере не сможет выполнить компиляцию, поскольку `cout` и `endl` определяются в \<iostream > заголовок, который учитывается, так как он включен, прежде чем файл предкомпилированного заголовка. Сборки этого примера, создайте все три файла, а затем скомпилировать stdafx.cpp, а затем скомпилировать C2065_pch.cpp.

```cpp
// stdafx.h
#include <stdio.h>
```

```cpp
// stdafx.cpp
// Compile by using: cl /EHsc /W4 /c /Ycstdafx.h stdafx.cpp
#include <stdafx.h>
```

```cpp
// C2065_pch.cpp
// compile with: cl /EHsc /W4 /Yustdafx.h C2065_pch.cpp
#include <iostream>
#include "stdafx.h"
using namespace std;

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
}
```

Чтобы устранить эту проблему, добавьте #include \<iostream > в предварительно скомпилированного заголовочного файла или перемещения его после предкомпилированного файла заголовка включается в файле исходного кода.

## <a name="example-missing-header-file"></a>Пример: отсутствует файл заголовка

Не был включен файл заголовка, который объявляет идентификатор. Убедитесь, что файл, который содержит объявление для идентификатора включен в каждый исходный файл, который его использует.

```cpp
// C2065_header.cpp
// compile with: cl /EHsc C2065_header.cpp

//#include <stdio.h>
int main() {
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined
}
```

Другой причиной является использование списка инициализаторов не включая \<initializer_list > заголовок.

```cpp
// C2065_initializer.cpp
// compile with: cl /EHsc C2065_initializer.cpp

// #include <initializer_list>
int main() {
    for (auto strList : {"hello", "world"})
        if (strList == "hello") // C2065: 'strList': undeclared identifier
            return 1;
    // To fix, uncomment the #include <initializer_list> line
}
```

Эта ошибка в исходных файлах рабочего стола Windows приложения может возникнуть, если определить `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, или `WIN32_EXTRA_LEAN`. Эти макросы препроцессора исключить некоторые файлы заголовков из файлов windows.h и afxv\_w32.h для ускорения компиляции. Искать в файлах windows.h и afxv_w32.h актуального описания того, что исключен.

## <a name="example-missing-closing-quote"></a>Пример: отсутствует закрывающая кавычка

Эта ошибка может возникать, если отсутствует закрывающая кавычка после строковой константы. Это легко перепутать компилятор. Обратите внимание, что отсутствует закрывающая кавычка может быть несколько строк, перед расположением ошибку.

```cpp
// C2065_quote.cpp
// compile with: cl /EHsc C2065_quote.cpp
#include <iostream>

int main() {
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee";
    std::cout << "Name: " << first
        << " " << last << std::endl; // C2065: 'last': undeclared identifier
}
```

## <a name="example-use-iterator-outside-for-loop-scope"></a>Пример: используйте итератора вне области видимости оператора for

Эта ошибка может возникать, если объявить переменную-итератор в `for` цикла, а затем попытайтесь использовать эту переменную итератора вне области `for` цикла. Компилятор включает [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) параметр компилятора по умолчанию. См. в разделе [поддержка отладочных итераторов](../../standard-library/debug-iterator-support.md) Дополнительные сведения.

```cpp
// C2065_iter.cpp
// compile with: cl /EHsc C2065_iter.cpp
#include <iostream>
#include <string>

int main() {
    // char last = '!';
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" };
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
}
```

## <a name="example-preprocessor-removed-declaration"></a>Пример: препроцессора удален объявления

Эта ошибка может возникать при ссылке на функцию или переменную в условно скомпилированного кода, который не компилируется для текущей конфигурации. Это также может произойти, если вы вызываете функцию в файл заголовка, который в настоящее время не поддерживается в среде построения. Если определенные переменные или функции доступен, только когда определен макрос препроцессора, убедитесь, что код, который вызывает эти функции можно скомпилировать, только если определен один и тот же макрос препроцессора. Эта проблема легко отслеживать в интегрированной среде разработки, так как объявление функции будет затенено, если необходимые макросы препроцессора не определены для текущей конфигурации построения.

Ниже приведен пример кода, который работает при построения в режиме отладки, но не розничной торговли:

```cpp
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate);
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```

## <a name="example-ccli-type-deduction-failure"></a>Пример C++Или ошибка определения типа интерфейса командной строки

Эта ошибка может возникать при вызове универсальной функции, если заданный аргумент типа не может быть выведен из параметров, используемых. Дополнительные сведения см. в разделе [универсальные функции (C++выполняет)](../../extensions/generic-functions-cpp-cli.md).

```cpp
// C2065_b.cpp
// compile with: cl /clr C2065_b.cpp
generic <typename ItemType>
void G(int i) {}

int main() {
   // global generic function call
   G<T>(10);     // C2065
   G<int>(10);   // OK - fix with a specific type argument
}
```

## <a name="example-ccli-attribute-parameters"></a>Пример C++Или параметры атрибутов интерфейса командной строки

Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: проверка параметров для атрибутов Visual C++.

```cpp
// C2065_attributes.cpp
// compile with: cl /c /clr C2065_attributes.cpp
[module(DLL, name=MyLibrary)];   // C2065
// try the following line instead
// [module(dll, name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```
