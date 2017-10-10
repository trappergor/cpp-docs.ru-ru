---
title: "Неустранимая ошибка C1017 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1017
dev_langs:
- C++
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 478a0a17ef8e0f0e6cb6589798d901837e7aff75
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
  
 Возможное решение:  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 Поскольку `CONSTANT_NAME` оценивает строку и не является целым числом, `#if` директива возникает неустранимая ошибка C1017.  
  
 В других случаях препроцессор оценивает константа undefined как ноль. Это может привести к нежелательным результатам, как показано в следующем примере. `YES`не определен, поэтому оно будет равно нулю. Выражение `#if` `CONSTANT_NAME` имеет значение false и код для использования на `YES` удаляется препроцессором. `NO`является также не задана (ноль), поэтому `#elif` `CONSTANT_NAME==NO` имеет значение true (`0 == 0`), вследствие чего препроцессор оставляет код в `#elif` инструкции — противоречит подобное поведение.  
  
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
