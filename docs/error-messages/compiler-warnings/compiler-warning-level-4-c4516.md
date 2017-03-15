---
title: "Предупреждение компилятора (уровень 4) C4516 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4516"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4516"
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4516
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс::символ": объявления доступа устарели; рекомендуется использовать объявления использования членов  
  
 Объявления доступа, которые используются для изменения доступа к членам производного класса без ключевого слова [using](../../cpp/using-declaration.md), определены комитетом ANSI по стандартизации C\+\+ как устаревшие.  Объявления доступа могут не поддерживаться в последующих версиях C\+\+.  
  
 Следующий пример приводит к возникновению ошибки C4516:  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```