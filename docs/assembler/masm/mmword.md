---
title: "MMWORD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MMWORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MMWORD directive"
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# MMWORD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется для обновления 64 \(sp2\) операндов мультимедиа с инструкциями MMX и SSE \(XMM\).  
  
## Синтаксис  
  
```  
MMWORD  
```  
  
## Заметки  
 `MMWORD` этот тип.  До MMWORD добавляемым к MASM, эквивалентную функциональность удалось получить с:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Хотя обе инструкции операндов, работают с пакетом обновления 64 \(sp2\) `QWORD` тип обновления 64 \(sp2\) для целых чисел без знака и  `MMWORD` тип значения мультимедиа с пакетом обновления 64 \(sp2\).  
  
 `MMWORD` должен представлять один и тот же тип, что и  [\_\_m64](../../cpp/m64.md).  
  
## Пример  
  
```  
movq     mm0, mmword ptr [ebx]  
```