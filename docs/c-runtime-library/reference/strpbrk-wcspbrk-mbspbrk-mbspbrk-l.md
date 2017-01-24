---
title: "strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft Docs"
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
  - "_mbspbrk"
  - "wcspbrk"
  - "_mbspbrk_l"
  - "strpbrk"
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
  - "_fstrpbrk"
  - "_mbspbrk"
  - "strpbrk"
  - "_tcspbrk"
  - "_ftcspbrk"
  - "wcspbrk"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstrpbrk - функция"
  - "_ftcspbrk - функция"
  - "_mbspbrk - функция"
  - "_mbspbrk_l - функция"
  - "_tcspbrk - функция"
  - "кодировки [C++], сканирование строк на наличие знаков"
  - "знаки [C++], сканирование строк"
  - "fstrpbrk - функция"
  - "ftcspbrk - функция"
  - "mbspbrk - функция"
  - "mbspbrk_l - функция"
  - "строки [C++], сканирование"
  - "strpbrk - функция"
  - "tcspbrk - функция"
  - "wcspbrk - функция"
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: 30
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ищет в строке символы из указанного набора символов.  
  
> [!IMPORTANT]
>  `_mbspbrk` и `_mbspbrk_l` невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C only  
char *strpbrk(  
   char *str,  
   const char *strCharSet   
); // C++ only  
const char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C++ only  
wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C only  
wchar_t *wcspbrk(  
   wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
const wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C only  
unsigned char *_mbspbrk(  
   unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
const unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C only  
unsigned char *_mbspbrk_l(  
   unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char* strCharSet,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 `str`  
 Строка для поиска, завершающаяся символом NULL.  
  
 `strCharSet`  
 Набор символов, завершающийся символом NULL.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Возвращает указатель на первое вхождение любого символа из `strCharSet` в `str` или указатель на `NULL`, если строковые аргументы не имеют общих символов.  
  
## Заметки  
 Функция `strpbrk` возвращает указатель на первое вхождение символа, принадлежащего набору символов `strCharSet`, в `str`.  Поиск не распространяется на завершающий нулевой символ.  
  
 `wcspbrk` и `_mbspbrk` — двубайтовая и многобайтовая символьные версии `strpbrk`.  Аргументы и возвращаемое значение `wcspbrk` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbspbrk` представляют собой многобайтовые строки.  
  
 `_mbspbrk` проверяет свои параметры.  Если `str` или `strCharSet` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то `_mbspbrk` возвращает `NULL` и устанавливает `errno` в `EINVAL`.  `strpbrk` и `wcspbrk` не проверяют свои параметры.  В остальных случаях эти три функции ведут себя идентично.  
  
 `_mbspbrk` аналогична `_mbscspn` за исключением того, что `_mbspbrk` возвращает указатель, а не значение типа [size\_t](../../c-runtime-library/standard-types.md).  
  
 В языке C эти функции принимают указатель `const` для первого аргумента.  В языке C\+\+ доступны две перегрузки.  Перегрузка, принимающая указатель на `const`, возвращает указатель на `const`; версия, которая принимает указатель на не являющийся `const`, возвращает указатель на не `const`.  Макрос \_CONST\_CORRECT\_OVERLOADS определен, если доступны и `const` и не `const` версии этих функций.  Если требуется не `const` функциональность для обеих перегрузок C\+\+, укажите символ \_CONST\_RETURN.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версия с суффиксом `_l` идентична, за исключением того, что она использует переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|  
|**Н\/Д**|**Н\/Д**|`_mbspbrk_l`|**Н\/Д**|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strpbrk`|\<string.h\>|  
|`wcspbrk`|\<string.h\> или \<wchar.h\>|  
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strpbrk.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";  
   char *result = NULL;  
  
   // Return pointer to first digit in "string".  
   printf( "1: %s\n", string );  
   result = strpbrk( string, "0123456789" );  
   printf( "2: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "3: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "4: %s\n", result );  
}  
```  
  
  **1: The 3 men and 2 boys ate 5 pigs**  
**2: 3 men and 2 boys ate 5 pigs**  
**3: 2 boys ate 5 pigs**  
**4: 5 pigs**   
## Эквивалент в .NET Framework  
 [System::String::IndexOfAny](https://msdn.microsoft.com/en-us/library/system.string.indexofany.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../Topic/strcspn,%20wcscspn,%20_mbscspn,%20_mbscspn_l.md)   
 [strchr, wcschr, \_mbschr, \_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)