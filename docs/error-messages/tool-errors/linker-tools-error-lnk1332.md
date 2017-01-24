---
title: "Ошибка средств компоновщика LNK1332 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1332"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1332"
ms.assetid: b31d5ca0-c27f-4177-896b-2637dccbde24
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1332
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

компоновщик \<count\> типы среды выполнения Windows, импортированных в одном модуле и определенные в другом модуле  
  
 Если он формирует текущего целевого объекта, компоновщик обнаружил типы \<`count`\> среды выполнения Windows, каждый из которых будет импортирован в одном модуле и уже определен в другом модуле.  
  
### Исправление этой ошибки  
  
-   Исправьте каждой из LNK2039 ошибок в построении согласно предложение в сообщении об ошибке.  
  
## См. также  
 [Ошибка средств компоновщика LNK2039](../../error-messages/tool-errors/linker-tools-error-lnk2039.md)   
 [Ошибки и предупреждения инструментов компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)