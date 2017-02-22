---
title: "_mbsnbset_s, _mbsnbset_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbset_s"
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
  - "mbsnbset_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbset_s - функция"
  - "_mbsnbset_s_l - функция"
  - "_tcsnset_s - функция"
  - "_tcsnset_s_l - функция"
  - "mbsnbset_s - функция"
  - "mbsnbset_s_l - функция"
  - "tcsnset_s - функция"
  - "tcsnset_s_l - функция"
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _mbsnbset_s, _mbsnbset_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает для первых `n` байтов строки многобайтовых символов значение указанного символа.  Эти версии функции [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md) отличаются повышенной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t _mbsnbset_s(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count   
);  
errno_t _mbsnbset_s_l(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbset_s(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbset_s_l(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 `str`  
 Строка, которую требуется изменить.  
  
 `size`  
 Размер строкового буфера.  
  
 `c`  
 Однобайтовый или многобайтовый параметр.  
  
 `count`  
 Число байтов, которые нужно задать.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Ноль в случае успешного выполнения; в противном случае — код ошибки.  
  
## Заметки  
 Функции `_mbsnbset_s` и `_mbsnbset_s_l` устанавливают максимум первые несколько байт \(`count`\) `str` до `c`.  Если значение `count` больше длины строки `str`, вместо параметра `count` используется длина строки `str`.  Если `c` является многобайтовым символом и не помещается полностью в последний байт, установленный параметром `count`, последний байт дополняется символом пробела.  `_mbsnbset_s` и `_mbsnbset_s_l` не добавляют завершающий символ null в конце `str`.  
  
 `_mbsnbset_s` и `_mbsnbset_s_l` напоминают `_mbsnset` за тем исключением, что задают количество байт `count`, а не количество символов `count` для параметра `c`.  
  
 Если `str` имеет значение `NULL` или значение `count` равно нулю, эта функция создает исключение недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает значение `NULL`.  Кроме того, если `c` не является допустимым многобайтовым символом, вместо него используется пробел, а параметру `errno` присваивается значение `EINVAL`.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Версия `_mbsnbset_s` этой функции использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; версия `_mbsnbset_s_l` работает аналогично, но использует переданный языковой стандарт.  Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в статье [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Чтобы отключить это поведение, используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsnset_s`|`_strnset_s`|`_mbsnbset_s`|`_wcsnset_s`|  
|`_tcsnset_s_l`|`_strnset_s _l`|`_mbsnbset_s_l`|`_wcsnset_s_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mbsnbset_s`|\<mbstring.h\>|  
|`_mbsnbset_s_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_mbsnbset_s.c  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset_s( string, sizeof(string), '*', 4 );  
   printf( "After:  %s\n", string );  
}  
```  
  
## Вывод  
  **До: это тест**  
**После: \*\*\*\* — это тест**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)