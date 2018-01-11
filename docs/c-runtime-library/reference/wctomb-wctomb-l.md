---
title: "wctomb, _wctomb_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_l
- wctomb
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
f1_keywords: wctomb
dev_langs: C++
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 462fecfcd9400d10dbc943fded0d04fb7a0cf010
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l
Преобразует расширенный символ в соответствующий многобайтовый символ. Существуют более безопасные версии этих функций; см. раздел [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mbchar`  
 Адрес последовательности многобайтовых символов.  
  
 `wchar`  
 Расширенный символ.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если функция `wctomb` преобразует расширенный символ в многобайтовый символ, она возвращает число байтов (которое никогда не превышает `MB_CUR_MAX`) в расширенном символе. Если `wchar` является расширенным нуль-символом (L '\0'), `wctomb` возвращает 1. Если целевой указатель `mbchar` имеет значение NULL, `wctomb` возвращает 0. Если преобразование не поддерживается в текущем языковом стандарте, `wctomb` возвращает -1 и `errno` равно `EILSEQ`.  
  
## <a name="remarks"></a>Примечания  
 Функция `wctomb` преобразует свой аргумент `wchar` в соответствующий многобайтовый символ и сохраняет результат в `mbchar`. Эту функцию можно вызывать из любой точки в любой программе. Функция `wctomb` использует текущий языковой стандарт для любых аспектов поведения, зависящих от языкового стандарта; функция `_wctomb_l` идентична `wctomb` за исключением того, что она использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 `wctomb` проверяет свои параметры. Если параметр `mbchar` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL` и функция возвращает –1.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wctomb`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Эта программа иллюстрирует поведение функции wctomb.  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)