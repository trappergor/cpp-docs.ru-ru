---
title: "_getcwd, _wgetcwd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wgetcwd"
  - "_getcwd"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd"
  - "wgetcwd"
  - "_wgetcwd"
  - "tgetcwd"
  - "_tgetcwd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "getcwd - функция"
  - "рабочая папка"
  - "_wgetcwd - функция"
  - "_getcwd - функция"
  - "текущая рабочая папка"
  - "wgetcwd - функция"
  - "Работа текущего каталоги [C++]"
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _getcwd, _wgetcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает текущий рабочий каталог.  
  
## Синтаксис  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### Параметры  
 `buffer`  
 Место хранения пути.  
  
 `maxlen`  
 Максимальная длина пути в символах: `char` для `_getcwd` и `wchar_t` для `_wgetcwd`.  
  
## Возвращаемое значение  
 Возвращает указатель на `buffer`. Возвращаемое значение `NULL` указывает на ошибку, а для `errno` задается значение `ENOMEM`, указывающее на недостаток памяти для выделения `maxlen` байт \(если аргумент `NULL` задан как `buffer`\), или значение `ERANGE`, указывающее, что длина пути превышает `maxlen`. Если значение `maxlen` меньше или равно нулю, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_getcwd` получает полный путь текущего рабочего каталога для диска по умолчанию и сохраняет его в параметре `buffer`. Целочисленный аргумент `maxlen` указывает максимальную длину пути. Если длина пути \(включая завершающий нуль\-символ\) превышает значение `maxlen`, возникает ошибка*.* Аргумент `buffer` может быть `NULL`; с помощью `malloc` автоматически выделяется буфер минимального размера `maxlen` \(больше только при необходимости\) для сохранения пути. Позже этот буфер можно освободить путем вызова `free` и передачи в него возвращаемого значения `_getcwd` \(указателя на выделенный буфер\).  
  
 `_getcwd` возвращает строку, представляющую путь к текущему рабочему каталогу. Если текущим рабочим каталогом является корневой каталог, строка заканчивается обратной косой чертой \( `\` \). Если текущий рабочий каталог отличается от корневого, строка заканчивается именем каталога, а не обратной косой чертой.  
  
 `_wgetcwd` — это версия с расширенными символами для `_getcwd`; аргумент `buffer` и возвращаемое значение `_wgetcwd` являются строками с расширенными символами. Поведение `_wgetcwd` и `_getcwd` идентично в противном случае.  
  
 Если определены директивы `_DEBUG` и `_CRTDBG_MAP_ALLOC`, вызовы функций `_getcwd` и `_wgetcwd` заменяются вызовами функций `_getcwd_dbg` и `_wgetcwd_dbg`, чтобы разрешить отладку выделения памяти. Дополнительные сведения см. в разделе [\_getcwd\_dbg, \_wgetcwd\_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_getcwd`|\<direct.h\>|  
|`_wgetcwd`|\<direct.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## Эквивалент в .NET Framework  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../Topic/_chdir,%20_wchdir.md)   
 [\_mkdir, \_wmkdir](../Topic/_mkdir,%20_wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)