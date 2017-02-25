---
title: "Совместное использование констант | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SH_DENYNO"
  - "_SH_DENYRD"
  - "_SH_DENYRW"
  - "_SH_DENYWR"
  - "_SH_COMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SH_COMPAT - константа"
  - "_SH_DENYNO - константа"
  - "_SH_DENYRD - константа"
  - "_SH_DENYRW - константа"
  - "_SH_DENYWR - константа"
  - "SH_COMPAT - константа"
  - "SH_DENYNO - константа"
  - "SH_DENYRD - константа"
  - "SH_DENYRW - константа"
  - "SH_DENYWR - константа"
  - "совместное использование констант"
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Совместное использование констант
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Константы для режимов общего доступа к файлам.  
  
## Синтаксис  
  
```  
  
#include <share.h>  
  
```  
  
## Заметки  
 Аргумент *shflag* определяет режим общего доступа, который состоит из одной или нескольких констант манифеста.  Их можно использовать в сочетании с аргументами *oflag* \(см. [Файловые Константы](../c-runtime-library/file-constants.md)\).  
  
 В следующей таблице перечислены константы и их значения:  
  
|Константа|Значение|  
|---------------|--------------|  
|`_SH_DENYRW`|Запрещает доступ к файлу для чтения и записи|  
|`_SH_DENYWR`|Запрещает доступ к файлу для записи|  
|`_SH_DENYRD`|Запрещает доступ к файлу на чтение|  
|`_SH_DENYNO`|Разрешает доступ на чтение и запись|  
|`_SH_SECURE`|Устанавливает безопасный режим \(совместный доступ на чтение, монопольный доступ на запись\)|  
  
## См. также  
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)