---
title: "_isatty | Microsoft Docs"
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
  - "_isatty"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_isatty"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isatty - функция"
  - "проверка устройства символов"
  - "проверка устройств символов"
  - "isatty - функция"
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _isatty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, связан ли дескриптор файлов с устройством символов.  
  
## Синтаксис  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### Параметры  
 `fd`  
 Дескриптор файла, который ссылается на устройство, подлежащее проверке.  
  
## Возвращаемое значение  
 `_isatty` возвращает ненулевое значение, если дескриптор связан с устройством символов.  В противном случае `_isatty` возвращает 0.  
  
## Заметки  
 Функция `_isatty` определяет, связан ли `fd` с устройством символов \(терминалом, консолью, принтером, или последовательным портом\).  
  
 Эта функция проверяет параметр `fd`.  Если `fd` является неправильным файловым указателем, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает 0 и устанавливает `errno` в значение `EBADF`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_isatty`|\<io.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## Пример результатов выполнения  
  
```  
stdout has not been redirected to a file  
```  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)