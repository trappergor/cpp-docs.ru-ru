---
title: Предупреждение компилятора (уровень 1) C4730 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4730
dev_langs:
- C++
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 467d9fd04e2fef78d480fc4db1417b6e4c8d5641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4730"></a>Предупреждение компилятора (уровень 1) C4730
«main»: смешение _m64 и с плавающей запятой, выражения могут стать причиной неверного кода  
  
 Функция использует [__m64](../../cpp/m64.md) и **float**/**двойные** типов. Так как MMX и регистры с плавающей запятой имеют одинаковое физического зарегистрировать пространства (нельзя использовать одновременно), с помощью `__m64` и **float**/**двойные** типов в одном функция может привести к повреждению данных, возможно, вызывая исключение.  
  
 Для безопасного использования `__m64` типов и типов с плавающей запятой в той же функции, каждая инструкция, которая использует один из типов должны быть разделены **_m_empty()** (для MMX) или **_m_femms()** (для 3DNow!) Встроенная функция.  
  
 Следующий пример приводит к возникновению ошибки C4730:  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```