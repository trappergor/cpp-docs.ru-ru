---
title: "Ошибка компилятора C2101 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2101"
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"&" в константе  
  
 Оператор address\-of \(`&`\) должен иметь операнд l\-value.  
  
 В следующем примере возникает ошибка C2101:  
  
```  
// C2101.cpp int main() { char test; test = &'a';   // C2101 test = 'a';   // OK }  
```