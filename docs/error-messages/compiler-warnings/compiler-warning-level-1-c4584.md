---
title: "Предупреждение компилятора (уровень 1) C4584 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4584"
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс\_1": базовый класс "класс\_2" уже является базовым классом "класс\_3"  
  
 Определенный класс наследуется от двух классов, один из которых наследуется от другого.  Примеры.  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 В данном случае появится предупреждение для класса C, так как он наследуется как от класса A, так и от класса B, который в свою очередь наследуется от класса A.  Это предупреждение служит для напоминания о необходимости полностью определять использование членов данного базового класса. В противном случае возникнет ошибка компилятора, вызванная неопределенностью обращения к члену класса.