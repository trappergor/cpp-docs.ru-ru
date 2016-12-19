---
title: "Ошибка компилятора C2027 | Microsoft Docs"
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
  - "C2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2027"
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использование неопределенного типа "тип"  
  
 Тип может использоваться только после того, как он будет определен.  Чтобы устранить эту ошибку, убедитесь, что перед обращением к типу он полностью определен.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2027.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## Пример  
 Существует возможность объявления указателя на объявленный, но неопределенный тип.  Однако в Visual C\+\+ не допускаются ссылки на неопределенный тип.  
  
 Следующий пример приводит к возникновению ошибки C2027.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```