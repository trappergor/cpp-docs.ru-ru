---
title: Написание фильтра исключений
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: aaf0dc77207399d7c6be86127d7decf03895ced5
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245984"
---
# <a name="writing-an-exception-filter"></a>Написание фильтра исключений

Исключение можно обработать посредством перехода на уровень обработчика исключений или путем продолжения выполнения. Instead of using the exception handler code to handle the exception and falling through, you can use *filter* to clean up the problem and then, by returning -1, resume normal flow without clearing the stack.

> [!NOTE]
>  После некоторых исключений возобновление невозможно. If *filter* evaluates to -1 for such an exception, the system raises a new exception. When you call [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception), you determine whether the exception will continue.

For example, the following code uses a function call in the *filter* expression: this function handles the problem and then returns -1 to resume normal flow of control:

```cpp
// exceptions_Writing_an_Exception_Filter.cpp
#include <windows.h>
int main() {
   int Eval_Exception( int );

   __try {}

   __except ( Eval_Exception( GetExceptionCode( ))) {
      ;
   }

}
void ResetVars( int ) {}
int Eval_Exception ( int n_except ) {
   if ( n_except != STATUS_INTEGER_OVERFLOW &&
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions
   return EXCEPTION_CONTINUE_SEARCH;

   // Execute some code to clean up problem
   ResetVars( 0 );   // initializes data to 0
   return EXCEPTION_CONTINUE_EXECUTION;
}
```

It is a good idea to use a function call in the *filter* expression whenever *filter* needs to do anything complex. Вычисление выражения приводит к выполнению функции, в данном случае — `Eval_Exception`.

Note the use of [GetExceptionCode](/windows/win32/Debug/getexceptioncode) to determine the exception. Эту функцию необходимо вызывать внутри фильтра. `Eval_Exception` cannot call `GetExceptionCode`, but it must have the exception code passed to it.

Если исключение не вызвано переполнением при операции с целыми числами или числами с плавающей запятой, этот обработчик передает управление другому обработчику. В этом случае обработчик вызывает функцию (`ResetVars` — это только пример, а не функция API), чтобы сбросить некоторые глобальные переменные. *Statement-block-2*, which in this example is empty, can never be executed because `Eval_Exception` never returns EXCEPTION_EXECUTE_HANDLER (1).

Вызов функции — хороший способ работы со сложными выражениями фильтров. Удобны также две другие возможности языка C:

- условный оператор;

- оператор "запятая".

Условный оператор часто полезен, поскольку его можно использовать для проверки конкретного кода возврата и последующего возврата одного из двух различных значений. For example, the filter in the following code recognizes the exception only if the exception is STATUS_INTEGER_OVERFLOW:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

Цель условного оператора в этом случае — в основном, обеспечить ясность, так как следующий код дает такие же результаты.

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

The conditional operator is more useful in situations where you might want the filter to evaluate to -1, EXCEPTION_CONTINUE_EXECUTION.

Оператор "запятая" позволяет выполнить несколько независимых операций в одном выражении. Результат, грубо говоря, представляет собой результат выполнения нескольких инструкций с последующим возвратом значения последнего выражения. Например, в следующем коде код исключения сохраняется в переменной и затем проверяется.

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>См. также

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)