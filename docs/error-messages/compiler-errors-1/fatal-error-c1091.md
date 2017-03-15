---
title: "Неустранимая ошибка C1091 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1091"
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Неустранимая ошибка C1091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора: длина строки превышает "длину" байт  
  
 Длина строковой константы превышает установленное ограничение.  
  
 Можно разбить статическую строку на две \(или более\) переменных и использовать функцию [strcpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) для объединения результатов в объявлении или во время выполнения.