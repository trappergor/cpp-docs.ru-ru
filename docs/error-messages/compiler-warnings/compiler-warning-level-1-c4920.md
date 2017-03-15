---
title: "Предупреждение компилятора (уровень 1) C4920 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4920"
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4920
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

enum enum member member\=value уже включен в перечисление enum как member\=value  
  
 Если TLB\-файл, который передается в директиву \#import, имеет один знак, определенный как минимум в двух перечислениях, это предупреждение указывает, что последующие идентичные знаки игнорируются и будут переведены в комментарии в TLH\-файле.  
  
 Предположим, TLB\-файл имеет следующее содержимое:  
  
```  
library MyLib { typedef enum { enumMember = 512 } AProblem; typedef enum { enumMember = 1024 } BProblem; };  
```  
  
 В следующих примерах возникнет предупреждение C4920:  
  
```  
// C4920.cpp // compile with: /W1 #import "t4920.tlb"   // C4920 int main() { }  
```