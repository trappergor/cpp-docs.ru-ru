---
title: Неустранимая ошибка C1017 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1017
dev_langs:
- C++
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08433109a959b324621e9c837e67cf529d9f6fdb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1017"></a>Неустранимая ошибка C1017
недопустимое константное выражение целого типа  
  
 Выражение в `#if` директива не существует или не определяется константой.  
  
 Константы, определенные с помощью `#define` должен иметь значения, вычисляемые в целочисленной константой, если они используются в `#if`, `#elif`, или `#else` директивы.  
  
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
  
 Поскольку `CONSTANT_NAME` оценивает строку и не является целым числом, `#if` директива возникает неустранимая ошибка C1017.  
  
 В других случаях препроцессор оценивает константа undefined как ноль. Это может привести к нежелательным результатам, как показано в следующем примере. `YES` не определен, поэтому оно будет равно нулю. Выражение `#if` `CONSTANT_NAME` имеет значение false и код для использования на `YES` удаляется препроцессором. `NO` является также не задана (ноль), поэтому `#elif` `CONSTANT_NAME==NO` имеет значение true (`0 == 0`), вследствие чего препроцессор оставляет код в `#elif` инструкции — противоречит подобное поведение.  
  
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