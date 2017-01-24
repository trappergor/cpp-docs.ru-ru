---
title: "Ошибка компилятора C2970 | Microsoft Docs"
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
  - "C2970"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2970"
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2970
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"class" : параметр шаблона "param" : "arg" : выражение, которое включает объекты с внутренней компоновкой не может использоваться как аргумент, не являющийся типом  
  
 Нельзя использовать имя или адрес статической переменной в качестве аргумента шаблона.  Класс шаблона ожидает константу, которая может быть определена во время компиляции.  
  
 Следующий пример приводит к возникновению ошибки C2970:  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```