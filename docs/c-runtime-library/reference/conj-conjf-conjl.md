---
title: "conj, conjf, conjl | Microsoft Docs"
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
  - "conj"
  - "conjf"
  - "conjl"
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
  - "conj"
  - "conjf"
  - "conjl"
  - "complex/conj"
  - "complex/conjf"
  - "complex/conjl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conj - функция"
  - "функция conjf"
  - "функция conjl"
ms.assetid: 792fccfa-19c6-4890-99f9-a3b89effccd6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# conj, conjf, conjl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает комплексно\-сопряженное комплексного числа.  
  
## Синтаксис  
  
```  
_Dcomplex conj(   
   _Dcomplex z   
);  
_Fcomplex conj(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex conj(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex conjf(   
   _Fcomplex z   
);  
_Lcomplex conjl(   
   _Lcomplex z   
);  
```  
  
#### Параметры  
 `z`  
 Комплексное число.  
  
## Возвращаемое значение  
 Сопряженное число комплексного `z`.  Результат имеет же действительной и мнимой части, что `z`, но с противоположным знаком.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `conj`, которые принимают и возвращают значения `_Fcomplex` и `_Lcomplex`. В программе на языке C `conj` всегда принимает и возвращает `_Dcomplex` значение.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`conj`, `conjf`, `conjl`|\<complex.h\>|\< ccomplex \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [нормы, normf, norml](../Topic/norm,%20normf,%20norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [cimag, cimagf, cimagl](../Topic/cimag,%20cimagf,%20cimagl.md)   
 [carg, cargf, cargl](../Topic/carg,%20cargf,%20cargl.md)   
 [CAB\-файлы, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)