---
title: "Ошибка компилятора C2110 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2110"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2110"
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2110
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\+": невозможно добавить два указателя  
  
 Предпринята попытка добавить два значения указателя с помощью оператора "плюс" \( `+` \).  
  
 Следующий пример приводит к возникновению ошибки C2110:  
  
```  
// C2110.cpp int main() { int a = 0; int *pa; int *pb; a = pa + pb;   // C2110 }  
```