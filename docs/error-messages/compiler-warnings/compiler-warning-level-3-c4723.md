---
title: "Предупреждение компилятора (уровень 3) C4723 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4723"
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

потенциальное деление на 0  
  
 Второй операнд в операции деления во время компиляции был равен нулю, что может привести к неопределенному результату.  
  
 Это предупреждение возникает только при использовании параметра [\/Og](../../build/reference/og-global-optimizations.md) или параметра оптимизации, подразумевающего \/Og.  
  
 Компилятор мог создать операнд, равный нулю.