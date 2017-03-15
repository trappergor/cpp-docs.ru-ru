---
title: "nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs"
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
  - "nextafterf"
  - "_nextafterf"
  - "nextafter"
  - "nextafterl"
  - "_nextafter"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
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
  - "nextafter"
  - "_nextafter"
  - "nextafterf"
  - "nextafterl"
  - "_nextafterf"
  - "math/nextafter"
  - "math/nextafterf"
  - "math/nextafterl"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
  - "math/nexttoward"
  - "math/nexttowardf"
  - "math/nexttowardl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_nextafter - функция"
  - "nextafter - функция"
  - "функция _nextafterf"
  - "nextafterf - функция"
  - "функция nextafterl"
  - "функция nexttoward"
  - "функция nexttowardf"
  - "функция nexttowardl"
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает следующий представимым значением с плавающей запятой.  
  
## Синтаксис  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой для запуска из.  
  
 `y`  
 Значение с плавающей запятой, чтобы перейти к.  
  
## Возвращаемое значение  
 Возвращает следующий представимым значением с плавающей запятой для возвращаемого типа после `x` в направлении `y`. Если `x`\=`y`, функция возвращает `y`, преобразованным в возвращаемый тип, исключение не запускается. Если `x` не равен `y`, результатом является denormal или ноль, задаются FE\_UNDERFLOW и FE\_INEXACT состояния исключения с плавающей запятой и возвращается правильный результат. Если параметр `x` или `y` имеет значение NAN, то возвращаемое значение является одним из входного значения NaN. Если `x` ограниченно и результатом является бесконечной или не представить в типе, возвращается правильно подписанного бесконечность или NAN, заданы состояния исключения с плавающей запятой FE\_OVERFLOW и FE\_INEXACT, и `errno` задано значение ERANGE.  
  
## Заметки  
 `nextafter` И `nexttoward` функция семейств эквивалентны, за исключением типа параметра `y`. Если `x` и `y` равны, возвращается значение `y` преобразуется в тип возвращаемого значения.  
  
 Поскольку C\+\+ допускает перегрузки, при включении \< cmath \> можно вызывать перегрузки `nextafter` и `nexttoward` возвращающее `float` и `long double` типов. В программе на языке C `nextafter` и `nexttoward` всегда возвращать `double`.  
  
 `_nextafter` И `_nextafterf` функции, определенные Майкрософт.`_nextafterf` Функция доступна только при компиляции для x64.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок \(C\)|Обязательный заголовок \(C\+\+\)|  
|------------------|----------------------------------|--------------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h\>|\<math.h\> или \<cmath\>|  
|`_nextafter`|\<float.h\>|\< float.h \> или \< cfloat \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isNaN \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)