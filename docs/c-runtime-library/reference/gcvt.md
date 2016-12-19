---
title: "_gcvt | Microsoft Docs"
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
  - "_gcvt"
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
  - "_gcvt"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt - функция"
  - "преобразования, значения с плавающей запятой к строкам"
  - "CVTBUFSIZE"
  - "функции с плавающей запятой, преобразование числа в строку"
  - "gcvt - функция"
  - "числа, преобразование в строки"
  - "строки [C++], преобразование из чисел с плавающей запятой"
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _gcvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует число с плавающей запятой в строку и сохраняет ее в буфере.  Существует более безопасная версия этой функции; см. раздел [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md).  
  
## Синтаксис  
  
```  
char *_gcvt(   
   double value,  
   int digits,  
   char *buffer   
);  
```  
  
#### Параметры  
 `value`  
 Преобразуемое значение.  
  
 `digits`  
 Количество хранящихся значащих цифр.  
  
 `buffer`  
 Место хранения для результата.  
  
## Возвращаемое значение  
 `_gcvt` возвращает указатель на строку цифр.  
  
## Заметки  
 Функция `_gcvt` преобразует `value` с плавающей запятой на символьную строку \(которая включает десятичную запятую и возможный байт знака\) и запоминает строку в `buffer`.  `buffer` должен быть достаточным для размещения преобразованного значения и конечного нулевого символа, который добавляется автоматически.  Если используется размер буфера `digits` \+ 1, то функция перезапишет конец буфера.  Это происходит потому, что преобразованная строка включает десятичную запятую и может содержать знак и экспоненту.  Защита от переполнения не предусмотрена.  `_gcvt` пытается создать числа `digits` в десятичном формате.  Если не удается, он создает числа `digits` в степенном формате.  Замыкающие нули можно отключить при преобразовании.  
  
 Буфер `buffer` длины `_CVTBUFSIZE` достаточен для любого значения с плавающей запятой.  
  
 Эта функция проверяет свои параметры.  Если параметр `buffer` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, функция устанавливает `errno` в `EINVAL` и возвращает `NULL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_gcvt`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_gcvt.c  
// compile with: /W3  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   char buffer[_CVTBUFSIZE];  
   double value = -1234567890.123;  
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );  
   _gcvt( value, 12, buffer ); // C4996  
   // Note: _gcvt is deprecated; consider using _gcvt_s instead  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
  
   printf( "\n" );  
   value = -12.34567890123;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
}  
```  
  
  **The following numbers were converted by \_gcvt\(value,12,buffer\):**  
**buffer: '\-1234567890.12' \(14 chars\)**  
**buffer: '\-12345678901.2' \(14 chars\)**  
**buffer: '\-123456789012' \(13 chars\)**  
**buffer: '\-1.23456789012e\+012' \(19 chars\)**  
**buffer: '\-12.3456789012' \(14 chars\)**  
**buffer: '\-1.23456789012' \(14 chars\)**  
**buffer: '\-0.123456789012' \(15 chars\)**  
**buffer: '\-1.23456789012e\-002' \(19 chars\)**   
## Эквивалент в .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../Topic/_fcvt.md)