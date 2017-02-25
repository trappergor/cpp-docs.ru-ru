---
title: "_CRTDBG_MAP_ALLOC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRTDBG_MAP_ALLOC"
  - "_CRTDBG_MAP_ALLOC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Макрос _CRTDBG_MAP_ALLOC"
  - "выделение памяти, в отладочных сборках"
  - "Макрос CRTDBG_MAP_ALLOC"
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _CRTDBG_MAP_ALLOC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Когда флажок **\_CRTDBG\_MAP\_ALLOC** определен в отладочной версии приложения, базовая версия функций кучи напрямую сопоставляется с их отладочными версиями.  Флаг используется в Crtdbg.h для выполнения сопоставления.  Этот флажок доступен только если флажок [\_DEBUG](../Topic/_DEBUG.md) был определен в приложении.  
  
 Дополнительные сведения об использовании отладочной версии и базовой версии функции кучи см. в разделе [Использование отладочной версии и базовой версии](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## См. также  
 [Флаги управления](../c-runtime-library/control-flags.md)