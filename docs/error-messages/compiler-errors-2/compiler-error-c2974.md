---
title: "Ошибка компилятора C2974 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2974"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2974"
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2974
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимый аргумент типа "number"; ожидается тип  
  
 Универсальный аргумент или аргумент шаблона не совпадает с универсальной декларацией или декларацией шаблона.  Тип должен появиться в угловых скобках.  Проверьте универсальное определение или определение шаблона, чтобы найти правильные типы.  
  
 Следующий пример приводит к возникновению ошибки C2974:  
  
```  
// C2974.cpp  
// C2974 expected  
template <class T>  
struct TC {};  
  
template <typename T>  
void tf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   TC<1>* tc;  
   tf<"abc">("abc");  
  
   TC<int>* tc;  
   tf<const char *>("abc");  
}  
```  
  
 Ошибка C2974 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2974b.cpp  
// compile with: /clr  
// C2974 expected  
using namespace System;  
generic <class T>  
ref struct GCtype {};  
  
generic <typename T>  
void gf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   GCtype<"a">^ gc;  
   gf<"a">("abc");  
  
   // OK  
   GCtype<int>^ gc;  
   gf<String ^>("abc");  
}  
```