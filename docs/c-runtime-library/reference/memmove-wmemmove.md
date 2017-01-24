---
title: "memmove, wmemmove | Microsoft Docs"
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
  - "memmove"
  - "wmemmove"
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
apitype: "DLLExport"
f1_keywords: 
  - "memmove"
  - "wmemmove"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memmove - функция"
  - "wmemmove - функция"
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memmove, wmemmove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перемещает один буфер в другой.  Существуют более безопасные версии этих функций; см. раздел [memmove\_s, wmemmove\_s](../../c-runtime-library/reference/memmove-s-wmemmove-s.md).  
  
## Синтаксис  
  
```  
void *memmove(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemmove(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### Параметры  
 `dest`  
 Объект назначения.  
  
 `src`  
 Объект\-источник.  
  
 `count`  
 Число байтов \(`memmove`\) или символов \(`wmemmove`\), которые нужно скопировать.  
  
## Возвращаемое значение  
 Значение параметра `dest`*.*  
  
## Заметки  
 Копирует `count` байт \(`memmove`\) или символов \(`wmemmove`\) из `src` в `dest`*.* Если некоторые части исходной области и области назначения перекрываются, то обе функции гарантируют, что байты первоисточника в перекрывающейся области копируются перед перезаписью.  
  
 **Примечание по безопасности:** Убедитесь, что буфер места назначения равен или превосходит буфер источника.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Функции `memmove` и `wmemmove` являются нерекомендуемыми, только если перед включением заголовочного файла, содержащего эти функции, определена константа `_CRT_SECURE_DEPRECATE_MEMORY` для того, чтобы показать, что функции нерекомендуемые, как в примере ниже:  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <string.h>  
or  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`memmove`|\<string.h\>|  
|`wmemmove`|\<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_memcpy.c  
// Illustrate overlapping copy: memmove  
// always handles it correctly; memcpy may handle  
// it correctly.  
//  
  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
  
char str1[7] = "aabbcc";  
  
int main( void )  
{  
   printf( "The string: %s\n", str1 );  
   memcpy( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
  
   strcpy_s( str1, sizeof(str1), "aabbcc" );   // reset string  
  
   printf( "The string: %s\n", str1 );  
   memmove( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
}  
```  
  
  **The string: aabbcc**  
**New string: aaaabb**  
**The string: aabbcc**  
**New string: aaaabb**   
## Эквивалент в .NET Framework  
 [System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)  
  
## См. также  
 [Манипуляция буфером](../Topic/Buffer%20Manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)