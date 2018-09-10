---
title: Спецификации исключений (throw, noexcept) (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-language
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
ms.workload:
- cplusplus
ms.openlocfilehash: 1dfc9c50503fcd277f34e8f5dfc4a630d888eebf
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318282"
---
# <a name="exception-specifications-throw-noexcept-c"></a>Спецификации исключений (throw, noexcept) (C++)

Спецификации исключений являются компонентом языка C++, которые указывают намерения программиста о типах исключений, которые могут распространяться с помощью функции. Можно указать, что функция может или не завершаться возникнет исключение с помощью *спецификация исключений*. Компилятор может использовать эти сведения для оптимизации вызовов функции, и чтобы завершить программу, если непредвиденное исключение экранирует функции. 

До C ++ 17 имеются два вида спецификация исключений. *Noexcept спецификации* появился в C ++ 11. Он определяет, является ли пустой набор возможных исключений, которые можно экранировать функции. *Спецификации динамических исключений*, или `throw(optional_type_list)` спецификации, был нерекомендуемыми в C ++ 11 и удалены в C ++ 17, за исключением `throw()`, который является псевдонимом для `noexcept(true)`. Эта спецификация исключений предназначен для предоставления сводные данные о какие исключения могут вызываться из функции, но на практике его удалось найти может привести к проблемам. Спецификации динамических исключений один, которая оказаться полезным было безусловный `throw()` спецификации. Например, в объявлении функции:

```cpp
void MyFunction(int i) throw();
```
сообщает компилятору, что функция не создает исключений. Однако в **/std: c ++ 14** режиме, это может привести к непредсказуемому поведению, если функция вызывает исключение. Поэтому мы рекомендуем использовать [noexcept](../cpp/noexcept-cpp.md) оператор вместо приведенного выше:

```cpp
void MyFunction(int i) noexcept;
```
В следующей таблице перечислены Microsoft Visual C++ реализации спецификаций исключений:

|Спецификация исключений|Значение|
|-----------------------------|-------------|
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|Функция не вызывает исключений. В [/std: c ++ 14](../build/reference/std-specify-language-standard-version.md) режиме (по умолчанию), `noexcept` и `noexcept(true)` эквивалентны. Когда возникает исключение из функции, которая объявлена `noexcept` или `noexcept(true)`, [std::terminate](../standard-library/exception-functions.md#terminate) вызывается. Когда возникает исключение из функции, объявленные как `throw()` в **/std: c ++ 14** режим, результат является неопределенным поведением. Вызывается без определенной функции. Это приспосабливаемости стандартом C ++ 14, требующий компилятору вызывать [std::unexpected](../standard-library/exception-functions.md#unexpected).  <br/> **Visual Studio 2017 версии 15.5 и более поздние версии**: В **/std: c ++ 17** режиме `noexcept`, `noexcept(true)`, и `throw()` являются эквивалентными. В **/std: c ++ 17** режиме `throw()` является псевдонимом для `noexcept(true)`. В **/std: c ++ 17** режим, когда исключение из функции с любой из этих спецификаций [std::terminate](../standard-library/exception-functions.md#terminate) вызывается как требует стандарт C ++ 17.|
|`noexcept(false)`<br/>`throw(...)`<br/>Нет спецификация|Функция может создавать исключения любого типа.|
|`throw(type)`| (**C ++ 14 и более ранних версий**) функция может создавать исключения типа `type`. Компилятор использует синтаксис, но оно интерпретируется как `noexcept(false)`. В **/std: c ++ 17** режиме компилятор выдает предупреждение C5040.|

Если в приложении используется обработка исключений, должно существовать функции в стеке вызовов, который отмечен как дескрипторы, создала исключения, прежде чем они выйти из внешней области функции `noexcept`, `noexcept(true)`, или `throw()`. Если какие-либо функции вызывается между тот, который вызывает исключение и тот, который обрабатывает исключение задаются как `noexcept`, `noexcept(true)` (или `throw()` в **/std: c ++ 17** режим), программа будет завершена, когда функция noexcept распространяет исключение.

Поведение исключения функции зависит от следующих факторов:

- Который [языковой режим стандартной компиляции](../build/reference/std-specify-language-standard-version.md) имеет значение.
- В какой среде выполняется компиляция функции — в C или C++.

- Который [/EH](../build/reference/eh-exception-handling-model.md) используется параметр компилятора.

- Задана ли явно спецификация исключений.

Явные спецификации исключений не разрешено использовать для функций C. Функция C считается не будет выдавать исключения при **/EHsc**и может вызывать структурированные исключения в разделе **/EHs**, **/EHa**, или **/EHac**.

В следующей таблице перечислены ли функции C++ может вызвать исключение в разделе параметров обработки различных исключение компилятора:

|Функция|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|Функция C++ без спецификации исключений|Да|Да|Да|Да|
|Функция C++ со `noexcept`, `noexcept(true)`, или `throw()` спецификация исключений|Нет|Нет|Да|Да|
|Функция C++ со `noexcept(false)`, `throw(...)`, или `throw(type)` спецификация исключений|Да|Да|Да|Да|

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