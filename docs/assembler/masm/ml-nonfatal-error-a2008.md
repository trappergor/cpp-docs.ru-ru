---
title: "ML Nonfatal Error A2008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2008"
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**синтаксическая ошибка:**  
  
 Токен в текущем расположении, вызвавшего синтаксическую ошибку.  
  
 Одно из следующих действий может происходить:  
  
-   Префикс был добавлен знак многоточия или был пропущен в рекомендации.  
  
-   Зарезервированое слово \(например, **C** OR  **Размер**\), используемый в качестве идентификатора.  
  
-   Инструкции использовалась, которая не была доступна с текущего выделения процессора или сопроцессора.  
  
-   Оператор среды выполнения сравнения \(например, `==`выписке\), используемого в условных сборки вместо реляционного оператора \(как  [EQ \(Равно\)](../../assembler/masm/operator-eq.md)\).  
  
-   Данной инструкции или директиве слишком мало операндов.  
  
-   Директива устарелая была использована.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)