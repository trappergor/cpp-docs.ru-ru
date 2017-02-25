---
title: "Ошибка компилятора C3772 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3772"
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Ошибка компилятора C3772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя": недопустимое объявление дружественного шаблона  
  
 Не допускается объявлять дружественный элемент для специализации шаблона класса. Вы не можете объявить в одном операторе явную или частичную специализацию шаблона класса и дружественный элемент для этой специализации.*Имя* идентифицирует недопустимое объявление.  
  
### Исправление ошибки  
  
-   Не объявляйте дружественный элемент для специализации шаблона класса.  
  
-   Если это нужно в вашем приложении, объявите дружественный элемент для шаблона класса либо для конкретной частичной или явной специализации.  
  
## Пример  
 В следующем примере кода произойдет ошибка компиляции из\-за объявления дружественного элемента для частичной специализации шаблона класса.  
  
```  
// c3772.cpp // compile with: /c // A class template. template<class T> class A {}; // A partial specialization of the class template. template<class T> class A<T*> {}; // An explicit specialization. template<> class A<char>; class X { // Invalid declaration of a friend of a partial specialization. template<class T> friend class A<T*>; // C3772 // Instead, if it is appropriate for your application, declare a // friend of the class template. Consequently, all specializations // of the class template are friends: //    template<class T> friend class A; // Or declare a friend of a particular partial specialization: //    friend class A<int*>; // Or declare a friend of a particular explicit specialization: //    friend class A<char>; };  
```  
  
## См. также  
 [Спецификации шаблонов](../Topic/Template%20Specifications.md)   
 [Частичная специализация шаблонов класса](../../cpp/template-specialization-cpp.md)   
 [Явная специализация шаблонов класса](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)