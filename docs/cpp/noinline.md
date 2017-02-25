---
title: "noinline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noinline"
  - "noinline_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], noinline"
  - "noinline __declspec - ключевое слово"
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# noinline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 **\_\_declspec\(noinline\)** указывает компилятору, что определенная функция\-член \(функция в классе\) не может быть встроенной.  
  
 Запрещать использовать функцию как встроенную имеет смысл, если она небольшая и не оказывает критического влияния на производительность кода.  То есть, если функция небольшая и вряд ли будет вызываться часто \(например, функция, которая обрабатывает условие ошибки\).  
  
 Имейте в виду, что если функция отмечена как `noinline`, размер вызывающей функции уменьшается, и она сама становится кандидатом для встраивания компилятором.  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)