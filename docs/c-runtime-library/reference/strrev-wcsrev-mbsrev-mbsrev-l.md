---
title: "_strrev, _wcsrev, _mbsrev, _mbsrev_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsrev"
  - "_mbsrev"
  - "_strrev"
  - "_mbsrev_l"
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
  - "_strrev"
  - "_ftcsrev"
  - "_tcsrev"
  - "mbsrev"
  - "mbsrev_l"
  - "_wcsrev_fstrrev"
  - "_mbsrev"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsrev - функция"
  - "_mbsrev - функция"
  - "_mbsrev_l - функция"
  - "_strrev - функция"
  - "_tcsrev - функция"
  - "_wcsrev - функция"
  - "знаки [C++], изменение порядка"
  - "знаки [C++], переключение"
  - "ftcsrev - функция"
  - "mbsrev - функция"
  - "mbsrev_l - функция"
  - "обращение знаков в строки"
  - "строки [C++], обращение порядка"
  - "strrev - функция"
  - "tcsrev - функция"
  - "wcsrev - функция"
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _strrev, _wcsrev, _mbsrev, _mbsrev_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Меняет порядок символов в строке на обратный.  
  
> [!IMPORTANT]
>  `_mbsrev` и `_mbsrev_l` не могут использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *_strrev(  
   char *str   
);  
wchar_t *_wcsrev(  
   wchar_t *str   
);  
unsigned char *_mbsrev(  
   unsigned char *str   
);  
unsigned char *_mbsrev_l(  
   unsigned char *str,  
   _locale_t locale   
);  
```  
  
#### Параметры  
 `str`  
 Строка, заканчивающаяся нулевым символом, для изменения порядка символов.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Возвращает указатель на измененную строку.  Нет зарезервированных возвращаемых значений для указания ошибки.  
  
## Заметки  
 Функция `_strrev` обращает порядок символов в `string`.  Завершающий нулевой символ остается на месте.  `_wcsrev` и `_mbsrev` — двубайтовая и многобайтовая символьные версии `_strrev`.  Аргументы и возвращаемое значение `_wcsrev` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbsrev` представляют собой многобайтовые строки.  Для `_mbsrev` порядок байтов в каждом многобайтовом символе `string` не изменяется.  В остальных случаях эти три функции ведут себя идентично.  
  
 `_mbsrev` проверяет свои параметры.  Если либо `string1`, либо `string2` является указателем на null, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то `_mbsrev` возвращает `NULL` и устанавливает `errno` в `EINVAL`.  `_strrev` и `_wcsrev` не проверяют свои параметры.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций с суффиксом `_l` идентичны версиям без суффикса, за исключением того, что версии с суффиксом `_l` используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
> [!IMPORTANT]
>  Эти функции могут быть подвержены угрозам переполнения буфера.  Переполнение буфера можно использовать для атак на систему, поскольку оно может привести к несанкционированному повышению уровня привилегий.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsrev`|`_strrev`|`_mbsrev`|`_wcsrev`|  
|**Н\/Д**|**Н\/Д**|`_mbsrev_l`|**Н\/Д**|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strrev`|\<string.h\>|  
|`_wcsrev`|\<string.h\> или \<wchar.h\>|  
|`_mbsrev`, `_mbsrev_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strrev.c  
// This program checks a string to see  
// whether it is a palindrome: that is, whether  
// it reads the same forward and backward.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* string = "Able was I ere I saw Elba";  
   int result;  
  
   // Reverse string and compare (ignore case):  
   result = _stricmp( string, _strrev( _strdup( string ) ) );  
   if( result == 0 )  
      printf( "The string \"%s\" is a palindrome\n", string );  
   else  
      printf( "The string \"%s\" is not a palindrome\n", string );  
}  
```  
  
  **The string "Able was I ere I saw Elba" is a palindrome**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)