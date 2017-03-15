---
title: "Ошибка компилятора C2283 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2283"
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": чистый спецификатор или абстрактный спецификатор переопределения не допускаются в безымянной структуре  
  
 Функция\-член неименованного класса или структуры объявляется с чистым спецификатором, что не допускается.  
  
 В следующем примере возникает ошибка C2283:  
  
```  
// C2283.cpp // compile with: /c struct { virtual void func() = 0;   // C2283 }; struct T { virtual void func() = 0;   // OK };  
```