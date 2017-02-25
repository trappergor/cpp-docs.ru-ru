---
title: "mbstowcs, _mbstowcs_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "mbstowcs"
  - "_mbstowcs_l"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbstowcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbstowcs_l - функция"
  - "mbstowcs - функция"
  - "mbstowcs_l - функция"
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# mbstowcs, _mbstowcs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразование последовательности многобайтовых символов в соответствующую последовательность расширенных символов.  Существуют более безопасные версии этих функций; см. раздел [mbstowcs\_s, \_mbstowcs\_s\_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md).  
  
## Синтаксис  
  
```  
size_t mbstowcs(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count   
);  
size_t _mbstowcs_l(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t mbstowcs(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _mbstowcs_l(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `wcstr`  
 Адрес последовательности расширенных символов.  
  
 \[входящий\] `mbstr`  
 Адрес последовательности многобайтовых символов, заканчивающейся нуль\-символом.  
  
 \[входящий\] `count`  
 Наибольшее число многобайтовых символов для преобразования.  
  
 \[входящий\] `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Если `mbstowcs` успешно преобразовывает исходную строку, она возвращает число преобразованных многобайтовых символов.  Если аргумент `wcstr` равен `NULL`, функция возвращает необходимый размер \(в расширенных символах\) строки назначения.  Если `mbstowcs` встречает недопустимый многобайтовый символ, возвращается \-1.  Если возвращаемое значение равно `count`, строка расширенных символов не заканчивается символом null.  
  
> [!IMPORTANT]
>  Убедитесь, что `wcstr` и `mbstr` не перекрываются, и что `count` правильно отражает количество многобайтовых символов для преобразования.  
  
## Заметки  
 Функция `mbstowcs` преобразовывает до максимального количества `count` многобайтовых символов, указанных в `mbstr`, в строку соответствующих расширенных символов, определенных текущим языковым стандартом.  Она сохраняет результирующую строку расширенных символов по адресу, представленному в `wcstr`*.* Результат аналогичен ряду вызовов `mbtowc`.  Если `mbstowcs` встречает однобайтовый нуль\-символ \('\\0'\) либо перед, либо после `count` символов, она конвертирует нуль\-символ в расширенный нуль\-символ и останавливается.  Таким образом, строка расширенных символов в `wcstr` заканчивается нуль\-символом, только если нуль\-символ встречается во время преобразования.  Если последовательности, на которые указывают `wcstr` и `mbstr`, перекрываются, то поведение не определено.  
  
 Если аргумент `wcstr` равен `NULL`, то `mbstowcs` возвращает количество расширенных символов, которые были бы результатом преобразования, не включающего конечный нуль\-символ.  Исходная строка должна завершаться нуль\-символом, чтобы возвращалось корректное значение.  Если требуется, чтобы результирующая строка расширенных символов завершалась нуль\-символом, добавьте его к возвращаемому значению.  
  
 Если аргумент `mbstr` равен `NULL`, или если `count` равен \> `INT_MAX`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, errno принимает значение `EINVAL`, и функция возвращает \-1.  
  
 `mbstowcs` использует текущий языковой стандарт для любых расширений, зависящих от языкового стандарта; `_mbstowcs_l`  идентична за исключением того, что она использует переданный языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`mbstowcs`|\<stdlib.h\>|  
|`_mbstowcs_l`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_mbstowcs.c  
// compile with: /W3  
// illustrates the behavior of the mbstowcs function  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main( void )  
{  
    size_t size;  
    int nChar = 2; // number of characters to convert  
    int requiredSize;  
  
    unsigned char    *pmbnull  = NULL;  
    unsigned char    *pmbhello = NULL;  
    char* localeInfo;  
  
    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters  
    wchar_t *pwc;  
  
    /* Enable the Japanese locale and codepage */  
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");  
    printf("Locale information set to %s\n", localeInfo);  
  
    printf( "Convert to multibyte string:\n" );  
  
    requiredSize = wcstombs( NULL, pwchello, 0); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    printf("  Required Size: %d\n", requiredSize);  
  
    /* Add one to leave room for the null terminator. */  
    pmbhello = (unsigned char *)malloc( requiredSize + 1);  
    if (! pmbhello)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    if (size == (size_t) (-1))  
    {  
        printf("Couldn't convert string. Code page 932 may"  
                " not be available.\n");  
        return 1;  
    }  
    printf( "  Number of bytes written to multibyte string: %u\n",  
            (unsigned int) size );  
    printf( "  Hex values of the " );  
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",  
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );  
    printf( "  Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");  
  
    printf( "Convert back to wide-character string:\n" );  
  
    /* Assume we don't know the length of the multibyte string.  
     Get the required size in characters, and allocate enough space. */  
  
    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996  
    /* Add one to leave room for the NULL terminator */  
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));  
    if (! pwc)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996  
    if (size == (size_t) (-1))  
    {  
       printf("Couldn't convert string--invalid multibyte character.\n");  
    }  
    printf( "  Characters converted: %u\n", (unsigned int)size );  
    printf( "  Hex value of first 2" );  
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );  
    free(pwc);  
    free(pmbhello);  
}  
```  
  
  **Locale information set to Japanese\_Japan.932**  
**Convert to multibyte string:**  
 **Required Size: 4**  
 **Number of bytes written to multibyte string: 4**  
 **Hex values of the  multibyte characters: 0x82 0xa0 0x82 0xa1**  
 **Codepage 932 uses 0x81 to 0x9f as lead bytes.**  
**Convert back to wide\-character string:**  
 **Characters converted: 2**  
 **Hex value of first 2 wide characters: 0x3042 0x3043**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)   
 [wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)