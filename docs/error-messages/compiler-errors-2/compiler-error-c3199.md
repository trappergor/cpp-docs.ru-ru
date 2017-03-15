---
title: "Ошибка компилятора C3199 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3199"
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3199
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимое использование прагм с плавающей запятой: исключения поддерживаются только в режиме повышенной точности  
  
 Директива pragma [float\_control](../Topic/float_control.md) используется для указания модели исключения с плавающей запятой, при этом применение параметра [\/fp](../../build/reference/fp-specify-floating-point-behavior.md) отличается от **\/fp:precise**.  
  
 Следующий пример приводит к возникновению ошибки C3199:  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```