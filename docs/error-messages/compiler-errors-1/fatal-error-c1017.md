---
title: Неустранимая ошибка C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: 0feda3bc4c3729d3101be356220aa0124ba85190
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756946"
---
# <a name="fatal-error-c1017"></a>Неустранимая ошибка C1017

недопустимое константное выражение целого типа

Выражение в директиве `#if` не существовало или не вычисляется как константа.

Константы, определенные с помощью `#define`, должны иметь значения, вычисляемые в целочисленную константу, если они используются в директиве `#if`, `#elif`или `#else`.

Следующий пример приводит к возникновению ошибки C1017:

```cpp
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

Возможное решение

```cpp
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

Поскольку `CONSTANT_NAME` вычисляет строку, а не целое число, директива `#if` создает неустранимую ошибку C1017.

В других случаях препроцессор вычисляет неопределенную константу как ноль. Это может привести к непредвиденным результатам, как показано в следующем примере. `YES` не определен, поэтому он равен нулю. Выражение `#if` `CONSTANT_NAME` принимает значение false, а код, используемый в `YES`, удаляется препроцессором. `NO` также является неопределенным (нулем), поэтому `#elif` `CONSTANT_NAME==NO` принимает значение true (`0 == 0`), что приводит к тому, что препроцессор оставляет код в `#elif` части инструкции — точно так же, как и в случае предполагаемого поведения.

```cpp
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

Чтобы точно увидеть, как компилятор обрабатывает директивы препроцессора, используйте [/p](../../build/reference/p-preprocess-to-a-file.md), [/e](../../build/reference/e-preprocess-to-stdout.md)или [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).
