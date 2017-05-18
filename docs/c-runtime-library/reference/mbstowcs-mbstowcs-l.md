---
title: "mbstowcs, _mbstowcs_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbstowcs
- _mbstowcs_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbstowcs
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_l function
- mbstowcs_l function
- mbstowcs function
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 436e581907e3b651716e819a9c82a24eed2e4b8e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="mbstowcs-mbstowcsl"></a>mbstowcs, _mbstowcs_l
Преобразует последовательность многобайтовых символов в соответствующую последовательность расширенных символов. Существуют более безопасные версии этих функций; см. раздел [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 [выходной] `wcstr`  
 Адрес последовательности расширенных символов.  
  
 [in] `mbstr`  
 Адрес последовательности многобайтовых символов, заканчивающейся нуль-символом.  
  
 [in] `count`  
 Наибольшее число многобайтовых символов для преобразования.  
  
 [in] `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если функция `mbstowcs` успешно преобразовывает исходную строку, возвращается число преобразованных многобайтовых символов. Если аргумент `wcstr` имеет значение `NULL`, функция возвращает необходимый размер (в расширенных символах) строки назначения. Если `mbstowcs` встречает недопустимый Многобайтовый символ, возвращается значение -1. Если возвращаемое значение равно `count`, строка расширенных символов не заканчивается нуль-символом.  
  
> [!IMPORTANT]
>  Убедитесь, что строки `wcstr` и `mbstr` не перекрываются, и что параметр `count` правильно отражает количество преобразуемых многобайтовых символов.  
  
## <a name="remarks"></a>Примечания  
 Функция `mbstowcs` преобразовывает не более `count` многобайтовых символов, указанных в параметре `mbstr`, в строку соответствующих расширенных символов, определяемых текущим языковым стандартом. Он сохраняет результирующая строка расширенных символов по адресу, представленного `wcstr`. Результат аналогичен последовательности вызовов функции `mbtowc`. Если функция `mbstowcs` встречает однобайтовый нуль-символ ("\0") в позиции, меньшей или равной `count` символов, она преобразует нуль-символ в расширенный нуль-символ (L"\0") и останавливается. Таким образом, строка расширенных символов в параметре `wcstr` заканчивается нуль-символом только в том случае, если нуль-символ встречается во время преобразования. Если последовательности, на которые указывают параметры `wcstr` и `mbstr`, перекрываются, то поведение не определено.  
  
 Если аргумент `wcstr` имеет значение `NULL`, функция `mbstowcs` возвращает количество расширенных символов, которые получились бы в результате преобразования, не включающего конечный нуль-символ. Чтобы возвращалось правильное значение, исходная строка должна заканчиваться нуль-символом. Если требуется, чтобы результирующая строка расширенных символов завершалась нуль-символом, добавьте его к возвращаемому значению.  
  
 Если аргумент `mbstr` имеет значение `NULL` или `count` > `INT_MAX`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр errno устанавливается в значение `EINVAL`, и функция возвращает –1.  
  
 Функция `mbstowcs` использует текущий языковой стандарт для любых аспектов поведения, зависящих от языкового стандарта; функция `_mbstowcs_l` идентична за исключением того, что она использует переданный языковой стандарт. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`mbstowcs`|\<stdlib.h>|  
|`_mbstowcs_l`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
Locale information set to Japanese_Japan.932  
Convert to multibyte string:  
  Required Size: 4  
  Number of bytes written to multibyte string: 4  
  Hex values of the  multibyte characters: 0x82 0xa0 0x82 0xa1  
  Codepage 932 uses 0x81 to 0x9f as lead bytes.  
  
Convert back to wide-character string:  
  Characters converted: 2  
  Hex value of first 2 wide characters: 0x3042 0x3043  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)
