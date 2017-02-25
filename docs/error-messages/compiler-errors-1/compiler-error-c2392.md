---
title: "Compiler Error C2392 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2392"
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Compiler Error C2392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

method1: ковариантные возвращаемые типы не поддерживаются в управляемых типах и типах WinRT, в противном случае method2 был бы переопределен  
  
 Ковариантные возвращаемые типы недопустимы для функций\-членов среды выполнения Windows или при компиляции с параметром [\/CLR \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 В следующем примере показано возникновение ошибки C2392 и приводятся сведения по ее устранению.  
  
```  
// C2392.cpp  
// compile with: /clr  
public ref struct B {  
public:  
   int i;  
};  
  
public ref struct D: public B{};  
  
public ref struct B1 {  
public:  
   virtual B^ mf() {  
      B^ pB = gcnew B;  
      pB->i = 11;  
      return pB;  
   }  
};  
  
public ref struct D1: public B1 {  
public:  
   virtual D^ mf() override {  // C2392  
   // try the following line instead  
   // virtual B^ mf() override {  
   // return type D^ is covariant with B^, not allowed with CLR types  
      D^ pD = gcnew D;  
      pD->i = 12;  
      return pD;  
   }  
};  
  
int main() {  
   B1^ pB1 = gcnew D1;  
   B^ pB = pB1->mf();  
   D^ pD = dynamic_cast<D^>(pB);  
}  
```