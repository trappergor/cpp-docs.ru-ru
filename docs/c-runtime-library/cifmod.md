---
title: "_CIfmod | Microsoft Docs"
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
  - "_CIfmod"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIfmod"
  - "CIfmod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIfmod - встроенный объект"
  - "_CIfmod - встроенный объект"
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIfmod
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет остаток с плавающей точкой от деления двух значений, находящихся на верху стека.  
  
## Синтаксис  
  
```  
void __cdecl _CIfmod();  
```  
  
## Заметки  
 Эта версия функции `fmod` имеет специализированное соглашение о вызовах, которое распознает компилятор.  Ускоряется по мере выполнения, поскольку она предотвращает создание копий и помогает с распределением регистра.  
  
 Результирующее значение кладется на вершину стека.  
  
## Требования  
 **Платформа:** x86  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmod, fmodf](../Topic/fmod,%20fmodf.md)