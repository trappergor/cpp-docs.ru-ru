---
title: "Ошибка компилятора C2955 | Microsoft Docs"
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
  - "C2955"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2955"
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2955
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

identifier: для использования шаблона класса или универсального псевдонима требуется список аргументов шаблона или универсальный список аргументов  
  
 Шаблон класса или универсальный класс нельзя использовать в качестве идентификатора без списка аргументов шаблона или универсального списка аргументов.  
  
 Подробнее: [Шаблоны классов](../Topic/Class%20Templates.md).  
  
 В следующем примере показано возникновение ошибки C2955 и приводятся сведения по ее устранению.  
  
```  
// C2955.cpp  
// compile with: /c  
template<class T>   
class X {};  
  
X x1;   // C2955  
X<int> x2;   // OK - this is how to fix it.  
```  
  
 Ошибка C2955 также может возникать при попытке определить вне строки функцию, объявленную в шаблоне класса:  
  
```  
// C2955_b.cpp  
// compile with: /c  
template <class T>  
class CT {  
public:  
   void CTFunc();  
   void CTFunc2();  
};  
  
void CT::CTFunc() {}   // C2955  
  
// OK - this is how to fix it  
template <class T>  
void CT<T>::CTFunc2() {}  
  
```  
  
 Ошибка C2955 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2955_c.cpp  
// compile with: /clr  
generic <class T>   
ref struct GC {   
   T t;  
};  
  
int main() {  
   GC^ g;   // C2955  
   GC <int>^ g;  
}  
```