---
title: "Ошибка компилятора C2177 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2177"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2177"
ms.assetid: 2a39a880-cddb-4d3e-a572-645a14c4c478
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2177
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком большая константа  
  
 Значение константы слишком велико для типа переменной, которой оно назначено.  
  
 В следующем примере возникает ошибка C2177:  
  
```  
// C2177.cpp int main() { int a=18446744073709551616;   // C2177 int b=18446744073709551615;   // OK }  
```