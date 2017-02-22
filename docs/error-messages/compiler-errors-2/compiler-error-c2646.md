---
title: "Ошибка компилятора C2646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2646"
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

анонимную структуру или объединение в глобальной области видимости или области видимости пространства имен необходимо объявлять как статическое  
  
 У анонимной структуры или объединения глобальная область видимости или область видимости пространства имен, но они не объявлены как `static`.  
  
 В следующем примере показано возникновение ошибки C2646 и приводятся сведения по ее устранению.  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```