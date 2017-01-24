---
title: "Ошибка компилятора C2042 | Microsoft Docs"
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
  - "C2042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2042"
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

зарезервированные слова signed и unsigned являются взаимоисключающими  
  
 Ключевые слова `signed` и `unsigned` используются в одном объявлении.  
  
 Следующий пример приводит к возникновению ошибки C2042:  
  
```  
// C2042.cpp unsigned signed int i;   // C2042  
```  
  
 Возможное решение  
  
```  
// C2042b.cpp // compile with: /c unsigned int i; signed int ii;  
```