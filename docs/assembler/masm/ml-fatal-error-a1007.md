---
title: "ML Fatal Error A1007 | Microsoft Docs"
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
  - "A1007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1007"
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**слишком глубокий уровень вложенности**  
  
 Ассемблер достиг ее предел вложения.  Ограничение 20 уровней за исключением случаев, когда отмеченных в противном случае.  
  
 Следующего вложены слишком глубоко:  
  
-   Высокоуровневая как директива [.IF](../Topic/.IF.md)"  [.REPEAT](../../assembler/masm/dot-repeat.md)или  [.WHILE](../../assembler/masm/dot-while.md).  
  
-   Определение структуры.  
  
-   Директива условный\-сборки.  
  
-   Определение процедуры.  
  
-   A PUSHCONTEXT ограничение \- директива \(10\).  
  
-   Определение сегмента.  
  
-   Файл include.  
  
-   Макрос.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)