---
title: "ceil, ceilf, ceill | Microsoft Docs"
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
  - "ceilf"
  - "ceil"
  - "ceill"
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
  - "ceil"
  - "ceilf"
  - "ceill"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "вычисление максимальных значений"
  - "ceil - функция"
  - "ceilf - функция"
  - "ceill - функция"
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ceil, ceilf, ceill
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет ближайшее целое число, превышающее значение.  
  
## Синтаксис  
  
```  
double ceil(   
   double x   
);  
float ceil(  
   float x  
);  // C++ only  
long double ceil(  
   long double x  
);  // C++ only  
float ceilf(  
   float x  
);  
long double ceill(  
   long double x  
);  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
## Возвращаемое значение  
 Функции `ceil` возвращают значение с плавающей запятой, представляющее наименьшее целое число, которое больше или равно `x`.  Нет какого\-либо возврата ошибки.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± `QNAN`,`IND`|Нет|`_DOMAIN`|  
  
 `ceil` имеет реализацию, которая использует набор инструкций SSE2.  Дополнительные сведения и ограничения по использованию реализации с SSE2 см. в разделе [\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузки, можно вызывать перегрузки `ceil`.  В программе на языке C `ceil` всегда принимает и возвращает значение типа double.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`ceil`, `ceilf`, `ceill`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример для [floor](../../c-runtime-library/reference/floor-floorf-floorl.md).  
  
## Эквивалент в .NET Framework  
 [System::Math::Ceiling](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../Topic/fmod,%20fmodf.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)