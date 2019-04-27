---
title: Обрабатывать структурированные исключения в C++
ms.date: 08/14/2018
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 2c4f1a8c3729e2b4d49a0152425e57717f7e9997
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154416"
---
# <a name="handle-structured-exceptions-in-c"></a>Обрабатывать структурированные исключения в C++

Основное отличие между C структурированной обработки исключений (SEH) и обработка исключений с ++ — что обработки модель основана на типах исключений языка C++, а C модель структурной обработки исключений основана на исключениях одного типа; в частности **unsigned int**. То есть, исключения языка C идентифицируются целым числом без знака, тогда как исключения языка C++ идентифицируются типом данных. При возникновении структурированное исключение на языке C все возможные обработчики используют фильтр, который проверяет контекст исключения языка C и определяет, следует ли принять исключение, передать его другим обработчику или игнорировать его. При возникновении исключения в языке C++ оно может быть любого типа.

Второе отличие заключается в том, что C модель структурной обработки исключений называется *асинхронной*, поскольку исключения возникают в дополнение к обычного потока управления. Механизм обработки исключений C++ является полностью *синхронной*, что означает, что исключения возникают только в момент их создания.

При использовании [/EHs или/EHsc](../build/reference/eh-exception-handling-model.md) параметр компилятора, без исключений дескриптор структурированные обработчики исключений C++. Эти исключения обрабатываются только **__catch** структурированные обработчиков исключений или **__finally** структурированные обработчиков завершения. Сведения см. в разделе [структурированная обработка исключений (C/C++)](structured-exception-handling-c-cpp.md).

В разделе [/EHa](../build/reference/eh-exception-handling-model.md) параметр компилятора, если возникает исключение языка C в программе на языке C++, оно могло быть обработано обработчиком структурированного исключения с его связанный фильтр или обработчиком C++ **catch** обработчик, какое значение динамически ближе всего к контекст исключения. Например, в следующей программе C++ вызывает исключение языка C внутри C++ **попробуйте** контекста:

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>Пример — Catch блок catch исключения языка c. в C++

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

В простом примере, как показано выше, исключение языка C может перехватываться только многоточие (**...** ) **catch** обработчика. Обработчику не передается никакая информация о типе или характере исключения. Хотя этот метод работает, в некоторых случаях может потребоваться определить преобразование между двумя моделями обработки исключений, чтобы каждое исключение языка C связан с определенным классом. Для этого можно определить класс-оболочку исключения языка C, который будет использоваться (или на основе которого будут создаваться производные классы) для назначения определенного типа класса исключению языка C. Таким образом, каждое исключение языка C может обрабатываться отдельно с определенной C++ **catch** обработчик, а не все из них в один обработчик.

Класс-оболочка может иметь интерфейс, состоящий из некоторых функций-членов, которые определяют значение исключения; этот интерфейс может получать расширенные сведения о контексте исключения, предоставляемые моделью исключений языка C. Можно также определить конструктор по умолчанию и конструктор, принимающий **unsigned int** аргумент (для учета базового представления исключений языка C), а также побитовый конструктор копий. Здесь показана возможная реализация класса-оболочки исключений C:

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

Чтобы использовать этот класс, установите пользовательскую функцию преобразования исключений C, которая вызывается внутренним механизмом каждый раз при возникновении исключения языка c. обработки исключением. Внутри функции преобразования, можно вызывать любое типизированное исключение (возможно `SE_Exception` тип или тип класса, производного от `SE_Exception`), может быть перехвачено соответствующего языка C++ **catch** обработчика. Функция преобразования может просто производить возврат — это означает, что она не обработала исключение. Если функция преобразования сама вызывает исключение языка C, [завершить](../c-runtime-library/reference/terminate-crt.md) вызывается.

Чтобы указать пользовательскую функцию преобразования, вызовите [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) функцию с именем функции преобразования в качестве единственного аргумента. Созданная функция преобразования вызывается один раз для каждого вызова функции в стеке, который имеет **попробуйте** блоков. Нет функции преобразования по умолчанию; Если вы не укажете его путем вызова **_set_se_translator**, исключение языка C может перехватываться только многоточие **catch** обработчика.

## <a name="example---use-a-custom-translation-function"></a>Пример использования пользовательскую функцию преобразования

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

## <a name="see-also"></a>См. также

[Сочетание исключений C++ C (структурированные) и](../cpp/mixing-c-structured-and-cpp-exceptions.md)
