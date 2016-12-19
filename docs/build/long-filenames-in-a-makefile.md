---
title: "Длинные имена файлов в makefile | Microsoft Docs"
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
helpviewer_keywords: 
  - "длинные имена файлов"
  - "программа NMAKE, длинные имена файлов"
ms.assetid: 626d56fc-8879-46ba-9c2d-dd386c78cccc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Длинные имена файлов в makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следует заключать длинные имена файлов в двойные кавычки, как показано:  
  
```  
all : "VeryLongFileName.exe"  
```  
  
## См. также  
 [Содержимое файла makefile](../build/contents-of-a-makefile.md)