---
title: "Ошибка компилятора C3642 | Microsoft Docs"
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
  - "C3642"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3642"
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3642
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"return\_type\/args": невозможно вызвать функцию с помощью соглашения о вызове \_\_clrcall из машинного кода  
  
 Функция, помеченная соглашением о вызове [\_\_clrcall](../../cpp/clrcall.md), не может быть вызвана из машинного \(неуправляемого\) кода.  
  
 *return\_type\/args* или имя функции или тип функции `__clrcall` попытке вызова.  Тип используется при вызове через указатель функции.  
  
 Чтобы вызвать управляемую функцию из собственного контекста, можно добавить функцию оболочки, которая вызовет функцию `__clrcall`.  Или можно использовать механизм маршалинга среды CLR; дополнительные сведения см. в разделе [Практическое руководство. Указатели функций маршалирования, использующие PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md).  
  
 Следующий пример приводит к возникновению ошибки C3642:  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```