---
title: "_CIatan2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIatan2"
apilocation: 
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIatan2"
  - "_CIatan2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIatan2 - встроенный объект"
  - "CIatan2 - встроенный объект"
ms.assetid: 31f8cc78-b79f-4576-b73b-8add18e08680
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIatan2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет арктангенс *x* \/ *y*, где *x* и *y* — значения на вершине стека.  
  
## Синтаксис  
  
```  
void __cdecl _CIatan2();  
```  
  
## Заметки  
 Эта версия функции `atan2` имеет специализированное соглашение о вызовах, которое распознает компилятор.  Ускоряется по мере выполнения, поскольку она предотвращает создание копий и помогает с распределением регистра.  
  
 Результирующее значение кладется на вершину стека.  
  
## Требования  
 **Платформа:** x86  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)