---
title: "Константы _locking | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_LK_RLCK"
  - "_LK_NBLCK"
  - "_LK_LOCK"
  - "_LK_NBRLCK"
  - "_LK_UNLCK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_LK_LOCK - константа"
  - "_LK_NBLCK - константа"
  - "_LK_NBRLCK - константа"
  - "_LK_RLCK - константа"
  - "_LK_UNLCK - константа"
  - "LK_LOCK - константа"
  - "LK_NBLCK - константа"
  - "LK_NBRLCK - константа"
  - "LK_RLCK - константа"
  - "LK_UNLCK - константа"
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Константы _locking
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## Заметки  
 Аргумент *mode* в вызове функции `_locking` определяет выполняемое действие блокировки.  
  
 Аргумент *mode* должен быть одной из следующих констант манифеста.  
  
 `_LK_LOCK`  
 Блокирует указанные байты.  Если байты не могут быть заблокированы, функция попытается повторить блокировку снова через 1 секунду.  Если после 10 попыток байты не могут быть заблокированы, функция возвращает ошибку.  
  
 `_LK_RLCK`  
 Эквивалентно `_LK_LOCK`.  
  
 `_LK_NBLCK`  
 Блокирует указанные байты.  Если невозможно заблокировать байты, функция возвращает ошибку.  
  
 `_LK_NBRLCK`  
 Эквивалентно `_LK_NBLCK`.  
  
 `_LK_UNLCK`  
 Разблокирует указанные байты. \(Байты должны быть заблокированы ранее.\)  
  
## См. также  
 [\_locking](../Topic/_locking.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)