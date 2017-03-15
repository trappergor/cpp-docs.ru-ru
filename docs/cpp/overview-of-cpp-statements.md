---
title: "Общие сведения об операторах в C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "операторы, C++"
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Общие сведения об операторах в C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Операторы C\+\+ выполняются последовательно, кроме случаев, когда эта последовательность специально изменяется с помощью оператора выражения, оператора выбора, оператора итерации или оператора перехода.  
  
 Операторы могут быть следующих типов:  
  
```  
  
        labeled-statement  
expression-statement  
compound-statement  
selection-statement  
iteration-statement  
jump-statement  
declaration-statement  
try-throw-catch  
```  
  
 В большинстве случаев синтаксис операторов C\+\+ совпадает с синтаксисом языка ANSI C.  Основное различие между этими двумя языками заключается в том, что в языке C объявления допускаются только в начале блока; в языке C\+\+ добавлен *оператор\-объявления*, который эффективно снимает данное ограничение.  Это позволяет вводить переменные в том месте программы, в котором можно вычислить заранее рассчитанное значение инициализации.  
  
 Объявление переменных внутри блоков также обеспечивает точный контроль над областью видимости и временем существования этих переменных.  
  
 В разделах, посвященных операторам, рассматриваются следующие ключевые слова языка C\+\+:  
  
|||||  
|-|-|-|-|  
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[\_\_if\_exists](../cpp/if-exists-statement.md)|[\_\_try](../cpp/structured-exception-handling-c-cpp.md)|  
|[case](../cpp/switch-statement-cpp.md)|[\_\_except](../cpp/structured-exception-handling-c-cpp.md)|[\_\_if\_not\_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|  
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[\_\_leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|  
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../Topic/return%20Statement%20\(C++\).md)||  
|[default](../cpp/switch-statement-cpp.md)|[\_\_finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||  
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||  
  
## См. также  
 [Операторы](../cpp/statements-cpp.md)