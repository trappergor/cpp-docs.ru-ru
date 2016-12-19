---
title: "Неустранимая ошибка C1022 | Microsoft Docs"
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
  - "C1022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1022"
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

непредвиденный \#endif  
  
 Директива `#if`, `#ifdef` или `#ifndef` не имеет соответствующей директивы `#endif`. Убедитесь, что каждая директива `#if`, `#ifdef` или `#ifndef` имеет соответствующую директиву `#endif`.  
  
 В следующем примере возникает ошибка C1022:  
  
```  
// C1022.cpp #define true 1 #if (true) #else #else    // C1022  
```  
  
 Возможное решение:  
  
```  
// C1022b.cpp // compile with: /c #define true 1 #if (true) #else #endif  
```