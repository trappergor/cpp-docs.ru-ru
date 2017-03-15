---
title: "clog, clogf, clogl | Microsoft Docs"
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
  - "clog"
  - "clogf"
  - "clogl"
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
  - "clog"
  - "clogf"
  - "clogl"
  - "complex/clog"
  - "complex/clogf"
  - "complex/clogl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clog - функция"
  - "функция clogf"
  - "функция clogl"
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# clog, clogf, clogl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает натуральный логарифм комплексного числа с ветвью разрезать отрицательной полуоси реальной.  
  
## Синтаксис  
  
```  
_Dcomplex clog(   
   _Dcomplex z   
);  
_Fcomplex clog(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex clog(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clogf(   
   _Fcomplex z   
);  
_Lcomplex clogl(   
   _Lcomplex z   
);  
```  
  
#### Параметры  
 `z`  
 Основание логарифма.  
  
## Возвращаемое значение  
 Натуральный логарифм числа `z`. Результат неограничен реальных оси и в интервале \[−iπ \+ iπ\] мнимой оси.  
  
 Ниже перечислены возможные возвращаемые значения  
  
|параметр z|Возвращаемое значение|  
|----------------|---------------------------|  
|Положительное число|Десятичный логарифм z|  
|Нуль|\- ∞|  
|Отрицательное число|NaN|  
|NaN|NaN|  
|\+ ∞|\+ ∞|  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `clog`, которые принимают и возвращают значения `_Fcomplex` и `_Lcomplex`. В программе на языке C `clog` всегда принимает и возвращает `_Dcomplex` значение.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`clog`, `clogf`, `clogl`|\<complex.h\>|\< ccomplex \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10, clog10f, clog10l](../Topic/clog10,%20clog10f,%20clog10l.md)