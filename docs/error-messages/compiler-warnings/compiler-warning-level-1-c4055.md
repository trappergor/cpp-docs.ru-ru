---
title: "Предупреждение компилятора (уровень 1) C4055 | Microsoft Docs"
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
  - "C4055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4055"
ms.assetid: f04b13ca-88a7-4f2b-8065-42e73e5ac353
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"преобразование": из указателя данных "тип1" в указатель функции "тип2"  
  
 Указатель данных приведен \(возможно некорректно\) к указателю функции. Это предупреждение уровня 1 при использовании параметра \/Za и предупреждение уровня 4 при использовании параметра \/Ze.  
  
 Следующий пример приводит к возникновению ошибки C4055:  
  
```  
// C4055.c // compile with: /Za /W1 /c typedef int (*PFUNC)(); int *pi; PFUNC f() { return (PFUNC)pi;   // C4055 }  
```  
  
 При использовании параметра \/Ze это предупреждение уровня 4.  
  
```  
// C4055b.c // compile with: /W4 /c typedef int (*PFUNC)(); int *pi; PFUNC f() { return (PFUNC)pi;   // C4055 }  
```