---
title: "Ошибка компилятора C2943 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2943"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2943"
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2943
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": идентификатор класса типа переопределен как аргумент типа шаблона  
  
 Нельзя вместо символа использовать универсальный класс или класс шаблона как аргумент универсального типа или типа шаблона.  
  
 В следующем примере возникает ошибка C2943:  
  
```  
// C2943.cpp // compile with: /c template<class T> class List {}; template<class List<int> > class MyList;   // C2943 template<class T >  class MyList;  
```