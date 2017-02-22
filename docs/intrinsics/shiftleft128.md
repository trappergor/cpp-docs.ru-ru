---
title: "__shiftleft128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__shiftleft128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__shiftleft128 intrinsic"
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# __shiftleft128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Сдвигает 128\-разрядную величину, представленную в виде двух величин по 64\-разряда `LowPart` и `HighPart`, влево на количество разрядов, указанное в `Shift` и возвращает старшие 64 разряда результата.  
  
## Синтаксис  
  
```  
unsigned __int64 __shiftleft128(     unsigned __int64 LowPart,     unsigned __int64 HighPart,     unsigned char Shift  );  
```  
  
#### Параметры  
 \[in\] `LowPart`  
 Младшие 64 разряда 128\-разрядной величины для сдвига.  
  
 \[in\] `HighPart`  
 Старшие 64 разряда 128\-разрядной величины для сдвига.  
  
 \[in\] `Shift`  
 Число разрядов для поворота.  
  
## Возвращаемое значение  
 Старшие 64 разряда результата.  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`__shiftleft128`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Это значение  всегда берется по модулю 64, поэтому, например, при вызове метода`__shiftleft128(1, 0, 64)`, функция будет сдвигать влево  разряды `0` младшей части возвращать старшую часть `0`, а не `1`, как в противном случае можно было ожидать.  
  
## Пример  
  
```  
// shiftleft128.c  
// processor: IPF, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic (__shiftleft128, __shiftright128)  
  
int main()  
{  
    unsigned __int64 i = 0x1I64;  
    unsigned __int64 j = 0x10I64;  
    unsigned __int64 ResultLowPart;  
    unsigned __int64 ResultHighPart;  
  
    ResultLowPart = i << 1;  
    ResultHighPart = __shiftleft128(i, j, 1);  
  
    // concatenate the low and high parts padded with 0's  
    // to display correct hexadecimal 128 bit values  
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",  
             j, i, ResultHighPart, ResultLowPart);  
  
    ResultHighPart = j >> 1;  
    ResultLowPart = __shiftright128(i, j, 1);  
  
    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",  
             j, i, ResultHighPart, ResultLowPart);    
}  
```  
  
  **0x100000000000000001 \<\< 1 \= 0x200000000000000002 0x100000000000000001 \>\> 1 \= 0x080000000000000000**   
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [\_\_shiftright128](../Topic/__shiftright128.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)