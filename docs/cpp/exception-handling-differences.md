---
title: Различия в обработке исключений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dafb3c41bd490e7c123e1aefe9ccaa04a4e6b233
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944520"
---
# <a name="exception-handling-differences"></a>Различия в обработке исключений
Основное отличие между структурной обработкой исключений и обработки исключений C++ — что обработки модель основана на типах исключений языка C++, а C модель структурной обработки исключений основана на исключениях одного типа — в частности,  **unsigned int**. То есть, исключения языка C идентифицируются целым числом без знака, тогда как исключения языка C++ идентифицируются типом данных. При возникновении исключения в языке C все возможные обработчики используют фильтр, который проверяет контекст исключения языка C и определяет, следует ли принять исключение, передать его какому-либо другому обработчику или игнорировать исключение. При возникновении исключения в языке C++ оно может быть любого типа.  
  
 Второе отличие заключается в том, что модель структурной обработки исключений языка C называется "асинхронной", так как исключения возникают в дополнение в обычному управлению ходом выполнения. Механизм обработки исключений языка C++ полностью "синхронный", т. е. исключения возникают только в момент их создания.  
  
 Если возникает исключение языка C в программе на языке C++, оно могло быть обработано обработчиком структурированного исключения с его связанный фильтр или обработчиком C++ **catch** обработчик, какое значение окажется динамически ближе к контекст исключения. Например, в следующей программе C++ вызывает исключение языка C внутри C++ **попробуйте** контекста:  
  
## <a name="example"></a>Пример  
  
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
  
##  <a name="_core_c_exception_wrapper_class"></a> Класс-оболочку исключения C  
 В простом примере, как показано выше, исключение языка C может перехватываться только многоточие (**...** ) **catch** обработчика. Обработчику не передается никакая информация о типе или характере исключения. Хотя этот метод работает, в некоторых случаях может потребоваться определить преобразование между двумя моделями обработки исключений, чтобы каждое исключение языка C было связано с определенным классом. Для этого можно определить класс-оболочку исключения языка C, который будет использоваться (или на основе которого будут создаваться производные классы) для назначения определенного типа класса исключению языка C. Таким образом, каждое исключение языка C может обрабатываться с C++ **catch** обработчик более выборочно, чем в предыдущем примере.  
  
 Класс-оболочка может иметь интерфейс, состоящий из некоторых функций-членов, которые определяют значение исключения; этот интерфейс может получать расширенные сведения о контексте исключения, предоставляемые моделью исключений языка C. Можно также определить конструктор по умолчанию и конструктор, принимающий **unsigned int** аргумент (для учета базового представления исключений языка C), а также побитовый конструктор копий. Ниже показана возможная реализация класса-оболочки исключений языка C++:  
  
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
  
 Чтобы использовать этот класс, требуется установить пользовательскую функцию преобразования исключений языка C, которая вызывается внутренним механизмом обработки исключением при каждом возникновении исключения языка C. Внутри функции преобразования, можно вызывать любое типизированное исключение (возможно `SE_Exception` тип или тип класса, производного от `SE_Exception`), может быть перехвачено соответствующего языка C++ **catch** обработчика. Функция преобразования может просто производить возврат — это означает, что она не обработала исключение. Если функция преобразования сама вызывает исключение языка C, [завершить](../c-runtime-library/reference/terminate-crt.md) вызывается.  
  
 Чтобы указать пользовательскую функцию преобразования, вызовите [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) функцию с именем функции преобразования в качестве единственного аргумента. Созданная функция преобразования вызывается один раз для каждого вызова функции в стеке, который имеет **попробуйте** блоков. Нет функции преобразования по умолчанию; Если вы не укажете его путем вызова `_set_se_translator`, исключение языка C может перехватываться только многоточие **catch** обработчика.  
  
## <a name="example"></a>Пример  
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
 [Сочетание исключений C (структурированные) и C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)