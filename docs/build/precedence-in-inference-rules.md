---
title: "Приоритет правил вывода | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "правила вывода (NMAKE)"
  - "приоритет, правило зависимости"
  - "правила, вывод"
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Приоритет правил вывода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если правило определения определяется многократно, NMAKE использует определение наивысшего приоритета.  В следующем списке показан порядок приоритетов от самого высокого до самого низкого:  
  
1.  Правило определения, определенное в makefile; приоритет имеют более поздние определения.  
  
2.  Правило определения, определенное в файле Tools.ini; приоритет имеют более поздние определения.  
  
3.  Предварительно определенное правило определения.  
  
## См. также  
 [Правила вывода](../build/inference-rules.md)