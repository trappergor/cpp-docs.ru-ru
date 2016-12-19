---
title: "fseek, _lseek Constants | Microsoft Docs"
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
  - "SEEK_END"
  - "SEEK_SET"
  - "SEEK_CUR"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SEEK_CUR - константа"
  - "SEEK_END - константа"
  - "SEEK_SET - константа"
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fseek, _lseek Constants
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <stdio.h>  
  
```  
  
## Заметки  
 Аргумент *origin* определяет первоначальную позицию и может быть одной из следующих констант манифеста:  
  
|Константа|Значение|  
|---------------|--------------|  
|`SEEK_END`|Конец файла|  
|`SEEK_CUR`|Текущая позиция указателя файла|  
|`SEEK_SET`|Начало файла|  
  
## См. также  
 [fseek, \_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)