---
title: "catanh, catanhf, catanhl | Microsoft Docs"
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
  - "catanh"
  - "catanhf"
  - "catanhl"
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
  - "catanh"
  - "catanhf"
  - "catanhl"
  - "complex/catanh"
  - "complex/catanhf"
  - "complex/catanhl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция catanh"
  - "функция catanhf"
  - "функция catanhl"
ms.assetid: 1b6021cb-647a-41b4-9d7f-919cc8b57b86
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# catanh, catanhf, catanhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает обратный гиперболический тангенс комплексное число, с сокращает ветви попадает в интервал \[−1; \+ 1\] на реальных оси.  
  
## Синтаксис  
  
```  
_Dcomplex catanh(   
   _Dcomplex z   
);  
_Fcomplex catanh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex catanh(   
   _Lcomplex z   
);  //  C++ only  
_Fcomplex catanhf(   
   _Fcomplex z   
);  
_Lcomplex catanhl(   
   _Lcomplex z   
);  
```  
  
#### Параметры  
 `z`  
 Комплексное число, представляющее угол в радианах.  
  
## Возвращаемое значение  
 Обратный гиперболический тангенс `z`, в радианах. Результат неограничен реальных оси и в интервале \[−iπ\-2; \+ iπ\-2\] мнимой оси. Если произойдет ошибка домена `z` не попадает в интервал \[\-1, \+ 1\]. Если произойдет ошибка полюсе `z` \-1 или \+ 1.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `catanh`, которые принимают и возвращают значения `_Fcomplex` и `_Lcomplex`. В программе на языке C `catanh` всегда принимает и возвращает `_Dcomplex` значение.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`catanh`, `catanhf`, `catanhl`|\<complex.h\>|\< ccomplex \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh, csinhf, csinhl](../Topic/csinh,%20csinhf,%20csinhl.md)   
 [casinh, casinhf, casinhl](../Topic/casinh,%20casinhf,%20casinhl.md)   
 [ccosh, ccoshf, ccoshl](../Topic/ccosh,%20ccoshf,%20ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)