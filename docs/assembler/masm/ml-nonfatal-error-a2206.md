---
title: "ML Nonfatal Error A2206 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2206"
ms.assetid: 711846d0-5a09-4353-8857-60588c25526a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**отсутствует оператор в выражении**  
  
 Выражение не может быть вычислено, поскольку оно не указана оператору.  Это сообщение об ошибке может также быть побочным эффектом предшествующей ошибки программы.  
  
 Следующая линия создаст эту ошибку.  
  
```  
value1 = ( 1 + 2 ) 3  
  
```  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)