---
title: "Сохраняемые регистры вызываемого и вызывающего объектов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Сохраняемые регистры вызываемого и вызывающего объектов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Регистры RAX, RCX, RDX, R8, R9, R10 и R11 считаются временными и должны уничтожаться при вызове функции \(если иное не требуется, исходя из соображений безопасности, например в процессе оптимизации программы\).  
  
 Регистры RBX, RBP, RDI, RSI, RSP, R12, R13, R14 и R15 считаются защищенными. Значения этих регистров должны сохраняться и восстанавливаться в использующей их функции.  
  
## См. также  
 [Соглашение о вызовах](../build/calling-convention.md)