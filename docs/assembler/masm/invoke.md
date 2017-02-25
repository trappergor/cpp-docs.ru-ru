---
title: "INVOKE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INVOKE directive"
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# INVOKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает процедуру по адресу, заданному by *Выражение*передача аргументов в стеке или в регистрах в соответствии с стандартом соглашения о вызовах для типа языка.  
  
## Синтаксис  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## Заметки  
 Каждый аргумент, передаваемый процедуре может быть выражением, ключом регистра или выражение адреса \(выражением предшествуемым by `ADDR`\).  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)