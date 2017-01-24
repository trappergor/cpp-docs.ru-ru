---
title: "_ismbbkalnum, _ismbbkalnum_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbkalnum"
  - "_ismbbkalnum_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbbkalnum"
  - "ismbbkalnum"
  - "ismbbkalnum_l"
  - "_ismbbkalnum_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbbkalnum_l - функция"
  - "ismbbkalnum_l - функция"
  - "_ismbbkalnum - функция"
  - "ismbbkalnum - функция"
ms.assetid: e1d70e7b-29d0-469c-9d93-442b99de22ac
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbbkalnum, _ismbbkalnum_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли определенный многобайтовый символ текстовым символом, не входящим в набор ASCII.  
  
## Синтаксис  
  
```  
int _ismbbkalnum(  
   unsigned int c   
);  
int _ismbbkalnum_l(  
   unsigned int c,  
   _locale_t locale   
);  
```  
  
#### Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `_ismbbkalnum` возвращает ненулевое значение, если целое число `c` представляет собой текстовый символ, не входящий в набор ASCII символ, и не является знаком препинания; в противном случае возвращает 0. Функция `_ismbbkalnum` использует текущий языковой стандарт для сведений о символах, зависящих от языкового стандарта. Функция `_ismbbkalnum_l` идентична функции `_ismbbkalnum` за тем исключением, что принимает в качестве параметра языковой стандарт. Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ismbbkalnum`|\<mbctype.h\>|  
|`_ismbbkalnum_l`|\<mbctype.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)