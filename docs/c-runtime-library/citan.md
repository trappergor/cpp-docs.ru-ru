---
title: "_CItan | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CItan"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CItan"
  - "CItan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CItan - встроенный объект"
  - "_CItan - встроенный объект"
ms.assetid: d1ea3113-50a2-45a6-b6bc-680fcdcc0928
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CItan
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет тангенс верхнего значения в стеке.  
  
## Синтаксис  
  
```  
void __cdecl _CItan();  
```  
  
## Заметки  
 Эта версия функции `tan` имеет специализированное соглашение о вызовах, которое распознает компилятор.  Функция ускоряется по мере выполнения, поскольку она предотвращает создание копий и помогает с распределением регистра.  
  
 Результирующее значение кладется на вершину стека.  
  
## Требования  
 **Платформа:** x86  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)