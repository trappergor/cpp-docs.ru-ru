---
title: "_CIlog10 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIlog10"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIlog10"
  - "_CIlog10"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIlog10 - встроенный объект"
  - "CIlog10 - встроенный объект"
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIlog10
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполняет операцию `log10` над верхним значением в стеке.  
  
## Синтаксис  
  
```  
void __cdecl _CIlog10();  
```  
  
## Заметки  
 Эта версия функции `log10` имеет специализированное соглашение о вызовах, которое распознает компилятор.  Функция ускоряется по мере выполнения, поскольку она предотвращает создание копий и помогает с распределением регистра.  
  
 Результирующее значение кладется на вершину стека.  
  
## Требования  
 **Платформа:** x86  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../Topic/log,%20logf,%20log10,%20log10f.md)