---
title: "Ошибка компилятора C3162 | Microsoft Docs"
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
  - "C3162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3162"
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип" : ссылочный тип, имеющий деструктор, не может использоваться в качестве типа статического члена данных "член"  
  
 Среда CLR не может определить момент для запуска пользовательского деструктора, если класс также содержит статическую функцию\-член.  
  
 Деструктор никогда не будет запущен, если только объект не будет удален явным образом.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Общие вопросы использования Visual C\+\+ для 64\-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3162:  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```