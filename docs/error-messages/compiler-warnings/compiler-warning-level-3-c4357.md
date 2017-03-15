---
title: "Предупреждение компилятора (уровень 3) C4357 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4357"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4357"
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 3) C4357
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

при создании функции "функция" аргумент array в списке формальных аргументов для делегата "del" пропущен  
  
 Атрибут `ParamArray` был проигнорирован, и функция `function` не может вызываться с переменным числом аргументом.  
  
 Следующий пример приводит к возникновению ошибки C4357:  
  
```  
// C4357.cpp  
// compile with: /clr /W3 /c  
using namespace System;  
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357  
  
public delegate void g(int i, array<Object^>^ varargs);   // OK  
```