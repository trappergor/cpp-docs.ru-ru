---
title: "Ошибка компилятора C3230 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3230"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3230"
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3230
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": аргумент типа шаблона для "шаблон" не может содержать параметр универсального типа: "параметр"  
  
 Экземпляры шаблонов создаются во время компиляции, но экземпляры универсальных объектов создаются во время выполнения. Следовательно, невозможно создать универсальный код, который может вызывать шаблон, поскольку экземпляр шаблона не создается во время выполнения, когда универсальный тип становится известен.  
  
 В следующем примере возникает ошибка C3230:  
  
```  
// C3230.cpp // compile with: /clr /LD template <class S> void f(S t); generic <class U> ref class C { void f1(U x) { f(x);   // C3230 } };  
```