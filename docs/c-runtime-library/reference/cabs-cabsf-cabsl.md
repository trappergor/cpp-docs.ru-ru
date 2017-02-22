---
title: "CAB-файлы, cabsf, cabsl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "cabs"
  - "cabsf"
  - "cabsl"
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
  - "cabs"
  - "cabsf"
  - "cabsl"
  - "complex/cabs"
  - "complex/cabsf"
  - "complex/cabsl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cabs - функция"
  - "функция cabsf"
  - "cabsl - функция"
ms.assetid: 6b8eb453-cc8f-4972-bebf-351cbdfdfc15
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# CAB-файлы, cabsf, cabsl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает абсолютное значение комплексного числа.  
  
## Синтаксис  
  
```  
double cabs(   
   _Dcomplex z   
);  
float cabs(   
   _Fcomplex z   
);  // C++ only  
long double cabs(   
   _Lcomplex z   
);  // C++ only  
float cabsf(   
   _Fcomplex z   
);  
long double cabsl(   
   _Lcomplex z   
);  
```  
  
#### Параметры  
 `z`  
 Комплексное число.  
  
## Возвращаемое значение  
 Абсолютное значение `z`.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `cabs` принимающих `_Fcomplex` или `_Lcomplex` значений и возвращают `float` или `long double` значения. В программе на языке C `cabs` всегда принимает `_Dcomplex` значения и возвращает `double` значение.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`cabs`, `cabsf`, `cabsl`|\<complex.h\>|\< ccomplex \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [нормы, normf, norml](../Topic/norm,%20normf,%20norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag, cimagf, cimagl](../Topic/cimag,%20cimagf,%20cimagl.md)   
 [carg, cargf, cargl](../Topic/carg,%20cargf,%20cargl.md)