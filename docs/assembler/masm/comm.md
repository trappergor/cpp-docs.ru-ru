---
title: "COMM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COMM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMM directive"
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# COMM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает общинная с атрибуты, указанные в переменной `definition`.  
  
## Синтаксис  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## Заметки  
 Каждое `definition` имеет следующую форму:  
  
 \[\[langtype\[\[\]\]**NEAR** &#124; **ДАЛЕКО**\]\] метка**.**`type`\[\[**.**Счетчик\]\]  
  
 *метка* имя переменной.  `type` может быть любой описатель типа \([byte](../../assembler/masm/byte-masm.md)"  [WORD](../../assembler/masm/word.md)и т п\) или целое число, указывающее количество байтов.  *Счетчик* указывает количество объектов данных \(по умолчанию\).  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)