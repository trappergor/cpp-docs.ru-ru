---
title: "Ошибка компилятора C2804 | Microsoft Docs"
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
  - "C2804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2804"
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

бинарный оператор operator имеет слишком много параметров  
  
 Перегруженная функция\-член бинарного оператора объявлена более чем с одним параметром.  Подразумевается первый операнд функции\-члена бинарного оператора, типом которого является включающий тип оператор.  
  
## Пример  
 В следующем примере показано возникновение ошибки C2804 и приводятся сведения по ее устранению.  
  
```  
// C2804.cpp  
// compile by using: cl /c /W4 C2804.cpp  
class X {  
public:  
   X& operator+= (const X &left, const X &right);   // C2804  
   X& operator+= (const X &right);   // OK - left operand implicitly *this  
};  
  
int main() {  
   X x, y;  
   x += y;   // equivalent to x.operator+=(y)  
}  
```  
  
## Пример  
 В следующем примере показано возникновение ошибки C2804 и приводятся сведения по ее устранению.  
  
```  
// C2804_2.cpp  
// compile with: /clr /c  
ref struct Y {  
   Y^ operator +(Y^ hY, int i);   // C2804  
   static Y^ operator +(Y^ hY, int i);   // OK  
   Y^ operator +(int i);   // OK  
};  
```