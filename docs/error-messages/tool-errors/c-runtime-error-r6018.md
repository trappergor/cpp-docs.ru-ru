---
title: "Ошибка во время выполнения R6018 C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6018"
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка во время выполнения C R6018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

непредвиденная ошибка кучи  
  
 Во время выполнении операции по управлению памятью в программе произошла неизвестная ошибка.  
  
 Эта ошибка обычно возникает, если программа во время выполнения случайно изменяет данные в куче.  Однако это также может быть вызвано внутренней ошибкой кода операционной системы или времени выполнения.  
  
 Если компилятор предоставляет библиотеку, содержащую функции `_heapchk` и `_heapwalk`, их можно использовать для выявления причины ошибки.