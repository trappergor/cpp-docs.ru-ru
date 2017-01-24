---
title: "strcpy_s, wcscpy_s, _mbscpy_s | Microsoft Docs"
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
  - "wcscpy_s"
  - "_mbscpy_s"
  - "strcpy_s"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strcpy_s"
  - "_mbscpy_s"
  - "_tcscpy_s"
  - "wcscpy_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "strcpy_s - функция"
  - "_tcscpy_s - функция"
  - "_mbscpy_s - функция"
  - "копирование строк"
  - "Копирование строк [C++]"
  - "tcscpy_s - функция"
  - "wcscpy_s - функция"
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
caps.latest.revision: 41
caps.handback.revision: 41
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcpy_s, wcscpy_s, _mbscpy_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Копирует строку. Эти версии [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md) усовершенствованной безопасностью, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  `_mbscpy_s` нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t strcpy_s(  
   char *strDestination,  
   size_t numberOfElements,  
   const char *strSource   
);  
errno_t wcscpy_s(  
   wchar_t *strDestination,  
   size_t numberOfElements,  
   const wchar_t *strSource   
);  
errno_t _mbscpy_s(  
   unsigned char *strDestination,  
   size_t numberOfElements,  
   const unsigned char *strSource   
);  
template <size_t size>  
errno_t strcpy_s(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
errno_t wcscpy_s(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
errno_t _mbscpy_s(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### Параметры  
 `strDestination`  
 Расположение строкового буфера назначения.  
  
 `numberOfElements`  
 Размер строкового буфера назначения в единицах `char` для узкой и многобайтовых функций и в единицах `wchar_t` для расширенных функций.  
  
 `strSource`  
 Исходная строка, завершающаяся нулем.  
  
## Возвращаемое значение  
 Ноль в случае успешного выполнения; в противном случае — код ошибки.  
  
### Условия ошибок  
  
|`strDestination`|`numberOfElements`|`strSource`|Возвращаемое значение|Содержимое `strDestination`|  
|----------------------|------------------------|-----------------|---------------------------|---------------------------------|  
|`NULL`|any|any|`EINVAL`|не изменено|  
|any|any|`NULL`|`EINVAL`|`strDestination`\[0\] имеет значение 0|  
|любые|0 или слишком мал|any|`ERANGE`|`strDestination`\[0\] имеет значение 0|  
  
## Заметки  
 Функция `strcpy_s` копирует содержимое по адресу `strSource`, включая завершающий символ нуля, в указанное расположение, заданное `strDestination`. Строка назначения должна быть достаточно велика для сохранения исходной строки и завершающего нуля. При перекрытии исходного и конечного буферов поведение `strcpy_s` не определено.  
  
 `wcscpy_s` является версией `strcpy_s` с расширенными символами, а `_mbscpy_s` — версией с многобайтовыми символами. Аргументы и возвращаемое значение `wcscpy_s` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbscpy_s` представляют собой многобайтовые строки. В остальном эти три функции ведут себя идентично.  
  
 Если `strDestination` или `strSource` является указателем null, или если целевой строки слишком мал, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `EINVAL` и задают для параметра `errno` значение `EINVAL`, если `strDestination` или `strSource` являются пустыми указателями. Они возвращают `ERANGE` и `errno` для `ERANGE`, если строка назначения слишком мала.  
  
 После успешного выполнения конечная строка всегда завершается нулем.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок, которые могут автоматически определять длину буфера, а также автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Для получения дополнительной информации см. [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFE. Чтобы отключить такое поведение, используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcscpy_s`|`strcpy_s`|`_mbscpy_s`|`wcscpy_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strcpy_s`|\<string.h\>|  
|`wcscpy_s`|\<string.h\> или \<wchar.h\>|  
|`_mbscpy_s`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strcpy_s.cpp  
// This program uses strcpy_s and strcat_s  
// to build a phrase.  
//  
  
#include <string.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   char string[80];  
   // using template versions of strcpy_s and strcat_s:  
   strcpy_s( string, "Hello world from " );  
   strcat_s( string, "strcpy_s " );  
   strcat_s( string, "and " );  
   // of course we can supply the size explicitly if we want to:  
   strcat_s( string, _countof(string), "strcat_s!" );  
  
   printf( "String = %s\n", string );  
}  
```  
  
```Output  
String = Hello world from strcpy_s и strcat_s!  
```  
  
## Эквивалент в .NET Framework  
 [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)