---
title: "fmin, fminf, fminl2 | Microsoft Docs"
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
  - "fmin"
  - "fminf"
  - "fminl"
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
  - "fmin"
  - "fminf"
  - "fminl"
  - "math/fmin"
  - "math/fminf"
  - "math/fminl"
helpviewer_keywords: 
  - "fmin - функция"
  - "fminf - функция"
  - "функция fminl"
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# fmin, fminf, fminl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет наименьшее из двух указанных значений.  
  
## Синтаксис  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
  
```  
  
#### Параметры  
 `x`  
 Первое сравниваемое значение.  
  
 `y`  
 Второе сравниваемое значение.  
  
## Возвращаемое значение  
 В случае успеха возвращает наименьшее значение из `x` или `y`.  
  
|Ввод|Результат|  
|----------|---------------|  
|`x` имеет значение NaN|`y`|  
|`y` имеет значение NaN|`x`|  
|`x` и `y` имеют тип NaN|NaN|  
  
 Функция не вызывает [\_matherr](../../c-runtime-library/reference/matherr.md) должен быть вызван, вызвать исключения с плавающей запятой, или изменить значение `errno`.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `fmin` принимающие и возвращающие float и long double типов. В программе на языке C `fmin` всегда принимает и возвращает значение типа double.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`fmin`, `fminf`,  `fminl`|C: \< math.h \><br /><br /> C\+\+: \< math.h \> и \< cmath \>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)