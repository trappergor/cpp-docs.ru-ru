---
title: "Ошибка компилятора C3283 | Microsoft Docs"
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
  - "C3283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3283"
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": интерфейс не может иметь конструктор экземпляров  
  
 [Интерфейс](../../windows/interface-class-cpp-component-extensions.md) CLR не может иметь конструктора экземпляров.  Статический конструктор разрешен.  
  
 При компиляции следующего примера возникнет ошибка C3283:  
  
```  
// C3283.cpp // compile with: /clr interface class I { I();   // C3283 };  
```  
  
 Возможное решение  
  
```  
// C3283b.cpp // compile with: /clr /c interface class I { static I(){} };  
```