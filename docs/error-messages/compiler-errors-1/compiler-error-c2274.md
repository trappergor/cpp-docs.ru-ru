---
title: "Ошибка компилятора C2274 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2274"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2274"
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2274
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"type": недопустимо в качестве выражения с правой стороны оператора "."  
  
 В качестве правого операнда оператора доступа к членам \(.\) используется тип.  
  
 Эта ошибка может быть вызвана попыткой обращения к преобразованию типа, определенного пользователем.  Используйте ключевое слово `operator` между точкой и типом `type`.  
  
 Следующий пример приводит к возникновению ошибки C2286:  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```