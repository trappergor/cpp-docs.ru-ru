---
title: "isNaN _isnan, _isnanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isnan"
  - "_isnanf"
  - "isnan"
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
  - "_isnan"
  - "isnan"
  - "math/isnan"
  - "math/_isnan"
  - "math/_isnanf"
  - "_isnanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NAN (не является числом)"
  - "_isnan - функция"
  - "представление IEEE с плавающей запятой"
  - "Не является числом (NaN)"
  - "isnan - функция"
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# isNaN _isnan, _isnanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет значение с плавающей запятой не является числом \(NAN\).  
  
## Синтаксис  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### Параметры  
 *x*  
 Проверяемое значение с плавающей запятой.  
  
## Возвращаемое значение  
 В языке C `isnan` макрос и `_isnan` и `_isnanf` функции возвращают ненулевое значение, если аргумент `x` имеет значение NAN; в противном случае они возвращают 0.  
  
 В C\+\+ `isnan` шаблона функции возвращают `true` Если аргумент `x` имеет значение NAN; в противном случае они возвращают `false`.  
  
## Заметки  
 C `isnan` макрос и `_isnan` и `_isnanf` функции проверяют значение с плавающей запятой *x*, возвращает ненулевое значение, если *x* не является числом \(NAN\) значение. Значение NAN создается в том случае, если результат операции с плавающей запятой не может представить в формате с плавающей запятой IEEE 754 для указанного типа. Сведения о том, как значение NAN представляется для вывода см. в разделе [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 При компиляции как C\+\+, `isnan` макрос не определен и `isnan` шаблона функция задана. Он возвращает значение типа `bool` вместо целого.  
  
 `_isnan` И `_isnanf` функции, определенные Майкрософт.`_isnanf` Функция доступна только при компиляции для x64.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок \(C\)|Обязательный заголовок \(C\+\+\)|  
|------------------|----------------------------------|--------------------------------------|  
|`isnan`, `_isnanf`|\<math.h\>|\<math.h\> или \<cmath\>|  
|`_isnan`|\<float.h\>|\< float.h \> или \< cfloat \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_finite, \_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [\_fpclass \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)