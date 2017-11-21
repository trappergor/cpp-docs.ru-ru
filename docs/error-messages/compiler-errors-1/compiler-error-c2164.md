---
title: "Ошибка компилятора C2164 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2164
dev_langs: C++
helpviewer_keywords: C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2a60b263dad350a0c2e28d3d20053ff10f128e24
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2164"></a>Ошибка компилятора C2164
«функция»: подставляемая функция не объявлена  
  
 `intrinsic` Pragma использует необъявленную функцию (только в случае с **/Oi**). Или один из встроенных функций компилятора использована без включения ее файла заголовка.  
  
 Следующий пример приводит к возникновению ошибки C2164:  
  
```  
// C2164.c  
// compile with: /c  
// processor: x86  
// Uncomment the following line to resolve.  
// #include "xmmintrin.h"  
void b(float *p) {  
   _mm_load_ss(p);   // C2164  
}  
```