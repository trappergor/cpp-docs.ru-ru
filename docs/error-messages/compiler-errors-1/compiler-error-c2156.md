---
title: "Ошибка компилятора C2156 | Microsoft Docs"
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
  - "C2156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2156"
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

директива pragma должна находиться вне функции  
  
 Директива pragma, которая должна быть определена на глобальном уровне \(вне тела функции\), находится внутри функции.  
  
 Следующий пример приводит к возникновению ошибки C2156:  
  
```  
// C2156.cpp #pragma optimize( "l", on )   // OK int main() { #pragma optimize( "l", on )   // C2156 }  
```