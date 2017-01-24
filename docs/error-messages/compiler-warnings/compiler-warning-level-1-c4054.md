---
title: "Предупреждение компилятора (уровень&#160;1) C4054 | Microsoft Docs"
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
  - "C4054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4054"
ms.assetid: bdd7f6d5-f6f2-44a7-a013-39f309de7a29
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;1) C4054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"преобразование": из указателя функции "тип1" в указатель данных "тип2"  
  
 Указатель функции приведен \(возможно некорректно\) к указателю данных. Это предупреждение уровня 1 при использовании параметра \/Za и предупреждение уровня 4 при использовании параметра \/Ze.  
  
 В следующем примере возникает ошибка C4054.  
  
```  
// C4054.c // compile with: /W1 /Za /c int (*pfunc)(); int* f() { return (int*)pfunc;   // C4054 }  
```  
  
 При использовании параметра \/Ze это предупреждение уровня 4.  
  
```  
// C4054b.c // compile with: /W4 /c int (*pfunc)(); int* f() { return (int*)pfunc;   // C4054 }  
```