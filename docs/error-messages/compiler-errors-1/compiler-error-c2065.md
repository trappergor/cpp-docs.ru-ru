---
title: Ошибка компилятора C2065 | Документы Microsoft
ms.custom: ''
ms.date: 09/01/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e67fcac9593dc4ad11dbff0cc479ac24d624110
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172794"
---
# <a name="compiler-error-c2065"></a>Ошибка компилятора C2065

> "*идентификатор*": необъявленный идентификатор

Компилятор не может найти объявление идентификатора. Существует несколько возможных причин этой ошибки. Наиболее распространенных причин C2065:, идентификатор еще не был объявлен, правильность написания идентификатор, заголовок, где объявлен идентификатора не включены в файл или идентификатор отсутствует квалификатор области, например, `cout` вместо `std::cout`. Дополнительные сведения об объявлениях в C++ см. в разделе [объявления и определения (C++)](../../cpp/declarations-and-definitions-cpp.md).

Ниже приведены некоторые распространенные проблемы и решения более подробно.

## <a name="the-identifier-is-undeclared"></a>Необъявленный идентификатор

Если идентификатор является переменной или имени функции, необходимо объявить ее, прежде чем можно будет использовать. Перед тем как использовать функции в объявлении функции необходимо также включить типы его параметров. Если переменная объявлена с помощью `auto`, компилятор должен уметь определить тип из ее инициализатора.

Если идентификатор является членом класса или структуры или объявлен в пространстве имен, оно должно быть дополнено именем класса или структуры или имя пространства имен при использовании вне области пространства имен, класса или структуры. Кроме того, необходимо перевести пространство имен в область действия `using` директивы, такие как `using namespace std;`, или имя члена должна проводиться в область действия `using` объявления, такие как `using std::string;`. В противном случае — неполное имя считается на необъявленный идентификатор в текущей области.

Если идентификатор является тег для определяемого пользователем типа, например, `class` или `struct`, должен быть объявлен тип тега, прежде чем можно будет использовать. Например, объявление `struct SomeStruct { /*...*/ };` должна существовать до можно объявить переменную `SomeStruct myStruct;` в коде.

Если идентификатор является псевдонима типа, тип должен объявляться с помощью `using` объявление или `typedef` прежде чем можно будет использовать. Например, необходимо объявить `using my_flags = std::ios_base::fmtflags;` перед использованием `my_flags` как псевдоним для `std::ios_base::fmtflags`.

## <a name="example-misspelled-identifier"></a>Пример: неправильно написанное идентификатор

Эта ошибка обычно происходит, когда неправильно указано имя идентификатора или идентификатора используется неверный прописные и строчные буквы. Имя в объявлении точно должно соответствовать имени, которые можно использовать.

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

## <a name="example-use-an-unscoped-identifier"></a>Пример: использование неограниченного идентификатора

Эта ошибка может возникать, если ваш идентификатор не входит в область должным образом. Если вы видите C2065 при использовании `cout`, в данном случае. При стандартной библиотеки C++ функций и операторов не полностью пространством имен, или не перевести в режим `std` пространства имен в текущей области видимости с помощью `using` директив, компилятор не может найти их. Чтобы устранить эту проблему, необходимо либо полностью квалифицировать имена идентификаторов, или укажите пространство имен с `using` директивы.

В этом примере возникает ошибка компиляции, поскольку `cout` и `endl` определены в `std` пространство имен:

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

Идентификаторы, объявленные внутри `class`, `struct`, или `enum class` типы также должно уточняться именем своей внешней области видимости, при использовании вне этой области.

## <a name="example-precompiled-header-isnt-first"></a>Пример: не первый предкомпилированного заголовка

Эта ошибка может возникать, если разместить все директивы препроцессора, таких как #include, #define, или #pragma, прежде чем #include файла предкомпилированного заголовка. Если исходный файл использует файл предкомпилированного заголовка (то есть, в том случае, если он компилируется с помощью **/Yu** параметр компилятора), а затем игнорируются все директивы препроцессора, прежде чем файл предкомпилированного заголовка.

В этом примере возникает ошибка компиляции, поскольку `cout` и `endl` определены в \<iostream > заголовок, который учитывается, так как он включен перед предкомпилированного файла заголовка. Сборку этого примера, создать все три файла, а затем Скомпилируйте файл stdafx.cpp, а затем скомпилировать C2065_pch.cpp.

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

Чтобы устранить эту проблему, добавьте #include \<iostream > в предкомпилированный файл заголовка или переместить его после предкомпилированного файла заголовка включается в файле исходного кода.

## <a name="example-missing-header-file"></a>Пример: отсутствует файл заголовка

Файл заголовка, который объявляет идентификатор не включены. Убедитесь, что файл, содержащий объявление идентификатор включается в каждый исходный файл, который его использует.

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

Другой возможной причиной является использование списка инициализаторов без включения \<initializer_list > заголовок.

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

Возможны ошибки в файлах исходного кода приложения рабочего стола Windows, при определении `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, или `WIN32_EXTRA_LEAN`. Эти макросы препроцессора исключить некоторые файлы заголовков из файлов windows.h и afxv\_w32.h для ускорения компиляции. Искать в файлах windows.h и afxv_w32.h актуального описания того, что исключается.

## <a name="example-missing-closing-quote"></a>Пример: отсутствует закрывающая кавычка

Эта ошибка может возникать, если отсутствует закрывающая кавычка после строковой константы. Это легко перепутать компилятор. Обратите внимание, что отсутствует закрывающая кавычка может быть несколько строк перед тем местом, указанной ошибки. 

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

## <a name="example-use-iterator-outside-for-loop-scope"></a>Пример: использование итератора вне области цикла

Эта ошибка может возникать, если объявить переменную-итератор в `for` цикла, а затем попытайтесь использовать эту переменную итератора вне области `for` цикла. Компилятор позволяет [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) параметр компилятора по умолчанию. В разделе [Поддержка итераторов при отладке](../../standard-library/debug-iterator-support.md) для получения дополнительной информации.

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

Эта ошибка может возникать при ссылке на функцию или переменную, которая находится в условно скомпилированного кода, который не компилируется для текущей конфигурации. Это также может произойти, если при вызове функции в файле заголовка, который в настоящее время не поддерживается в среде построения. Если некоторые переменные или функции доступны только если определен макрос препроцессора, убедитесь, что код, который вызывает эти функции можно скомпилировать, только если определен макрос препроцессора же. Эта проблема легко отслеживать в Интегрированной среде разработки, так как объявление функции будет затенено, если требуется макросы препроцессора не определены для текущей конфигурации построения.

Ниже приведен пример кода, который работает во время построения в отладочной, но не в розничной торговле:

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

## <a name="example-ccli-type-deduction-failure"></a>Пример: C + +/ сбой выведение типа CLI

Эта ошибка может возникать при вызове универсальной функции, если заданный аргумент типа не могут быть выведены параметрам. Дополнительные сведения см. в разделе [универсальные функции (C + +/ CLI)](../../windows/generic-functions-cpp-cli.md).

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

## <a name="example-ccli-attribute-parameters"></a>Пример: C + +/ CLI атрибута параметров

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
