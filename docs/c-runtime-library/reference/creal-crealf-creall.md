---
title: "creal, crealf, creall | Microsoft Docs"
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
  - "creal"
  - "crealf"
  - "creall"
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
  - "creal"
  - "crealf"
  - "creall"
  - "complex/creal"
  - "complex/crealf"
  - "complex/creall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция creal"
  - "функция crealf"
  - "функция creall"
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# creal, crealf, creall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает действительная часть комплексного числа.  
  
## Синтаксис  
  
```  
double creal(   
   _Dcomplex z   
);  
float creal(   
   _Fcomplex z   
);  // C++ only  
long double creal(   
   _Lcomplex z   
);  // C++ only  
float crealf(   
   _Fcomplex z   
);  
long double creall(   
  _Lcomplex z   
);  
```  
  
#### Параметры  
 `z`  
 Комплексное число.  
  
## Возвращаемое значение  
 Вещественная часть `z`.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `creal` принимающих `_Fcomplex` или `_Lcomplex` значений и возвращают `float` или `long double` значения. В программе на языке C `creal` всегда принимает `_Dcomplex` значения и возвращает `double` значение.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`creal`, `crealf`, `creall`|\<complex.h\>|\< ccomplex \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [нормы, normf, norml](../Topic/norm,%20normf,%20norml1.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag, cimagf, cimagl](../Topic/cimag,%20cimagf,%20cimagl.md)   
 [carg, cargf, cargl](../Topic/carg,%20cargf,%20cargl.md)   
 [CAB\-файлы, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)