---
title: "Ошибка компилятора C3771 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3771"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3771"
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Ошибка компилятора C3771
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": в ближайшей области пространства имен не удалось найти дружественное объявление  
  
 Объявление шаблона класса для указанного шаблона *идентификатор* не удалось найти в текущем пространстве имен.  
  
### Исправление ошибки  
  
-   Убедитесь, что объявление шаблона класса для идентификатора шаблона задается в текущем пространстве имен или что идентификатор шаблона является полным именем.  
  
## Пример  
 Следующий пример кода объявляет шаблон класса и функцию в пространстве имен `NA`, но пытается объявить шаблон дружественной функции в пространстве имен `NB`.  
  
```  
// C3771.cpp // compile with: /c namespace NA { template<class T> class A { void aFunction(T t) {}; }; } // using namespace NA; namespace NB { class X { template<class T> friend void A<T>::aFunction(T); // C3771 // try the following line instead //      template<class T> friend void NA::A<T>::aFunction(T); // or try "using namespace NA;" instead. }; }  
```  
  
## См. также  
 [Спецификации шаблонов](../Topic/Template%20Specifications.md)