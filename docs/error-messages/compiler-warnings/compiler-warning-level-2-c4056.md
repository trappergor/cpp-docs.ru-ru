---
title: "Предупреждение компилятора (уровень 2) C4056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4056"
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 2) C4056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

переполнение в арифметической операции с константой с плавающей запятой  
  
 Арифметическая операция с константой с плавающей запятой дает результат, который превышает максимально допустимое значение.  
  
 Это предупреждение может быть вызвано оптимизацией компилятора, выполняемой в течение арифметической операции с константой.  Это предупреждение можно смело игнорировать, если оно исчезает при выключении оптимизации \([\/Od](../../build/reference/od-disable-debug.md)\).  
  
 Следующий пример приводит к возникновению ошибки C4056:  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```