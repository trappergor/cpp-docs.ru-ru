---
title: "_CIpow | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIpow"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIpow"
  - "_CIpow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIpow - встроенный объект"
  - "_CIpow - встроенный объект"
ms.assetid: 477aaf0c-ac58-4252-89dd-9f3e35d47536
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIpow
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет *x*, возведенное в степень *y*, основываясь на верхних значениях стека.  
  
## Синтаксис  
  
```  
void __cdecl _CIpow();  
```  
  
## Заметки  
 Эта версия функции `pow` имеет специализированное соглашение о вызовах, которое распознает компилятор.  Ускоряется по мере выполнения, поскольку она предотвращает создание копий и помогает с распределением регистра.  
  
 Результирующее значение кладется на вершину стека.  
  
## Требования  
 **Платформа:** x86  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [pow, powf, powl](../Topic/pow,%20powf,%20powl.md)