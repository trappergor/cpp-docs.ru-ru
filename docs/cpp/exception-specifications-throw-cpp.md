---
title: "Спецификации исключений (throw) (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++], throw() vs. throw(...)
- throw keyword [C++], exception specifications
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e308d95f25b25a99fecde976d8ba6433316f460f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="exception-specifications-throw-noexcept-c"></a>Спецификации исключений (throw, noexcept) (C++)
Спецификации исключений — это функция языка C++, которая показывает намерения программиста типы исключений, которые могут распространяться с помощью функции. Можно указать, функция может или не может закрыть это исключение с помощью *спецификацией исключений*. Компилятор может использовать эти сведения для оптимизации вызовы функции и завершение программы, если произошло непредвиденное исключение экранирует функции. Существует два вида спецификацией исключений. *Noexcept спецификации* новые возможности C ++ 11. Он указывает, является ли пустым набор возможных исключений, которые могут заключить такую функцию. *Спецификации динамических исключений*, или `throw(optional_type_list)` спецификация, рекомендуется использовать в C ++ 11 и поддерживается лишь частично с помощью Visual Studio. Эта спецификация исключений был разработан для обеспечения сводную информацию о какие исключения из функции, но на практике найден становится проблематичным. Спецификации динамических исключений один, которая оказаться полезным был безусловный `throw()` спецификации. Например, объявление функции:  
  
```cpp  
void MyFunction(int i) throw();  
```  
  
 сообщает компилятору, что функция не создает исключений. Это эквивалентно использованию [__declspec(nothrow)](../cpp/nothrow-cpp.md). Его использование не является обязательным.  
  
В C ++ 11 стандарте ISO [noexcept](../cpp/noexcept-cpp.md) оператор был введен в качестве замены. Он поддерживается в Visual Studio 2015 и более поздних версий. По возможности используйте `noexcept` выражение, чтобы указать, может ли функция вызывать исключения. Например это объявление функции можно используйте вместо приведенному выше:  
  
```cpp  
void MyFunction(int i) noexcept;  
```  
  
Хотя Visual C++ полностью поддерживает `noexcept` выражения, оно не соответствует стандарту ISO C++ в своей реализации спецификации динамических исключений.  В следующей таблице представлены сводные сведения о реализации спецификаций исключений в Visual C++.  
  
|Спецификация исключений|Значение|  
|-----------------------------|-------------|  
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|Функция не вызывает исключений. Тем не менее если создается исключение из функции, помеченной `throw()`, вызывает компилятор Visual C++ `std::terminate`, а не `std::unexpected`. В разделе [std::unexpected](../c-runtime-library/reference/unexpected-crt.md) для получения дополнительной информации. Если функция помечена `noexcept`, `noexcept(true)`, или `throw()`, компилятор Visual C++ предполагает, что функция не создает исключений C++ и формирует код соответствующим образом. Из-за оптимизации кода может выполнять компилятор C++, исходя из предположения, что функция не вызывает никаких исключений C++, если функция вызывает исключение, программа может работать неправильно.|  
|`noexcept(false)`<br/>`throw(...)`<br/>Нет спецификация|Функция может создавать исключения любого типа.|  
|`throw(type)`|Функция может создавать исключения типа `type`. В Visual C++, принимается следующий синтаксис, но он интерпретируется как `noexcept(false)`.|  
  
 Если в приложении используется обработка исключений, должна существовать функции в стеке вызовов, обрабатывает исключение исключения перед их выхода из внешней области функции, помеченной `noexcept`, `noexcept(true)`, или `throw()`. Если все функции, вызываемые между, порождающий исключение и обрабатывающий исключение задаются в виде `noexcept`, `noexcept(true)`, или `throw()`, выполнение программы завершается, когда функция noexcept распространяет исключение.  
  
 Поведение исключения функции зависит от следующих факторов:  
  
-   В какой среде выполняется компиляция функции — в C или C++.  
  
-   Который [/EH](../build/reference/eh-exception-handling-model.md) используется параметр компилятора.  
  
-   Задана ли явно спецификация исключений.  
  
 Явные спецификации исключений не разрешено использовать для функций C. Функция C считается не будет выдавать исключения при **/EHsc**и может вызвать исключение структурированные исключения в разделе **/EHs**, **/EHa**, или **/EHac**.  
  
 В следующей таблице перечислены ли функции C++ потенциально может вызвать исключение в группе параметров обработки различных исключение компилятора:  
  
|Функция|/EHsc|/EHs|/EHa|/EHac|  
|--------------|------------|-----------|-----------|------------|  
|Функция C++ без спецификации исключений|Да|Да|Да|Да|  
|Функция C++ со `noexcept`, `noexcept(true)`, или `throw()` спецификации исключений|Нет|Нет|Да|Да|  
|Функция C++ со `noexcept(false)`, `throw(...)`, или `throw(type)` спецификации исключений|Да|Да|Да|Да|  
  
## <a name="example"></a>Пример  
  
```cpp  
// exception_specification.cpp  
// compile with: /EHs  
#include <stdio.h>  
  
void handler() {  
   printf_s("in handler\n");  
}  
  
void f1(void) throw(int) {  
   printf_s("About to throw 1\n");  
   if (1)  
      throw 1;  
}  
  
void f5(void) throw() {  
   try {  
      f1();  
   }  
   catch(...) {  
      handler();  
    }  
}  
  
// invalid, doesn't handle the int exception thrown from f1()  
// void f3(void) throw() {  
//   f1();  
// }  
  
void __declspec(nothrow) f2(void) {  
   try {  
      f1();  
   }  
   catch(int) {  
      handler();  
    }  
}  
  
// only valid if compiled without /EHc   
// /EHc means assume extern "C" functions don't throw exceptions  
extern "C" void f4(void);  
void f4(void) {  
   f1();  
}  
  
int main() {  
   f2();  
  
   try {  
      f4();  
   }  
   catch(...) {  
      printf_s("Caught exception from f4\n");  
   }  
   f5();  
}  
```  
  
```Output  
About to throw 1  
in handler  
About to throw 1  
Caught exception from f4  
About to throw 1  
in handler  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы try, throw и catch (C++)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [Обработка исключений С++](../cpp/cpp-exception-handling.md)