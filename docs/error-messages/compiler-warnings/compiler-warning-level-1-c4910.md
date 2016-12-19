---
title: "Предупреждение компилятора (уровень 1) C4910 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4910"
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\<идентификатор\>": "\_\_declspec\(dllexport\)" и "extern" несовместимы при явном создании экземпляра  
  
 Явное создание экземпляров шаблона с именем *\<идентификатор\>* изменено ключевыми словами `__declspec(dllexport)` и `extern`. Однако эти ключевые слова являются взаимоисключающими. Ключевое слово `__declspec(dllexport)` означает создание экземпляра класса шаблона, тогда как ключевое слово `extern` не разрешает автоматическое создание экземпляра класса шаблона.  
  
## См. также  
 [Явное создание экземпляра](../Topic/Explicit%20Instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Общие правила и ограничения](../../cpp/general-rules-and-limitations.md)