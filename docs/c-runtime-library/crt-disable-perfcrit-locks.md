---
title: "_CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs"
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
  - "_CRT_DISABLE_PERFCRIT_LOCKS"
  - "CRT_DISABLE_PERFCRIT_LOCKS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS - константа"
  - "CRT_DISABLE_PERFCRIT_LOCKS - константа"
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CRT_DISABLE_PERFCRIT_LOCKS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отключает критическую с точки зрения производительности блокировку в операциях ввода вывода.  
  
## Синтаксис  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## Заметки  
 Определение этого символа может улучшить производительность в однопоточной привязанной к вводу\-выводу программе путем навязывания всем операциям ввода\-вывода однопоточной модели ввода\-вывода.  Для получения дополнительной информации см. [Производительность многопотоковых библиотек](../c-runtime-library/multithreaded-libraries-performance.md).  
  
## См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)