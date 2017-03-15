---
title: "Предупреждение компилятора (уровень 1) C4730 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4730"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4730"
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 1) C4730
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"main" : смешивание в выражении операндов с плавающей запятой и \_m64 может привести к созданию неверного кода  
  
 Функция использует типы [\_\_m64](../../cpp/m64.md) и **float**\/**double**.  Так как MMX и регистры с плавающей запятой делят одно и тоже физическое пространство \(их нельзя использовать одновременно\), используя типы `__m64` и **float**\/**double** в одной и той же функции может привести к повреждению данных, возможному генерированию исключения.  
  
 Для безопасного использования типов и типов с плавающей запятой `__m64` в одной и той же функции, каждая инструкция, которая использует один из типов должна отделяться **\_m\_empty\(\)** \(для MMX\) или встроенной функции **\_m\_femms\(\)** \(для 3DNow\!\).  
  
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