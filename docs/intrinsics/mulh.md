---
title: "__mulh | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__mulh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __mulh"
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __mulh
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Возвращает старшие 64 2 64 знаковых продукта 32\-разрядных целых чисел.  
  
## Синтаксис  
  
```  
__int64 __mulh(   
   __int64 a,   
   __int64 b   
);  
```  
  
#### Параметры  
 \[входящий\] `a`  
 Первое число для перемножения.  
  
 \[входящий\] `b`  
 Второе число для перемножения.  
  
## Возвращаемое значение  
 Старшие 64 128 бит умножения результата.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__mulh`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Эта процедура доступна только в качестве внутреннего элемента.  
  
## Пример  
  
```  
// mulh.cpp  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic (__mulh)  
  
int main()  
{  
    __int64 a = 0x0fffffffffffffffI64;  
    __int64 b = 0xf0000000I64;  
  
    __int64 result = __mulh(a, b); // the high 64 bits  
    __int64 result2 = a * b; // the low 64 bits  
  
    printf_s(" %#I64x * %#I64x = %#I64x%I64x\n",  
             a, b, result, result2);  
}  
```  
  
  **0xfffffffffffffff \* 0xf0000000 \= 0xeffffffffffffff10000000**   
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)