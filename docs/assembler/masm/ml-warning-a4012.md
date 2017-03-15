---
title: "ML Warning A4012 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A4012"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A4012"
ms.assetid: 842b1259-9679-4eeb-a02d-672a583a94e5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Warning A4012
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**число линии для сегмента без КОДА классов"**  
  
 Были инструкции в сегменте, который не имеет имя класса, который заканчивается на "КОД". Ассемблер не создал данные CodeView для этих инструкций.  
  
 CodeView не может обрабатывать модулей с кодом в сегментах с именами класса, в которых не оканчиваются на "КОД".  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)