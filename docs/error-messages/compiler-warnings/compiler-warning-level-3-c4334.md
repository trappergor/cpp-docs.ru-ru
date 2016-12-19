---
title: "Предупреждение компилятора (уровень 3) C4334 | Microsoft Docs"
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
  - "C4334"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4334"
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4334
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор" : результат 32\-разрядного смещения неявно преобразуется в 64\-разрядное значение \(предполагалось 64\-разрядное смещение?\)  
  
 Результат 32\-разрядного сдвига неявно преобразован в 64\-разрядный, а компилятор подозревает, что предполагался 64\-разрядный сдвиг.  Для устранения предупреждения используйте 64\-разрядный сдвиг или явно приведите результат сдвига к 64\-разрядному.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4334.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```