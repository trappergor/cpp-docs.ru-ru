---
title: "Неустранимая ошибка NMAKE U1099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1099"
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка NMAKE U1099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

переполнение стека  
  
 Обрабатываемый makefile слишком сложен для текущего выделения стека в NMAKE.  Выделение NMAKE составляет 0x3000 \(12K\).  
  
 Чтобы увеличить выделение стека NMAKE, следует запустить служебную программу [editbin \/stack](../../build/reference/stack.md) с большим параметром стека:  
  
 **editbin \/STACK:reserve NMAKE.EXE**  
  
 где *reserve* представляет большее число, чем текущее выделение стека в NMAKE.