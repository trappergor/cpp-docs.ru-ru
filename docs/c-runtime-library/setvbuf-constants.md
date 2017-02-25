---
title: "Константы setvbuf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_IOFBF"
  - "_IONBF"
  - "_IOLBF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_IOFBF - константа"
  - "_IOLBF - константа"
  - "_IONBF - константа"
  - "IOFBF - константа"
  - "IOLBF - константа"
  - "IONBF - константа"
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Константы setvbuf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <stdio.h>  
  
```  
  
## Заметки  
 Эти константы представляет тип буфера для `setvbuf`.  
  
 Возможные значения заданы следующими константами:  
  
|Константа|Значение|  
|---------------|--------------|  
|`_IOFBF`|Полная буферизация. Используется буфер, указанный в вызове `setvbuf`, и его размер равен указанному в вызове `setvbuf`.  Если указатель буфера имеет значение **NULL**, используется автоматически выделенный буфер указанного размера.|  
|`_IOLBF`|Эквивалентно `_IOFBF`.|  
|`_IONBF`|Буфер не используется, независимо от аргументов в вызове `setvbuf`.|  
  
## См. также  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)