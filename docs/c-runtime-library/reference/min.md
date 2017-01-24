---
title: "__min | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__min"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__min"
  - "min"
  - "_min"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__min - макрос"
  - "_min - макрос"
  - "min - макрос"
  - "minimum - макрос"
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __min
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает меньшее из двух значений.  
  
## Синтаксис  
  
```  
type __min(  
   type a,  
   type b   
);  
```  
  
#### Параметры  
 `type`  
 Любой числовой тип данных  
  
 `a, b`  
 Значения любого числового типа для сравнения.  
  
## Возвращаемое значение  
 Меньшее из двух аргументов.  
  
## Заметки  
 Макрос `__min` сравнивает два значения и возвращает значение меньшего.  Аргументы могут быть любого числового типа данных со знаком или без знака.  И аргументы и возвращаемое значение должны иметь одинаковый тип данных.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`__min`|\<stdlib.h\>|  
  
## Пример  
  
```  
// crt_minmax.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int a = 10;  
   int b = 21;  
  
   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );  
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );  
}  
```  
  
  **Большее из 10 и 21 — 21**  
**Меньшее из 10 и 21 — 10**   
## Эквивалент в .NET Framework  
 [System::Math::Min](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_\_max](../../c-runtime-library/reference/max.md)