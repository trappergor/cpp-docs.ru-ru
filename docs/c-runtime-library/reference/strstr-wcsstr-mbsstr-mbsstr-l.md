---
title: "strstr, wcsstr, _mbsstr, _mbsstr_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsstr"
  - "wcsstr"
  - "_mbsstr_l"
  - "strstr"
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
  - "_fstrstr"
  - "_ftcsstr"
  - "strstr"
  - "wcsstr"
  - "_mbsstr"
  - "_tcsstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrstr - функция"
  - "_ftcsstr - функция"
  - "_mbsstr - функция"
  - "_mbsstr_l - функция"
  - "_tcsstr - функция"
  - "fstrstr - функция"
  - "ftcsstr - функция"
  - "mbsstr - функция"
  - "mbsstr_l - функция"
  - "строки [C++], поиск"
  - "strstr - функция"
  - "подстроки, поиск"
  - "tcsstr - функция"
  - "wcsstr - функция"
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# strstr, wcsstr, _mbsstr, _mbsstr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает указатель на первое вхождение строки для поиска в строке.  
  
> [!IMPORTANT]
>  `_mbsstr` и `_mbsstr_l` не могут использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *strstr(  
   const char *str,  
   const char *strSearch   
); // C only  
char *strstr(  
   char *str,  
   const char *strSearch   
); // C++ only  
const char *strstr(  
   const char *str,  
   const char *strSearch   
); // C++ only  
wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C only  
wchar_t *wcsstr(  
   wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
const wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C only  
unsigned char *_mbsstr(  
   unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
const unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C only  
unsigned char *_mbsstr_l(  
   unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 `str`  
 Строка, заканчивающаяся нулевым символом, в которой будет производиться поиск.  
  
 `strSearch`  
 Строка, заканчивающаяся нулевым символом, поиск которой будет производиться.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Возвращает указатель на первое вхождение `strSearch` в `str` или `NULL`, если `strSearch` не появляется в `str`.  Если `strSearch` указывает на строку нулевой длины, то функция возвращает `str`.  
  
## Заметки  
 Функция `strstr` возвращает указатель на первое вхождение `strSearch` в `str`.  Поиск не распространяется на завершающий нулевой символ.  `wcsstr` является версией `strstr` с расширенными символами, а `_mbsstr` — версией с многобайтовыми знаками.  Аргументы и возвращаемое значение `wcsstr` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbsstr` представляют собой многобайтовые строки.  `_mbsstr` проверяет свои параметры.  Если `str` или `strSearch` равно `NULL`, то вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то `_mbsstr` устанавливает `errno` в `EINVAL` и возвращает 0.  `strstr` и `wcsstr` не проверяют свои параметры.  В остальных случаях эти три функции ведут себя идентично.  
  
> [!IMPORTANT]
>  Эти функции могут создать угрозу из проблемы переполнения буфера.  Проблемы переполнения буфера могут использоваться для атаки на систему, поскольку они могут допустить выполнение произвольного кода, который может вызвать произвольное повышение прав доступа.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 В языке C эти функции принимают указатель `const` для первого аргумента.  В языке C\+\+ доступны две перегрузки.  Перегрузка, принимающая указатель на `const`, возвращает указатель на `const`; версия, которая принимает указатель на не `const`, возвращает указатель на не `const`.  Макрос \_CONST\_CORRECT\_OVERLOADS определен, если доступны и `const` и не `const` версии этих функций.  Если требуется не `const` функциональность для обеих перегрузок C\+\+, укажите символ \_CONST\_RETURN.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для этого поведения, зависящего от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**Н\/Д**|**Н\/Д**|`_mbsstr_l`|**Н\/Д**|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strstr`|\<string.h\>|  
|`wcsstr`|\<string.h\> или \<wchar.h\>|  
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strstr.c  
  
#include <string.h>  
#include <stdio.h>  
  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int  result;  
   printf( "String to be searched:\n   %s\n", string );  
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );  
   pdest = strstr( string, str );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "%s found at position %d\n", str, result );  
   else  
      printf( "%s not found\n", str );  
}  
```  
  
  **String to be searched:**  
 **The quick brown dog jumps over the lazy fox**  
 **1         2         3         4         5**  
 **12345678901234567890123456789012345678901234567890**  
**lazy found at position 36**   
## Эквивалент в .NET Framework  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../Topic/strcspn,%20wcscspn,%20_mbscspn,%20_mbscspn_l.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [basic\_string::find](../Topic/basic_string::find.md)