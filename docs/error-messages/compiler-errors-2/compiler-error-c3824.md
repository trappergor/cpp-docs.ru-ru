---
title: "Ошибка компилятора C3824 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3284"
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

член: этот тип не может использоваться в данном контексте \(параметр функции, тип возвращаемого значения или статический член\)  
  
 Закрепляющие указатели не могут быть параметрами функции, возвращаемыми типами или объявляемыми `static`.  
  
 Следующий пример приводит к возникновению ошибки C3824:  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
  
 **Управляемые расширения для C\+\+**  
  
 Локальные указатели, объявленные при помощи ключевого слова `__pin`, не могут быть объявлены `static` и не могут быть внутренними указателями.  
  
 Следующий пример приводит к возникновению ошибки C3824:  
  
```  
// C3824b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc struct A {};  
  
void func() {  
   static A __pin* a;   // C3824  
   A __pin* b;   // OK  
}  
```