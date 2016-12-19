---
title: "alloca | Microsoft Docs"
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
ms.assetid: 2b209335-e3a0-4934-93f0-3b5925d22918
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alloca
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функции [\_alloca](../c-runtime-library/reference/alloca.md) требуется выравнивание по 16\-байтовой границе и использование указателя кадра стека.  
  
 Выделяемый стек должен включать расположенное под ним пространство для параметров функций, вызываемых позднее, как описано в разделе [Выделение памяти в стеке](../build/stack-allocation.md).  
  
## См. также  
 [Использование стека](../build/stack-usage.md)