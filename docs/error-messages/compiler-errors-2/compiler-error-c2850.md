---
title: "Ошибка компилятора C2850 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2850"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2850"
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2850
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"конструктор": разрешается использовать только с видимостью на уровне файла; не может находиться во вложенном конструкторе  
  
 Конструкторы, такие как прагмы, могут находиться только в глобальной области.  
  
 Следующий пример приводит к возникновению ошибки C2850:  
  
```  
// C2850.cpp  
// compile with: /c /Yc  
// try the following line instead  
// #pragma hdrstop  
namespace X {  
   #pragma hdrstop   // C2850  
};  
```