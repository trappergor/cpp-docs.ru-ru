---
title: "cpow, cpowf, cpowl | Microsoft Docs"
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
  - "cpow"
  - "cpowf"
  - "cpowl"
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
  - "cpow"
  - "cpowf"
  - "cpowl"
  - "complex/cpow"
  - "complex/cpowf"
  - "complex/copwl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция cpow"
  - "функция cpowf"
  - "функция комплексное и cpowl"
ms.assetid: 83fe2187-22b7-4295-ab16-4d77abdbb80b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# cpow, cpowf, cpowl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает значение числа, возведенного в заданную степень, в которых базового и экспоненты комплексных чисел. Эта функция имеет Вырезать экспоненты вдоль оси реальных отрицательных ветви.  
  
## Синтаксис  
  
```  
_Dcomplex cpow(   
   _Dcomplex x, _Dcomplex y   
);  
_Fcomplex cpow(   
   _Fcomplex x, _Fcomplex y   
);  // C++ only  
_Lcomplex cpow(   
   _Lcomplex x, _Lcomplex y   
);  // C++ only  
_Fcomplex cpowf(   
   _Fcomplex x, _Fcomplex y   
);  
_Lcomplex cpowl(   
   _Lcomplex x, _Lcomplex y   
);  
```  
  
#### Параметры  
 `x`  
 Основание.  
  
 `y`  
 Показатель степени.  
  
## Возвращаемое значение  
 Значение `x` степени `y` с ветвью Вырезать для `x` вдоль оси реальных отрицательное.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `cpow`, которые принимают и возвращают значения `_Fcomplex` и `_Lcomplex`. В программе на языке C `cpow` всегда принимает и возвращает `_Dcomplex` значение.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`cpow`, `cpowf`, `cpowl`|\<complex.h\>|\< ccomplex \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [clog10, clog10f, clog10l](../Topic/clog10,%20clog10f,%20clog10l.md)   
 [clog, clogf, clogl](../../c-runtime-library/reference/clog-clogf-clogl.md)