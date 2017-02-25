---
title: "btowc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "btowc"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "btowc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "btowc - функция"
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# btowc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определить, представляет ли целое число допустимый однобайтовый символ в начальном состоянии переноса.  
  
## Синтаксис  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
## Возвращаемое значение  
 Возвращает представление символа в расширенных символах, если целое число представляет допустимый однобайтовый символ в начальном состоянии переноса.  Возвращает WEOF, если целое число является EOF или не является допустимым однобайтовым символом в начальном состоянии переноса.  Вывод этой функции зависит от текущего языкового стандарта `LC_TYPE`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`btowc`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [mbtowc, \_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)