---
title: "Ошибка компилятора C2801 | Microsoft Docs"
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
  - "C2801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2801"
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operator оператор" должен быть нестатическим членом  
  
 Следующие операторы могут перегружаться только как нестатические члены:  
  
-   Присваивание `=`;  
  
-   Обращение к членам класса `->`;  
  
-   Индексация `[]`;  
  
-   Вызов функции `()`  
  
 Возможные причины возникновения ошибки C2801:  
  
-   Перегруженный оператор не является членом класса, структуры или объединения.  
  
-   Перегруженный оператор объявлен как `static`.  
  
-   Следующий пример приводит к возникновению ошибки C2801:  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```