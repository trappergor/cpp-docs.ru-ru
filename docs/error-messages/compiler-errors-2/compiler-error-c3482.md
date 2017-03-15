---
title: "Ошибка компилятора C3482 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3482"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3482"
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3482
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"this" может быть использован в качестве передаваемого параметра в лямбда\-выражении только с нестатической функцией\-членом  
  
 Нельзя передавать `this` в список передаваемых параметров лямбда\-выражения, объявленного в статическом методе или в глобальной функции.  
  
### Исправление ошибки  
  
-   Преобразуйте включающую функцию в нестатический метод или  
  
-   удалите указатель `this` из списка передаваемых параметров лямбда\-выражения.  
  
## Пример  
 Следующий пример приводит к возникновению предупреждения C3482:  
  
```  
// C3482.cpp // compile with: /c class C { public: static void staticMethod() { [this] {}(); // C3482 } };  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)