---
title: "Спецификации исключений (throw, noexcept) (C++) | Документы Microsoft"
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cbd45c8afed11f613722ecc7586436ff707042d7
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
# <a name="exception-specifications-throw-noexcept-c"></a>Спецификации исключений (throw, noexcept) (C++)

Спецификации исключений — это функция языка C++, которая показывает намерения программиста типы исключений, которые могут распространяться с помощью функции. Можно указать, функция может или не может закрыть это исключение с помощью *спецификацией исключений*. Компилятор может использовать эти сведения для оптимизации вызовы функции и завершение программы, если произошло непредвиденное исключение экранирует функции. 

До C ++ 17 обнаружены два вида спецификацией исключений. *Noexcept спецификации* впервые появился в C ++ 11. Он указывает, является ли пустым набор возможных исключений, которые могут заключить такую функцию. *Спецификации динамических исключений*, или `throw(optional_type_list)` спецификация, был рекомендуется использовать в C ++ 11 и удалена в C ++ 17, за исключением `throw()`, который является псевдонимом для `noexcept(true)`. Эта спецификация исключений был разработан для обеспечения сводную информацию о какие исключения из функции, но на практике найден становится проблематичным. Спецификации динамических исключений один, которая оказаться полезным был безусловный `throw()` спецификации. Например, объявление функции:

```cpp
void MyFunction(int i) throw();
```
сообщает компилятору, что функция не создает исключений. Однако в **/std: c ++ 14** режиме, это может привести к неопределенному поведению, если функция вызывает исключение. Поэтому мы рекомендуем использовать [noexcept](../cpp/noexcept-cpp.md) оператор вместо приведенному выше:

```cpp
void MyFunction(int i) noexcept;
```
В следующей таблице перечислены Microsoft Visual C++ реализации спецификаций исключений:

|Спецификация исключений|Значение|
|-----------------------------|-------------|
|`noexcept`<br>`noexcept(true)`<br>`throw()`|Функция не вызывает исключений. В [/std: c ++ 14](../build/reference/std-specify-language-standard-version.md) режиме (по умолчанию), `noexcept` и `noexcept(true)` являются эквивалентными. Если создается исключение из функции, которая объявлена `noexcept` или `noexcept(true)`, [std::terminate](../standard-library/exception-functions.md#terminate) вызывается. Если создается исключение из функции, объявленные как `throw()` в **/std: c ++ 14** режим, результатом является неопределенное поведение. Вызывается ни одна из функций. Это расхождения из стандартом C ++ 14, которого требуется вызвать компилятор [std::unexpected](../standard-library/exception-functions.md#unexpected).  <br> **Visual Studio 2017 г 15,5 и более поздних версий**: В **/std: c ++ 17** режиме `noexcept`, `noexcept(true)`, и `throw()` являются эквивалентными. В **/std: c ++ 17** режиме `throw()` является псевдонимом для `noexcept(true)`. В **/std: c ++ 17** режиме, при возникновении исключения из функции, объявленной с любым из этих спецификаций [std::terminate](../standard-library/exception-functions.md#terminate) вызывается согласно требованиям C ++ 17 standard.|
|`noexcept(false)`<br/>`throw(...)`<br/>Нет спецификация|Функция может создавать исключения любого типа.|
|`throw(type)`| (**C ++ 14 и более ранних версий**) функция может создавать исключения типа `type`. Компилятор использует синтаксис, но оно интерпретируется как `noexcept(false)`. В **/std: c ++ 17** режиме компилятор выдает предупреждение C5040.|

Если в приложении используется обработка исключений, должна существовать функции в стеке вызовов, обрабатывает исключение исключения перед их выхода из внешней области функции, помеченной `noexcept`, `noexcept(true)`, или `throw()`. Если все функции, вызываемые между, порождающий исключение и обрабатывающий исключение задаются в виде `noexcept`, `noexcept(true)` (или `throw()` в **/std: c ++ 17** режим), выполнение программы завершается функция noexcept распространяет исключение.

Поведение исключения функции зависит от следующих факторов:

- Который [режим стандартной компиляции языка](../build/reference/std-specify-language-standard-version.md) имеет значение.
- В какой среде выполняется компиляция функции — в C или C++.

- Который [/EH](../build/reference/eh-exception-handling-model.md) используется параметр компилятора.

- Задана ли явно спецификация исключений.

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

 [try, throw и catch инструкции (C++)](../cpp/try-throw-and-catch-statements-cpp.md) [обработки исключений в C++](../cpp/cpp-exception-handling.md)