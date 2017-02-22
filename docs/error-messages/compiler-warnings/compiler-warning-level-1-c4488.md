---
title: "Предупреждение компилятора (уровень 1) C4488 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4488"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4488"
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Предупреждение компилятора (уровень 1) C4488
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": необходимо ключевое слово "ключевое слово" для реализации метода интерфейса "метод интерфейса"  
  
 Класс должен реализовывать все члены интерфейса, от которых он прямо наследует.  Реализованный член должен открыт для общего доступа и помечен как виртуальный.  
  
## Пример  
 Ошибка C4488 может возникнуть в том случае, если реализуемый член не открыт для общего доступа.  Следующий пример демонстрирует причины возникновения ошибки C4488.  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## Пример  
 Ошибка C4488 может возникнуть в том случае, если реализуемый член не помечен как виртуальный.  Следующий пример демонстрирует причины возникновения ошибки C4488.  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```