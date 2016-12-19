---
title: ".DOSSEG | Microsoft Docs"
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
  - ".DOSSEG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".DOSSEG directive"
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .DOSSEG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Упорядочивает сегменты согласно соглашению сегмента MS\-DOS: Сегменты КОДА сначала затем в DGROUP, а затем сегменты в DGROUP.  
  
## Синтаксис  
  
```  
  
.DOSSEG  
  
```  
  
## Заметки  
 Сегменты в DGROUP за этим порядком: сегменты не в BSS или СТЕКЕ, затем сегментах BSS и, наконец, сегментах стека.  В основном используется для обеспечения поддержки CodeView в программах MASM изолированных.  Аналогично DOSSEG.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)