---
title: "Ошибка компилятора C2903 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2903"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2903"
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2903
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор: символ не является ни шаблоном класса, ни шаблоном функции  
  
 Код пытается явно создать экземпляр объекта, который не является шаблоном.  
  
 В следующем примере возникает ошибка C2903:  
  
```  
// C2903.cpp // compile with: /c namespace N { template<class T> class X {}; class Y {}; } void g() { N::template Y y;   // C2903 N::X<N::Y> y;   // OK }  
```  
  
 Ошибка C2903 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2903b.cpp // compile with: /clr /c namespace N { class Y {}; generic<class T> ref class Z {}; } void f() { N::generic Y y;   // C2903 N:: generic Z<int>^ z;   // OK }  
```