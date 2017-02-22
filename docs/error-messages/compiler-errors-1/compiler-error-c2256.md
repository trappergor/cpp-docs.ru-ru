---
title: "Ошибка компилятора C2256 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2256"
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимое использование спецификатора friend для "function"  
  
 Ни деструктора, ни конструктора нельзя указывать в качестве [friend](../../cpp/friend-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C2256:  
  
```  
// C2256.cpp  
// compile with: /c  
class C {  
public:  
   friend ~C();   // C2256  
   ~C();   // OK  
};  
```