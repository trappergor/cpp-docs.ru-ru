---
title: "Ошибка компилятора C2065 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 5a3a0d4389a958f421f23a4dc96a395eaf3e22ab
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2065"></a>Ошибка компилятора C2065
identifier: необъявленный идентификатор  
  
Компилятор не может найти объявление идентификатора. Если идентификатор является переменной, необходимо указать тип переменной в объявлении, прежде чем можно будет использовать. Если идентификатор является имя функции, параметров, которые используются функции необходимо указать в объявлении, прежде чем можно использовать функцию. Если идентификатор является тег для определяемого пользователем типа, например, `class` или `struct`, должен быть объявлен тип тега, прежде чем можно будет использовать. Если идентификатор является псевдонима типа, тип должен объявляться с помощью `using` объявление или `typedef` прежде чем можно будет использовать тип.  
  
Существует несколько возможных причин этой ошибки. Ниже приведены некоторые из наиболее распространенных проблем.
  
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
  
## <a name="example-missing-header-file"></a>Пример: отсутствует файл заголовка  
  
Файл заголовка, который объявляет идентификатор не включены. Убедитесь, что файл, содержащий объявление идентификатор включается в каждый исходный файл, который его использует.  
  
```cpp  
// C2065_header.cpp  
// compile with: cl /EHsc C2065_spell.cpp 

//#include <stdio.h> 
int main() { 
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier 
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined  
} 
```  
  
Возможны ошибки в файлах исходного кода приложения рабочего стола Windows, при определении `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, или `WIN32_EXTRA_LEAN`. Эти макросы препроцессора исключить некоторые файлы заголовков из файлов windows.h и afxv\_w32.h для ускорения компиляции. Искать в файлах windows.h и afxv_w32.h актуального описания того, что исключается.  
  
## <a name="eample-missing-closing-quote"></a>Eample: отсутствует закрывающая кавычка  
  
Эта ошибка может возникать, если отсутствует закрывающая кавычка после строковой константы. Это легко перепутать компилятор. 
  
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
  
## <a name="example-use-an-unscoped-identifier"></a>Пример: использование неограниченного идентификатора  
  
Эта ошибка может возникать, если ваш идентификатор не входит в область должным образом. Например, при стандартной библиотеки C++ функций и операторов не полностью пространством имен, или не перевести в режим `std` пространства имен в текущей области видимости с помощью `using` директив, компилятор не может найти их. Чтобы устранить эту проблему, необходимо либо полностью квалифицировать имена идентификаторов, или укажите пространство имен с `using` директивы.  
  
В этом примере возникает ошибка компиляции, поскольку `cout` и `endl` определены в `std` пространство имен:  
  
```cpp  
// C2065_scope.cpp  
// compile with: cl /EHsc C2065_scope.cpp 
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier 
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead  
    std::cout << "Hello" << std::endl;  
}
```  
  
Идентификаторы, объявленные внутри `class`, `struct`, или `enum class` типов, также должно быть дополнено именем внешней области видимости.
  
## <a name="example-ccli-type-deduction-failure"></a>Пример: C + +/ сбой выведение типа CLI  
  
Эта ошибка может возникать при вызове универсальной функции, если заданный аргумент типа не могут быть выведены параметрам. Дополнительные сведения см. в разделе [универсальные функции (C + +/ CLI)](../../windows/generic-functions-cpp-cli.md).  
  
```cpp  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
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

