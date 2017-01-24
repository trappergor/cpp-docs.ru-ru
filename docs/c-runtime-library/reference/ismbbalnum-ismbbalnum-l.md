---
title: "_ismbbalnum, _ismbbalnum_l | Microsoft Docs"
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
  - "_ismbbalnum"
  - "_ismbbalnum_l"
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
  - "_ismbbalnum"
  - "ismbbalnum"
  - "_ismbbalnum_l"
  - "ismbbalnum_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbbalnum_l - функция"
  - "ismbbalnum - функция"
  - "ismbbalnum_l - функция"
  - "_ismbbalnum - функция"
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbbalnum, _ismbbalnum_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли указанный многобайтовый символ буквой или цифрой.  
  
## Синтаксис  
  
```  
int _ismbbalnum(  
   unsigned int c   
);  
int _ismbbalnum_l(  
   unsigned int c   
);  
```  
  
#### Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `_ismbbalnum` возвращает ненулевое значение, если выражение  
  
```  
isalnum || _ismbbkalnum  
```  
  
 имеет ненулевое значение для `c`, или значение 0, если это не так.  
  
 Версия этой функции с суффиксом `_l` идентична, однако для поведения, определяемого языковым стандартом, вместо текущего языкового стандарта в ней используется переданный языковой стандарт.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ismbbalnum`|\<mbctype.h\>|  
|`_ismbbalnum_l`|\<mbctype.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)