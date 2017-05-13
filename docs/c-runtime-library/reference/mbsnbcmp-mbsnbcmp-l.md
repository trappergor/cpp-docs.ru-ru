---
title: "_mbsnbcmp, _mbsnbcmp_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbcmp
- _mbsnbcmp_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsnbcmp
- tcsnbmp
- _mbsnbcmp_l
- mbsnbcmp_l
- _mbsnbcmp
dev_langs:
- C++
helpviewer_keywords:
- mbsnbcmp_l function
- mbsnbcmp function
- tcsncmp function
- _mbsnbcmp_l function
- _tcsncmp function
- _mbsnbcmp function
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
caps.latest.revision: 23
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 9fdaa428d5772c0622ca4c2f08c64fb376173240
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="mbsnbcmp-mbsnbcmpl"></a>_mbsnbcmp, _mbsnbcmp_l
Сравнивает первые `n` байт двух строк многобайтовых символов.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `string1, string2`  
 Строки для сравнения.  
  
 `count`  
 Число байтов для сравнения.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение отражает порядковую взаимосвязь подстрок `string1` и `string`.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|< 0|Подстрока `string1` меньше, чем подстрока `string2`.|  
|0|Подстрока `string1` идентична подстроке `string2`.|  
|> 0|Подстрока `string1` больше, чем подстрока `string2`.|  
  
 При ошибке проверки параметра функции `_mbsnbcmp` и `_mbsnbcmp_l` возвращают ошибку `_NLSCMPERROR`, которая определена в \<string.h> и \<mbstring.h>.  
  
## <a name="remarks"></a>Примечания  
 Функции `_mbsnbcmp` сравнивают не более чем `count` первых байт в `string1` и `string2` и возвращают значение, указывающее отношение между подстроками. `_mbsnbcmp` — чувствительная к регистру версия `_mbsnbicmp`. В отличие от `_mbsnbcoll`, на функцию `_mbsnbcmp` не влияет порядок сортировки языкового стандарта. Функция `_mbsnbcmp` распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой [кодовой страницей](../../c-runtime-library/code-pages.md).  
  
 Функция `_mbsnbcmp` похожа на `_mbsncmp` за тем исключением, что `_mbsncmp` сравнивает строки посимвольно, а не побайтно.  
  
 На выходное значение влияет настройка категории `LC_CTYPE` языкового стандарта, которая определяет начальные и конечные байты многобайтовых символов. Дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функция `_mbsnbcmp` использует текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта. Функция `_mbsnbcmp_l` идентична за исключением того, что она использует вместо этого параметр `locale`. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если `string1` или `string2` является указателем NULL, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `_NLSCMPERROR` и устанавливают для параметра `errno` значение `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|---------------------------------------|--------------------|-----------------------|  
|`_tcsncmp`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcmp`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
|`_tcsncmp_l`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcml`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_mbsnbcmp`|\<mbstring.h>|  
|`_mbsnbcmp_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_mbsnbcmp.c  
#include <mbstring.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n          %s\n", string1 );  
   printf( "          %s\n\n", string2 );  
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );  
   result = _mbsncmp( string1, string2 , 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );  
   result = _mbsnicmp( string1, string2, 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
Compare strings:  
          The quick brown dog jumps over the lazy fox  
          The QUICK brown fox jumps over the lazy dog  
  
Function: _mbsnbcmp (first 10 characters only)  
Result:   String 1 is greater than string 2  
  
Function: _mbsnicmp _mbsnicmp (first 10 characters only)  
Result:   String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbicmp, _mbsnbicmp_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
