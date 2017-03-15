---
title: "_finite, _finitef | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_finite"
  - "_finitef"
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
  - "finite"
  - "_finite"
  - "_finitef"
  - "math/_finite"
  - "math/_finitef"
  - "float/_finite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "finite - функция"
  - "_finite - функция"
  - "Функция _finitef"
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _finite, _finitef
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли значение с плавающей запятой конечным.  
  
## Синтаксис  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### Параметры  
 `x`  
 Проверяемое значение с плавающей запятой.  
  
## Возвращаемое значение  
 `_finite` и `_finitef` возвращают ненулевое значение, если аргумент *x* является конечным, то есть если –INF \< `x` \< \+INF. Возвращает 0, если аргумент является бесконечным или NAN.  
  
## Заметки  
 `_finite` И `_finitef` функции, определенные Майкрософт.`_finitef` Функция компилируется только доступна, если для x86 ARM или ARM64 платформы.  
  
## Требования  
  
|Функция|Обязательный заголовок \(C\)|Обязательный заголовок \(C\+\+\)|  
|-------------|----------------------------------|--------------------------------------|  
|`_finite`|\<float.h\> или \<math.h\>|\<float.h\>, \<math.h\>, \<cfloat\> или \<cmath\>|  
|`_finitef`|\<math.h\>|\<math.h\> или \<cmath\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 [System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isNaN \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [\_fpclass \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)