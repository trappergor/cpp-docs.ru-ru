---
title: "Приоритет в макроопределениях | Microsoft Docs"
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
  - "макросы, приоритет"
  - "программа NMAKE, приоритет в макроопределениях"
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Приоритет в макроопределениях
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если макрос имеет несколько определений, то программа NMAKE использует определение с наивысшим приоритетом.  В следующем списке показан порядок приоритетов от самого высокого до самого низкого:  
  
1.  Макрос, определенный в командной строке;  
  
2.  Макрос, определенный в файле makefile или включаемом файле;  
  
3.  Наследуемый макрос переменной среды;  
  
4.  Макрос, определенный в файле Tools.ini;  
  
5.  Предопределенный макрос, например [CC](../build/command-macros-and-options-macros.md) и [AS](../build/command-macros-and-options-macros.md).  
  
 Используйте параметр \/E, чтобы макросы, унаследованные от переменных среды, имели больший приоритет, чем одноименные макросы из файла makefile.  Используйте оператор **\!UNDEF** для переопределения командной строки.  
  
## См. также  
 [Определение макроса NMAKE](../build/defining-an-nmake-macro.md)