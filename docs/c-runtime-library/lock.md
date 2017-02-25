---
title: "_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lock"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lock"
  - "_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock - функция"
  - "_lock - функция"
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _lock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает многопоточную блокировку.  
  
> [!IMPORTANT]
>  Эта функция устарела. Начиная с Visual Studio 2015 она недоступна в CRT.  
  
## Синтаксис  
  
```  
void __cdecl _lock  
   int locknum  
);  
```  
  
#### Параметры  
 \[in\] `locknum`  
 Идентификатор блокировки, которую нужно получить.  
  
## Заметки  
 Если блокировка уже была получена, этот метод все равно получает блокировку и вызывает внутреннюю ошибку среды выполнения языка C \(CRT\). Если метод не может получить блокировку, он завершается с неустранимой ошибкой и устанавливает код ошибки `_RT_LOCK`.  
  
## Требования  
 **Источник:** mlock.c  
  
## См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_unlock](../Topic/_unlock.md)