---
title: "_umul128 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__umul128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__umul128 intrinsic"
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _umul128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Умножает два 64\-разрядных целых числа без знака, переданных в качестве первых двух аргументов, и помещает старшие 64 разряда произведения в 64\-разрядное целое число без знака, на которое указывает `HighProduct` и возвращает младшие 64 разряда произведения.  
  
## Синтаксис  
  
```  
unsigned __int64 _umul128(     unsigned __int64 Multiplier,     unsigned __int64 Multiplicand,     unsigned __int64 *HighProduct  );  
```  
  
#### Параметры  
 \[in\] `Multiplier`  
 Первое 64\-разрядное целое для умножения.  
  
 \[in\] `Multiplicand`  
 Второе 64\-разрядное целое для умножения.  
  
 \[выходной\] `HighProduct`  
 Старшие 64 разряда произведения.  
  
## Возвращаемое значение  
 Младшие 64 разряда произведения.  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`_umul128`|ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
  
## Пример  
  
```  
// umul128.c  
// processor: IPF, x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_umul128)  
  
int main()  
{  
    unsigned __int64 a = 0x0fffffffffffffffI64;  
    unsigned __int64 b = 0xf0000000I64;  
    unsigned __int64 c, d;  
  
    d = _umul128(a, b, &c);  
  
    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);  
}  
```  
  
  **0xfffffffffffffff \* 0xf0000000 \= 0xeffffffffffffff10000000**   
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)