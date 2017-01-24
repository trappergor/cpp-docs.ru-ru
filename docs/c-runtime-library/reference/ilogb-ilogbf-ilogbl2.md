---
title: "ilogb, ilogbf, ilogbl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
  - "math/ilogb"
  - "math/ilogbf"
  - "math/ilogbl"
helpviewer_keywords: 
  - "ilogb - функция"
  - "ilogbf - функция"
  - "функция ilogbl"
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ilogb, ilogbf, ilogbl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает целое число, представляющее несмещенной по основанию 2 экспоненты заданного значения.  
  
## Синтаксис  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Указанное значение.  
  
## Возвращаемое значение  
 В случае успешного выполнения возврата экспоненты по основанию 2 `x` как со знаком `int` значение.  
  
 В противном случае — возвращает одно из следующих значений, определенных в \< math.h \>.  
  
|Ввод|Результат|  
|----------|---------------|  
|±0|FP\_ILOGB0|  
|±INF ±nan, неопределенное|FP\_ILOGBNAN|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `ilogb` принимающие и возвращающие float и long double типов. В программе на языке C `ilogb` всегда принимает и возвращает значение типа double.  
  
 При вызове этой функции аналогичен вызову эквивалент `logb` функции, а затем приведение возвращаемого значения `int`.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`ilogb`, `ilogbf`,  `ilogbl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb, logbf, logbl, \_logb, \_logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)