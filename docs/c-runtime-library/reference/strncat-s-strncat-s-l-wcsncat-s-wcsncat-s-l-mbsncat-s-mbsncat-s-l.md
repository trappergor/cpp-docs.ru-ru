---
title: "strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsncat_s_l"
  - "wcsncat_s"
  - "_mbsncat_s_l"
  - "_mbsncat_s"
  - "strncat_s"
  - "_strncat_s_l"
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
  - "strncat_s_l"
  - "_mbsncat_s_l"
  - "_tcsncat_s"
  - "wcsncat_s"
  - "wcsncat_s_l"
  - "strncat_s"
  - "_mbsncat_s"
  - "_tcsncat_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsncat_s - функция"
  - "_mbsncat_s_l - функция"
  - "_tcsncat_s - функция"
  - "_tcsncat_s_l - функция"
  - "дополнение строк"
  - "объединение строк"
  - "mbsncat_s - функция"
  - "mbsncat_s_l - функция"
  - "объединение строк [C++]"
  - "строки [C++], присоединение"
  - "strncat_s - функция"
  - "strncat_s_l - функция"
  - "wcsncat_s - функция"
  - "wcsncat_s_l - функция"
ms.assetid: de77eca2-4d9c-4e66-abf2-a95fefc21e5a
caps.latest.revision: 42
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 42
---
# strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Добавляет символы в строку.  В этих версиях [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  `_mbsncat_s` и `_mbsncat_s_l` невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t strncat_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncat_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncat_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncat_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncat_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count  
);  
errno_t _mbsncat_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t strncat_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncat_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncat_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncat_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `strDest`  
 Строка назначения, завершающаяся символом NULL.  
  
 \[входящий\]`numberOfElements`  
 Размер буфера назначения.  
  
 \[входной\]`strSource`  
 Исходная строка, завершающаяся символом NULL.  
  
 \[входящий\]`count`  
 Количество добавляемых знаков, или [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[входящий\] `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Возвращает 0 при успехе; код ошибки при неудаче.  
  
### Условия возникновения ошибки  
  
|`strDestination`|`numberOfElements`|`strSource`|Возвращаемое значение|Содержимое `strDestination`.|  
|----------------------|------------------------|-----------------|---------------------------|----------------------------------|  
|`NULL` или без признака завершения|any|any|`EINVAL`|без изменений|  
|any|any|`NULL`|`EINVAL`|без изменений|  
|any|0 или слишком мало|any|`ERANGE`|без изменений|  
  
## Заметки  
 Эти функции пытаются добавить первые `D` символов строки `strSource` в конец строки `strDest`, где `D` меньшее из величины `count` и длины `strSource`.  Если эти добавляемые `D` символов поместятся внутри `strDest` \(чей размер задается как `numberOfElements`\), и по\-прежнему останется место для завершающего нуль\-символа, тогда эти символы добавляются, начиная с исходного нуль\-символа `strDest`, и добавляется новый завершающий нуль\-символ; в противном случае `strDest`\[0\] становится равным нуль\-символу, и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Для вышеприведенного абзаца есть исключения.  Если `count` равен [\_TRUNCATE](../../c-runtime-library/truncate.md), то в `strDest` добавляется столько символов из `strSource`, сколько поместится, что оставит место для добавления завершающего нуль\-символа.  
  
 Например:  
  
 `char dst[5];`  
  
 `strncpy_s(dst, _countof(dst), "12", 2);`  
  
 `strncat_s(dst, _countof(dst), "34567", 3);`  
  
 это означает, что происходит попытка добавить с помощью `strncat_s` три символа к двум символам в буфере длиной в пять символов; это не оставит места для завершающего нуль\-символа, поэтому `strncat_s` обнуляет строку и вызывает обработчик недопустимого параметра.  
  
 Если необходимо усечение, следует использовать `_TRUNCATE` или отрегулировать параметр `size` соответствующим образом:  
  
 `strncat_s(dst, _countof(dst), "34567", _TRUNCATE);`  
  
 или  
  
 `strncat_s(dst, _countof(dst), "34567", _countof(dst)-strlen(dst)-1);`  
  
 Во всех случаях, результирующая строка завершается нуль\-символом.  Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 Если параметр `strSource` или `strDest` равен `NULL`, или `numberOfElements` равен нулю, то вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает `EINVAL` без изменения параметров.  
  
 `wcsncat_s` и `_mbsncat_s` — двубайтовая и многобайтовая символьные версии `strncat_s`.  Строковые аргументы и возвращаемое значение `wcsncat_s`представляют собой строки расширенных символов; аргументы и возвращаемое значение `_mbsncat_s` представляют собой многобайтовые строки.  В остальных случаях эти три функции ведут себя идентично.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsncat_s`|`strncat_s`|`_mbsnbcat_s`|`wcsncat_s`|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
 `_strncat_s_l` и `_wcsncat_s_l` не зависят от языкового стандарта; они предназначены только для `_tcsncat_s_l`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strncat_s`|\<string.h\>|  
|`wcsncat_s`|\<string.h\> или \<wchar.h\>|  
|`_mbsncat_s`, `_mbsncat_s_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strncat_s.cpp  
// compile with: /MTd  
  
// These #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncat_s_tester( const char * initialDest,  
                          const char * src,  
                          int count )  
{  
   char dest[10];  
   strcpy_s( dest, _countof(dest), initialDest );  
  
   printf_s( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf_s( "Appending '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf_s( "Appending %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   printf_s( "    old contents of dest: '%s'\n", dest );  
  
   errno_t err = strncat_s( dest, _countof(dest), src, count );  
  
   printf_s( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncat_s_tester( "hi ", "there", 4 );  
   strncat_s_tester( "hi ", "there", 5 );  
   strncat_s_tester( "hi ", "there", 6 );  
  
   printf_s( "\nDestination buffer too small:\n" );  
   strncat_s_tester( "hello ", "there", 4 );  
  
   printf_s( "\nTruncation examples:\n" );  
  
   errno_t err = strncat_s_tester( "hello ", "there", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncat_s_tester( "hello ", "!", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf_s( "\nSecure template overload example:\n" );  
  
   char dest[10] = "cats and ";  
   strncat( dest, "dachshunds", 15 );  
   // With secure template overloads enabled (see #define  
   // at top of file), the preceding line is replaced by  
   //    strncat_s( dest, _countof(dest), "dachshunds", 15 );  
   // Instead of causing a buffer overrun, strncat_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncat would  
   // append "dachshunds" and overrun the dest buffer.  
   printf_s( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf_s(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
  **Appending 4 chars of 'there' to 10\-byte buffer dest**  
 **old contents of dest: 'hi '**  
 **new contents of dest: 'hi ther'**  
**Appending 5 chars of 'there' to 10\-byte buffer dest**  
 **old contents of dest: 'hi '**  
 **new contents of dest: 'hi there'**  
**Appending 6 chars of 'there' to 10\-byte buffer dest**  
 **old contents of dest: 'hi '**  
 **new contents of dest: 'hi there'**  
**Destination buffer too small:**  
**Appending 4 chars of 'there' to 10\-byte buffer dest**  
 **old contents of dest: 'hello '**  
**Invalid parameter handler invoked: \(L"Buffer is too small" && 0\)**  
 **new contents of dest: ''**  
**Truncation examples:**  
**Appending 'there' to 10\-byte buffer dest with truncation semantics**  
 **old contents of dest: 'hello '**  
 **new contents of dest: 'hello the'**  
 **truncation did occur**  
**Appending '\!' to 10\-byte buffer dest with truncation semantics**  
 **old contents of dest: 'hello '**  
 **new contents of dest: 'hello \!'**  
 **truncation did not occur**  
**Secure template overload example:**  
**Invalid parameter handler invoked: \(L"Buffer is too small" && 0\)**  
 **new contents of dest: ''**   
## Эквивалент в .NET Framework  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)