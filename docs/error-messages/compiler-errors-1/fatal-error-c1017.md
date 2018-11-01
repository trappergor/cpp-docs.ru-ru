---
title: Неустранимая ошибка C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: e2309b93be65b049c35abf96572e144a0a518007
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614283"
---
# <a name="fatal-error-c1017"></a>Неустранимая ошибка C1017

недопустимое константное выражение целого типа

Выражение в `#if` директива не существует или не принимает значение константы.

Константы, определенные с помощью `#define` должен иметь значения, вычисляемые в целочисленной константой, если они используются в `#if`, `#elif`, или `#else` директива.

Следующий пример приводит к возникновению ошибки C1017:

```
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

Возможное решение

```
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

Так как `CONSTANT_NAME` оценивает в строку и не является целым числом, `#if` директива возникает неустранимая ошибка C1017.

В других случаях препроцессор оценивает константа undefined как ноль. Это может привести к неожиданным результатам, как показано в следующем примере. `YES` не определен, поэтому он приводит к нулю. Выражение `#if` `CONSTANT_NAME` принимает значение false и код, который будет использоваться для `YES` удаляется препроцессором. `NO` является также не задана (ноль), поэтому `#elif` `CONSTANT_NAME==NO` имеет значение true (`0 == 0`), вследствие чего препроцессор оставляет код в `#elif` часть инструкции — противоречит правильности поведения.

```
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

Чтобы увидеть, каким образом компилятор обрабатывает директивы препроцессора, используйте [/P](../../build/reference/p-preprocess-to-a-file.md), [/E](../../build/reference/e-preprocess-to-stdout.md), или [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).