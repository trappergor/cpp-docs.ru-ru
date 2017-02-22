---
title: "vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, __vswprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vswprintf_l"
  - "_vsprintf_l"
  - "vsprintf"
  - "vswprintf"
  - "__vswprintf_l"
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
  - "vstprintf"
  - "vswprintf"
  - "_vstprintf"
  - "vsprintf"
  - "__vswprintf_l"
  - "_vsprintf_l"
  - "_vswprintf_l"
  - "vswprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vswprintf_l - функция"
  - "_vsprintf_l - функция"
  - "_vstprintf - функция"
  - "_vstprintf_l - функция"
  - "_vswprintf_l - функция"
  - "вызывать переполнение буфера"
  - "буферы, исключение переполнения"
  - "буферы, вызывать переполнение буфера"
  - "форматированный текст"
  - "vsprintf - функция"
  - "vsprintf_l - функция"
  - "vstprintf - функция"
  - "vstprintf_l - функция"
  - "vswprintf - функция"
  - "vswprintf_l - функция"
ms.assetid: b8ef1c0d-58f9-4a18-841a-f1a989e1c29b
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, __vswprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывают форматированные выходные данные с помощью указателя на список аргументов.  Существуют более безопасные версии этих функций; см. раздел [vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md).  
  
## Синтаксис  
  
```  
int vsprintf(  
   char *buffer,  
   const char *format,  
   va_list argptr   
);   
int _vsprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);   
int vswprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vswprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
int __vswprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsprintf(  
   char (&buffer)[size],  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int vswprintf(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vswprintf_l(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 Место хранения выходных данных.  
  
 `count`  
 Максимальное число символов для хранения, в версии `UNICODE` для этой функции.  
  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `vsprintf` и `vswprintf` возвращают число записанных символов, не включая конечный нуль\-символ, или отрицательное значение, если произошла ошибка вывода.  Если `buffer` или `format` является указателем null, то эти функции вызывают обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эти функции возвращают \-1 и устанавливают `errno` в значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Каждая из этих функций принимает указатель на список аргументов, а затем форматирует и записывает заданные данные в область памяти, на которую указывает `buffer`.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
> [!IMPORTANT]
>  Не существует способа ограничения количества записанные символов с помощью `vsprintf`, что означает, что код, использующий эту функцию, восприимчив к переполнениям буфера.  Вместо этой функции следует использовать [\_vsnprintf](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) или вызывать [\_vscprintf](../../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md), чтобы определить, насколько больший буфер нужен.  Также убедитесь, что `format` не является строкой, определяемой пользователем.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 `vswprintf` соответствует стандарту ISO C, который требует второго параметра `count` типа `size_t`.  Чтобы принудительно использовать старое нестандартное поведение, укажите `_CRT_NON_CONFORMING_SWPRINTFS.` Старое поведение может быть не включено в будущие версии, поэтому код должен быть изменен для использования нового соответствующего поведения.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vstprintf`|`vsprintf`|`vsprintf`|`vswprintf`|  
|`_vstprintf_l`|`_vsprintf_l`|`_vsprintf_l`|`_vswprintf_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|------------------|----------------------------|------------------------------|  
|`vsprintf`, `_vsprintf_l`|\<stdio.h\> и \<stdarg.h\>|\<varargs.h\>\*|  
|`vswprintf`, `_vswprintf_l`|\<stdio.h\> или \<wchar.h\> и \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Требуется для обеспечения совместимости с UNIX V.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_vsprintf.c  
// compile with: /W3  
// This program uses vsprintf to write to a buffer.  
// The size of the buffer is determined by _vscprintf.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <stdarg.h>  
  
void test( char * format, ... )  
{  
    va_list args;  
    int     len;  
    char    *buffer;  
  
    // retrieve the variable arguments  
    va_start( args, format );  
  
    len = _vscprintf( format, args ) // _vscprintf doesn't count  
                                + 1; // terminating '\0'  
  
    buffer = (char*)malloc( len * sizeof(char) );  
  
    vsprintf( buffer, format, args ); // C4996  
    // Note: vsprintf is deprecated; consider using vsprintf_s instead  
    puts( buffer );  
  
    free( buffer );  
}  
  
int main( void )  
{  
   test( "%d %c %d", 123, '<', 456 );  
   test( "%s", "This is a string" );  
}  
```  
  
  **123 \< 456**  
**This is a string**   
## Эквивалент в .NET Framework  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [Синтаксис описания формата: функции printf и wprintf](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)