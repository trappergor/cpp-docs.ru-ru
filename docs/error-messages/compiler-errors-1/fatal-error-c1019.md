---
title: "Неустранимая ошибка C1019 | Microsoft Docs"
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
  - "C1019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1019"
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

непредвиденный \#else  
  
 Директива `#else` находится за пределами конструкции `#if`, `#ifdef` или `#ifndef`. Используйте `#else` только в одной из этих конструкций.  
  
 При компиляции следующего примера возникнет ошибка C1019:  
  
```  
// C1019.cpp #else   // C1019 #endif int main() {}  
```  
  
 Возможное решение  
  
```  
// C1019b.cpp #if 1 #else #endif int main() {}  
```