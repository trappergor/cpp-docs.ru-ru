---
title: "ML Nonfatal Error A2133 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2133"
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**значение регистра перезаписанное by ВЫЗЫВАЕТ**  
  
 Регистр был передан в качестве аргумента процедуры, но код, созданный by INVOKE передавать другие аргументы разрушил содержимое регистров.  
  
 ОСЬ AL регистрирует АХ, EAX, DX, DL, DH и EDX может использоваться ассемблером для выполнения преобразования данных.  
  
 Используйте другой регистр.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)