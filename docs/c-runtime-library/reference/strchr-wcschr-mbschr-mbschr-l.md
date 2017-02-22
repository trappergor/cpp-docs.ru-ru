---
title: "strchr, wcschr, _mbschr, _mbschr_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strchr"
  - "wcschr"
  - "_mbschr_l"
  - "_mbschr"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ftcschr"
  - "strchr"
  - "wcschr"
  - "_tcschr"
  - "_mbschr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcschr - функция"
  - "_mbschr - функция"
  - "_mbschr_l - функция"
  - "_tcschr - функция"
  - "знаки [C++], поиск в строках"
  - "ftcschr - функция"
  - "mbschr - функция"
  - "mbschr_l - функция"
  - "strchr - функция"
  - "строки [C++], поиск"
  - "tcschr - функция"
  - "wcschr - функция"
ms.assetid: 2639905d-e983-43b7-b885-abef32cfac43
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# strchr, wcschr, _mbschr, _mbschr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Находит символ в строке, используя текущий языковой стандарт или указанную категорию состояния преобразования LC\_CTYPE.  
  
> [!IMPORTANT]
>  `_mbschr` и `_mbschr_l` невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *strchr(  
   const char *str,  
   int c   
);  // C only  
char *strchr(  
   char * str,  
   int c   
); // C++ only  
const char *strchr(  
   const char * str,  
   int c   
); // C++ only  
wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
); // C only  
wchar_t *wcschr(  
   wchar_t *str,  
   wchar_t c   
);  // C++ only  
const wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
);  // C++ only  
unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C only  
unsigned char *_mbschr(  
   unsigned char *str,  
   unsigned int c   
); // C++ only  
const unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C++ only  
unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C only   
unsigned char *_mbschr_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 `str`  
 Исходная строка, завершающаяся символом NULL.  
  
 `c`  
 Символ, который требуется найти.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на первое вхождение `c` в `str` или `NULL`, если `c` не найден.  
  
## Заметки  
 Функция `strchr` находит первое вхождение `c` в `str` или возвращает `NULL`, если `c` не найден.  Нулевой конечный символ включен в поиск.  
  
 `wcschr`, `_mbschr` и `_mbschr_l` являются версиями функции `strchr` для расширенных и многобайтовых символов.  Аргументы и возвращаемое значение `wcschr` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbschr` представляют собой многобайтовые строки.  `_mbschr` распознает последовательности многобайтовых символов.  Кроме того, если строка — нулевой указатель, `_mbschr` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то `_mbschr` возвращает `NULL` и устанавливает `errno` в `EINVAL`.  `strchr` и `wcschr` не проверяют свои параметры.  В остальных случаях эти три функции ведут себя идентично.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В языке C эти функции принимают указатель `const` для первого аргумента.  В языке C\+\+ доступны две перегрузки.  Перегрузка, принимающая указатель на `const`, возвращает указатель на `const`; версия, которая принимает указатель на не являющийся `const`, возвращает указатель на не `const`.  Макрос \_CONST\_CORRECT\_OVERLOADS определен, если доступны и `const` и не `const` версии этих функций.  Если требуется не `const` функциональность для обеих перегрузок C\+\+, укажите символ \_CONST\_RETURN.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcschr`|`strchr`|`_mbschr`|`wcschr`|  
|**\_n\/a**|**Н\/Д**|`_mbschr_l`|**Н\/Д**|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strchr`|\<string.h\>|  
|`wcschr`|\<string.h\> или \<wchar.h\>|  
|`_mbschr`, `_mbschr_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strchr.c  
//   
// This program illustrates searching for a character  
// with strchr (search forward) or strrchr (search backward).  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int  ch = 'r';  
  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int result;  
  
   printf_s( "String to be searched:\n      %s\n", string );  
   printf_s( "      %s\n      %s\n\n", fmt1, fmt2 );  
   printf_s( "Search char:   %c\n", ch );  
  
   // Search forward.   
   pdest = strchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   first %c found at position %d\n",   
              ch, result );  
   else  
      printf_s( "Result:   %c not found\n", ch );  
  
   // Search backward.   
   pdest = strrchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   last %c found at position %d\n", ch, result );  
   else  
      printf_s( "Result:\t%c not found\n", ch );  
}  
```  
  
  **String to be searched:**  
 **The quick brown dog jumps over the lazy fox**  
 **1         2         3         4         5**  
 **12345678901234567890123456789012345678901234567890**  
**Search char:   r**  
**Result:   first r found at position 12**  
**Result:   last r found at position 30**   
## Эквивалент в .NET Framework  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../Topic/strcspn,%20wcscspn,%20_mbscspn,%20_mbscspn_l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strstr, wcsstr, \_mbsstr, \_mbsstr\_l](../../c-runtime-library/reference/strstr-wcsstr-mbsstr-mbsstr-l.md)