---
title: "inline_recursion | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inline_recursion_CPP"
  - "vc-pragma.inline_recursion"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "inline_recursion - прагма"
  - "прагмы, inline_recursion"
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# inline_recursion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Управляет развертыванием встроенного кода непосредственных или взаимных рекурсивных вызовов функций.  
  
## Синтаксис  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## Заметки  
 Используйте эту директиву \#pragma для управления функциями, помеченными как [inline](../misc/inline-inline-forceinline.md) и [\_\_inline](../misc/inline-inline-forceinline.md), или функциями, автоматически развертываемыми компилятором при заданном параметре \/Ob2.  Для использования этой директивы \#pragma необходимо, чтобы параметр [\/Ob](../build/reference/ob-inline-function-expansion.md) компилятора имел значение 1 или 2.  По умолчанию функция `inline_recursion` отключена.  Эта директива \#pragma действует начиная с первого после нее вхождения вызова функции и не влияет на определение функции.  
  
 Директива \#pragma `inline_recursion` управляет развертыванием рекурсивных функций.  Если параметр `inline_recursion` выключен и встроенная функция вызывает саму себя \(прямо или косвенно\), эта функция разворачивается только один раз.  Если параметр `inline_recursion` включен, функция разворачивается несколько раз, пока не будет достигнуто одно из следующих значений: значение, установленное с помощью директивы \#pragma [inline\_depth](../preprocessor/inline-depth.md), значение по умолчанию для рекурсивных функций, определяемое директивой \#pragma `inline_depth`, или значение, ограничиваемое ресурсами.  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_depth](../preprocessor/inline-depth.md)   
 [Параметр \/Ob \(расширение встроенных функций\)](../build/reference/ob-inline-function-expansion.md)