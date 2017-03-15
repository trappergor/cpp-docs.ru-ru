---
title: "_CIcos | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIcos"
apilocation: 
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIcos"
  - "_CIcos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIcos - встроенный объект"
  - "CIcos - встроенный объект"
ms.assetid: 6fc203fb-66f3-4ead-9784-f85833c26f1b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIcos
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет косинус верхнего значения в стеке.  
  
## Синтаксис  
  
```  
void __cdecl _CIcos();  
```  
  
## Заметки  
 Эта версия функции `cos` имеет специализированное соглашение о вызовах, которое распознает компилятор.  Ускоряется по мере выполнения, поскольку она предотвращает создание копий и помогает с распределением регистра.  
  
 Результирующее значение кладется на вершину стека.  
  
## Требования  
 **Платформа:** x86  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)