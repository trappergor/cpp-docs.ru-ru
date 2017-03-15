---
title: "wctomb_s _wctomb_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_s_l
- wctomb_s
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
- wctomb_s
- _wctomb_s_l
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 94973bf59580354aed75b8c7a3a154f415060163
ms.lasthandoff: 02/24/2017

---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l
Преобразует расширенный символ в соответствующий многобайтовый символ. Версия функции [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pRetValue`  
 Число байтов или код, указывающий результат.  
  
 [выходной] `mbchar`  
 Адрес последовательности многобайтовых символов.  
  
 [in] `sizeInBytes`  
 Размер буфера `mbchar`.  
  
 [in] `wchar`  
 Расширенный символ.  
  
 [in] `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль в случае успеха или код ошибки в случае неудачи.  
  
 Условия ошибок  
  
|`mbchar`|`sizeInBytes`|Возвращаемое значение|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|>0|`EINVAL`|не изменено|  
|любые|>`INT_MAX`|`EINVAL`|не изменено|  
|any|слишком мало|`EINVAL`|не изменено|  
  
 Если выполняется какое-либо из приведенных выше условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция `wctomb` возвращает значение `EINVAL` и устанавливает параметр `errno` в значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `wctomb_s` преобразует свой аргумент `wchar` в соответствующий многобайтовый символ и сохраняет результат в `mbchar`. Эту функцию можно вызывать из любой точки в любой программе.  
  
 Если функция `wctomb_s` преобразует расширенный символ в многобайтовый символ, она помещает число байтов (которое никогда не превышает `MB_CUR_MAX`) в расширенном символе в целое число со знаком, на которое указывает `pRetValue`. Если `wchar` является расширенным нуль-символом (L '\0'), `wctomb_s` заполняет `pRetValue` символом 1. Если целевой указатель `mbchar` имеет значение NULL, `wctomb_s` помещает 0 в `pRetValue`. Если преобразование невозможно в текущем языковом стандарте, `wctomb_s` помещает –1 в `pRetValue`.  
  
 Функция `wctomb_s` использует текущий языковой стандарт для информации, обусловленной языковыми стандартами; функция `_wctomb_s_l` идентична за исключением того, что она использует переданный языковой стандарт. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h>|  
|`_wctomb_s_l`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Эта программа иллюстрирует поведение функции `wctomb`.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
