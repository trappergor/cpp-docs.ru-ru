---
title: "Ошибка компилятора C2477 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2477"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2477"
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2477
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член" : статический член данных не может инициализироваться через производный класс  
  
 Неправильная инициализация статического члена данных класса шаблона.  Критические изменения внесены в версии компилятора Visual C\+\+, более ранних, чем Visual Studio .NET 2003, для соответствия стандартам ISO C\+\+.  
  
 Следующий пример приводит к возникновению ошибки C2477:  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```