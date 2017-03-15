---
title: "2.6.3 barrier Directive | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.3 barrier Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**барьер** директива синхронизировать все потоки в рабочей группе.  Сталкивано каждый поток в рабочей группе ожидает, пока все остальные не достигнут этот пункт.  Синтаксис  **барьер** директива выглядит следующим образом:  
  
```  
#pragma omp barrier new-line  
```  
  
 После того как все потоки в рабочей группе сталкивались барьера каждый поток в рабочей группе начинает выполняться выписки после директивы барьера параллельно.  Обратите внимание, что поскольку **барьер** директива не имеет выписку языка c, как часть своего синтаксиса, существуют некоторые ограничения на его месте в рамках программы.  См. [Приложение C\#](../Topic/C.%20OpenMP%20C%20and%20C++%20Grammar.md) для формального грамматики.  В приведенном ниже примере показаны эти ограничения.  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```