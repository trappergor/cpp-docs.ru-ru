---
title: "Ошибка компилятора C2885 | Microsoft Docs"
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
  - "C2885"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2885"
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2885
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс::идентификатор": недопустимое объявление using вне области видимости класса  
  
 Недопустимое использование объявления [using](../../cpp/using-declaration.md).  
  
## Пример  
 Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C\+\+ 2005. В текущей версии использование объявления `using` во вложенном типе не допускается. Необходимо явно задавать каждую ссылку на вложенный тип, поместить тип в пространство имен или создать определение типа.  
  
 В следующем примере возникает ошибка C2885.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## Пример  
 Если ключевое слово `using` используется с членом класса, в C\+\+ необходимо определить этот член внутри другого \(производного\) класса.  
  
 В следующем примере возникает ошибка C2885.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```