---
title: "ASSUME | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ASSUME"
  - "_assume_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSUME directive"
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ASSUME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Включает проверку ошибок для значений регистра.  
  
## Синтаксис  
  
```  
  
      ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## Заметки  
 После `ASSUME` активизирует, контрольные значения для ассемблера изменения значений заданного регистров.  **Ошибка** формирует ошибку, если регистр.  **NOTHING** удаляет проверка ошибок регистра.  Можно комбинировать различные типы допущений в одной выписке.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)