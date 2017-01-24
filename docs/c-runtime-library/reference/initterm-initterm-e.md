---
title: "_initterm, _initterm_e | Microsoft Docs"
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
  - "_initterm_e"
  - "_initterm"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_initterm_e"
  - "initterm"
  - "_initterm"
  - "initterm_e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "initterm - функция"
  - "initterm_e - функция"
  - "_initterm - функция"
  - "_initterm_e - функция"
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _initterm, _initterm_e
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Внутренние методы, которые обходят таблицу указателей функций и инициализируют их.  
  
 Первый указатель — это начальное расположение в таблице, а второй указатель — конечное расположение.  
  
## Синтаксис  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## Возвращаемое значение  
 Ненулевой код ошибки, если инициализация завершается неудачей и генерирует ошибку; 0, если ошибка не возникает.  
  
## Заметки  
 Эти методы вызываются только внутри во время инициализации программы C\+\+.  Не следует вызывать эти методы в программе.  
  
 Когда эти методы обходят таблицу записей функций, они пропускают записи `NULL` и продолжают выполнение.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)