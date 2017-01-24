---
title: "gets_s, _getws_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getws_s"
  - "gets_s"
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
  - "_getws_s"
  - "gets_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getws_s - функция"
  - "вызывать переполнение буфера"
  - "буферы, исключение переполнения"
  - "буферы, вызывать переполнение буфера"
  - "gets_s - функция"
  - "getws_s - функция"
  - "линии, получение"
  - "стандартный ввод, чтение из"
  - "потоки, получение строк"
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 29
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gets_s, _getws_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает строку из потока `stdin`.  В этих версиях [gets, \_getws](../../c-runtime-library/gets-getws.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `buffer`  
 Место хранения входной строки.  
  
 \[входящий\] `sizeInCharacters`  
 Размер буфера.  
  
## Возвращаемое значение  
 Возвращает значение `buffer` в случае успеха.  Указатель `NULL` говорит об ошибке или конце файла.  Используйте [ferror](../../c-runtime-library/reference/ferror.md) или [feof](../../c-runtime-library/reference/feof.md) для определения того, что именно произошло.  
  
## Заметки  
 Функция `gets_s` считывает строку из стандартного потока ввода `stdin` и сохраняет его в `buffer`.  Строка состоит из всех символов до первого символа новой строки \('\\n'\).  `gets_s` затем заменяет символ новой строки на нулевой символом \('\\0'\) перед тем, как вернуть строку.  Напротив, функция `fgets_s` сохраняет символ новой строки.  
  
 Если первый прочитанный символ — символ конца файла, в начале `buffer` сохраняется нулевой символ и возвращается `NULL`.  
  
 `_getws` — это версия функции `gets_s` с расширенными символами; ее аргумент и возвращаемое значение являются строками расширенных символов.  
  
 Если `buffer` — `NULL`, или `sizeInCharacters` меньше или равен нулю, или если буфер слишком мал для хранения входной строки и нулевого завершающего символа, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `NULL` и устанавливают для `ERANGE` значение errno.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`gets_s`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
  **`Привет!`Введенная строка: Привет\!**   
## Эквивалент в .NET Framework  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../Topic/fputs,%20fputws.md)   
 [puts, \_putws](../Topic/puts,%20_putws.md)