---
title: "Ошибка компилятора C2678 | Microsoft Docs"
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
  - "C2678"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2678"
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2678
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

бинарный operator: не определен оператор, принимающий левый операнд типа type \(или приемлемое преобразование отсутствует\)  
  
 Чтобы использовать этот оператор, необходимо перегрузить его для указанного типа или определить преобразование в тип, для которого определен оператор.  
  
## Пример  
 Ошибка C2678 может возникать, если левый операнд квалифицирован как константный, однако оператор определен для принятия неконстантного аргумента.  
  
 В следующем примере показано возникновение ошибки C2678 и приводятся сведения по ее устранению.  
  
```  
// C2678a.cpp  
// Compile by using: cl /EHsc /W4 C2678a.cpp  
struct Combo {  
   int number;  
   char letter;  
};  
  
inline Combo& operator+=(Combo& lhs, int rhs) {  
   lhs.number += rhs;  
   return lhs;  
}  
  
int main() {  
   Combo const combo1{ 42, 'X' };  
   Combo combo2{ 13, 'Z' };  
  
   combo1 += 6; // C2678  
   combo2 += 9; // OK - operator+= matches non-const Combo  
}  
```  
  
## Пример  
 Ошибка C2678 также может возникать, если не закрепить собственный член до вызова для него функции\-члена.  
  
 В следующем примере показано возникновение ошибки C2678 и приводятся сведения по ее устранению.  
  
```  
// C2678.cpp  
// compile with: /clr /c  
struct S { int _a; };  
  
ref class C {  
public:  
   void M( S param ) {  
      test = param;   // C2678  
  
      // OK  
      pin_ptr<S> ptest = &test;  
      *ptest = param;  
   }  
   S test;  
};  
```  
  
## Пример  
 В следующем примере показано возникновение ошибки C2678 и приводятся сведения по ее устранению.  
  
```  
// C2678_2.cpp  
// compile with: /clr:oldSyntax /c  
struct S { int _a; };  
  
__gc class C {  
public:  
   void M(S param) {  
      test = param;   // C2678  
  
      // OK  
      S __pin* ptest = &test;  
      *ptest = param;  
   }  
  
   S test;  
};  
```