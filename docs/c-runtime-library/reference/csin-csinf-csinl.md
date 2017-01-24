---
title: "csin, csinf, csinl | Microsoft Docs"
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
  - "csin"
  - "csinf"
  - "csinl"
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
  - "csin"
  - "csinf"
  - "csinl"
  - "complex/csin"
  - "complex/csinf"
  - "complex/csinl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "функция csin"
  - "функция csinf"
  - "функция csinl"
ms.assetid: 3ed475e8-9aae-42ba-a25c-7ae656a0fd4d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# csin, csinf, csinl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает синус комплексного числа.  
  
## Синтаксис  
  
```  
_Dcomplex csin(   
   _Dcomplex z   
);  
_Fcomplex csin(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex csin(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex csinf(   
   _Fcomplex z   
);  
_Lcomplex csinl(   
   _Lcomplex z   
);  
```  
  
#### Параметры  
 `z`  
 Комплексное число, представляющее угол в радианах.  
  
## Возвращаемое значение  
 Синус `z`, в радианах.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `csin`, которые принимают и возвращают значения `_Fcomplex` и `_Lcomplex`. В программе на языке C `csin` всегда принимает и возвращает `_Dcomplex` значение.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`csin`, `csinf`, `csinl`|\<complex.h\>|\< ccomplex \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh, csinhf, csinhl](../Topic/csinh,%20csinhf,%20csinhl.md)   
 [casinh, casinhf, casinhl](../Topic/casinh,%20casinhf,%20casinhl.md)   
 [ccosh, ccoshf, ccoshl](../Topic/ccosh,%20ccoshf,%20ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)