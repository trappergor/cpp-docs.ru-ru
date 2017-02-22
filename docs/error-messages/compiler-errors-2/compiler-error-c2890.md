---
title: "Ошибка компилятора C2890 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2890"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2890"
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2890
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": ссылочный класс может содержать только один неинтерфейсный базовый класс  
  
 Ссылочный класс может содержать только один базовый класс.  
  
 Следующий пример приводит к возникновению ошибки C2890:  
  
```  
// C2890.cpp  
// compile with: /clr /c  
ref class A {};  
ref class B {};  
ref class C : public A, public B {};   // C2890  
ref class D : public A {};   // OK  
```  
  
 **Управляемые расширения для C\+\+**  
  
 Следующий пример приводит к возникновению ошибки C2890:  
  
```  
// C2890b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class A {};  
__gc class B {};  
  
__gc class C : public A, public B {};   // C2890  
__gc class D : public A {};   // OK  
```