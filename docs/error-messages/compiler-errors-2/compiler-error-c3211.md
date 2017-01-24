---
title: "Ошибка компилятора C3211 | Microsoft Docs"
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
  - "C3211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3211"
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"явная специализация": явная специализация с синтаксисом частичной специализации; замените на "template \<\>"  
  
 Явная специализация имеет неправильный формат.  
  
 Следующий пример приводит к возникновению ошибки C3211:  
  
```  
// C3211.cpp // compile with: /LD template<class T> struct s; template<class T> // use the following line instead // template<> struct s<int>{};   // C3211  
```