---
title: "Предупреждение (уровень 1) C4401 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4401
dev_langs:
- C++
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1042550b4ea176a314e174549ed560cd3ece025
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4401"></a>Предупреждение компилятора (уровень 1) C4401
«битовое поле»: член является битовым полем  
  
 Встроенный код ассемблера пытается получить доступ к члена битового поля. Встроенная сборка нет доступа к членами-битовыми полями, поэтому используется последняя граница упаковки перед члена битового поля.  
  
 Чтобы избежать этого предупреждения, прежде чем использовать его во встроенный код ассемблера необходимо привести битовое поле в соответствующий тип. Следующий пример приводит к возникновению ошибки C4401:  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```