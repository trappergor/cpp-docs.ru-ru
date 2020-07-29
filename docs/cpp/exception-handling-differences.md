---
title: Обработка структурированных исключений в C++
description: Обработка структурированных исключений с помощью модели обработки исключений C++.
ms.date: 09/19/2019
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 0f92bbe64db028ec6a7fd6ae2cc217c707d3e2c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221592"
---
# <a name="handle-structured-exceptions-in-c"></a>Обработка структурированных исключений в C++

Основное различие между обработкой исключений C (SEH) и C++ заключается в том, что модель обработки исключений C++ работает в типах, а модель обработки структурированных исключений C работает с исключениями одного типа. в частности, **`unsigned int`** . То есть, исключения языка C идентифицируются целым числом без знака, тогда как исключения языка C++ идентифицируются типом данных. При возникновении структурированного исключения в C каждый возможный обработчик выполняет фильтр, который проверяет контекст исключения C и определяет, следует ли принимать исключение, передавать его другому обработчику или игнорировать. При возникновении исключения в языке C++ оно может быть любого типа.

Второе отличие заключается в том, что модель обработки структурированных исключений C называется *асинхронной*, поскольку исключения происходят во вторичном потоке управления. Механизм обработки исключений C++ полностью *синхронен*. Это означает, что исключения происходят только при возникновении.

При использовании параметра компилятора [/EHs или/EHsc](../build/reference/eh-exception-handling-model.md) обработчики исключений C++ не обрабатывали структурированные исключения. Эти исключения обрабатываются только **`__except`** структурированными обработчиками исключений или **`__finally`** структурированными обработчиками завершения. Дополнительные сведения см. в разделе [структурированная обработка исключений (C/C++)](structured-exception-handling-c-cpp.md).

В случае с параметром компилятора [/EHa](../build/reference/eh-exception-handling-model.md) , если в программе C++ возникает исключение C, оно может быть обработано структурированным обработчиком исключений со связанным фильтром или **`catch`** обработчиком C++, в зависимости от того, какой из них динамически находится ближе к контексту исключения. Например, этот пример программы C++ вызывает исключение C внутри **`try`** контекста c++:

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>Пример. перехват исключения C в блоке catch C++

```cpp
// exceptions_Exception_Handling_Differences.cpp
// compile with: /EHa
#include <iostream>

using namespace std;
void SEHFunc( void );

int main() {
   try {
      SEHFunc();
   }
   catch( ... ) {
      cout << "Caught a C exception."<< endl;
   }
}

void SEHFunc() {
   __try {
      int x, y = 0;
      x = 5 / y;
   }
   __finally {
      cout << "In finally." << endl;
   }
}
```

```Output
In finally.
Caught a C exception.
```

## <a name="c-exception-wrapper-classes"></a>Классы-оболочки исключений C

В простом примере, как показано выше, исключение C может быть перехвачено только многоточием (**...**) **`catch`** обработке. Обработчику не передается никакая информация о типе или характере исключения. Хотя этот метод работает, в некоторых случаях может потребоваться определить преобразование между двумя моделями обработки исключений, чтобы каждое исключение C было связано с конкретным классом. Для преобразования можно определить класс-оболочку исключения C, который может использоваться или быть производным от, чтобы атрибут определенного типа класса использовался в исключении C. Таким образом, каждое исключение C может обрабатываться отдельно от конкретного **`catch`** обработчика C++, а не из одного обработчика.

Класс-оболочка может иметь интерфейс, состоящий из некоторых функций-членов, которые определяют значение исключения; этот интерфейс может получать расширенные сведения о контексте исключения, предоставляемые моделью исключений языка C. Также может потребоваться определить конструктор по умолчанию и конструктор, принимающий **`unsigned int`** аргумент (для обеспечения базового представления исключения C) и побитовый конструктор копирования. Ниже приведена возможная реализация класса-оболочки исключения C.

```cpp
// exceptions_Exception_Handling_Differences2.cpp
// compile with: /c
class SE_Exception {
private:
   SE_Exception() {}
   SE_Exception( SE_Exception& ) {}
   unsigned int nSE;
public:
   SE_Exception( unsigned int n ) : nSE( n ) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() {
      return nSE;
   }
};
```

Чтобы использовать этот класс, установите пользовательскую функцию преобразования исключений C, которая вызывается внутренним механизмом обработки исключений каждый раз при возникновении исключения C. В функции перевода можно создать любое типизированное исключение (возможно `SE_Exception` , тип или класс, производный от `SE_Exception` ), который может быть перехвачен соответствующим **`catch`** обработчиком C++. Вместо этого функция перевода может возвращать значение, указывающее, что она не обрабатывала исключение. Если функция перевода вызывает исключение C, вызывается метод [Terminate](../c-runtime-library/reference/terminate-crt.md) .

Чтобы указать пользовательскую функцию перевода, вызовите функцию [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) с именем функции перевода в качестве одного аргумента. Функция перевода, которую вы пишете, вызывается один раз для каждого вызова функции в стеке, который имеет **`try`** блоки. Функция перевода по умолчанию отсутствует; Если не указать его путем вызова **_set_se_translator**, исключение C может быть перехвачено только **`catch`** обработчиком многоточия.

## <a name="example---use-a-custom-translation-function"></a>Пример. Использование пользовательской функции перевода

Например, следующий код устанавливает пользовательскую функцию преобразования, а затем создает исключение языка C, которое находится в оболочке класса `SE_Exception`:

```cpp
// exceptions_Exception_Handling_Differences3.cpp
// compile with: /EHa
#include <stdio.h>
#include <eh.h>
#include <windows.h>

class SE_Exception {
private:
   SE_Exception() {}
   unsigned int nSE;
public:
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}
   SE_Exception(unsigned int n) : nSE(n) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() { return nSE; }
};

void SEFunc() {
    __try {
        int x, y = 0;
        x = 5 / y;
    }
    __finally {
        printf_s( "In finally\n" );
    }
}

void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {
    printf_s( "In trans_func.\n" );
    throw SE_Exception( u );
}

int main() {
    _set_se_translator( trans_func );
    try {
        SEFunc();
    }
    catch( SE_Exception e ) {
        printf_s( "Caught a __try exception with SE_Exception.\n" );
        printf_s( "nSE = 0x%x\n", e.getSeNumber() );
    }
}
```

```Output
In trans_func.
In finally
Caught a __try exception with SE_Exception.
nSE = 0xc0000094
```

## <a name="see-also"></a>См. также раздел

[Сочетание исключений C (структурированные) и C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)
