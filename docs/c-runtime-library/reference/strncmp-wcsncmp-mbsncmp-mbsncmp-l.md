---
title: "strncmp, wcsncmp, _mbsncmp, _mbsncmp_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- strncmp
- _mbsncmp
- wcsncmp
- _mbsncmp_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsnccmp
- _ftcsncmp
- _tcsncmp
- _tcsnccmp
- strncmp
- _mbsncmp
- wcsncmp
dev_langs:
- C++
helpviewer_keywords:
- _tcsnccmp function
- ftcsncmp function
- wcsncmp function
- _ftcsncmp function
- _mbsncmp function
- tcsncmp function
- mbsncmp function
- _mbsncmp_l function
- mbsncmp_l function
- strncmp function
- strings [C++], comparing characters of
- string comparison [C++], strncmp function
- _tcsncmp function
- tcsnccmp function
- ftcsnccmp function
- characters [C++], comparing
- _ftcsnccmp function
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92ec6c3c6a28258ffc953fc9c7f5a344e1f3d0f9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strncmp-wcsncmp-mbsncmp-mbsncmpl"></a>strncmp, wcsncmp, _mbsncmp, _mbsncmp_l
Сравнивает символы двух строк вплоть до указанного количества.  
  
> [!IMPORTANT]
>  Функции `_mbsncmp` и `_mbsncmp_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int strncmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int wcsncmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsncmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,   
   _locale_t locale  
);int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `string1, string2`  
 Строки для сравнения.  
  
 `count`  
 Число сравниваемых символов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение отражает взаимосвязь подстрок `string1` и `string2`, как показано ниже.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|< 0|Подстрока `string1` меньше, чем подстрока `string2`.|  
|0|Подстрока `string1` идентична подстроке `string2`.|  
|> 0|Подстрока `string1` больше, чем подстрока `string2`.|  
  
 При ошибке проверки параметров функции `_mbsncmp` и `_mbsncmp_l` возвращают ошибку `_NLSCMPERROR`, которая определена в \<string.h> и \<mbstring.h>.  
  
## <a name="remarks"></a>Примечания  
 Функция `strncmp` выполняет порядковое сравнение не более чем `count` первых символов в `string1` и `string2` и возвращает значение, указывающее отношение между подстроками. `strncmp` — чувствительная к регистру версия `_strnicmp`. `wcsncmp` и `_mbsncmp` — чувствительные к регистру версии `_wcsnicmp` и `_mbsnicmp`.  
  
 Функции `wcsncmp` и `_mbsncmp` являются версиями функции `strncmp` для расширенных и многобайтовых символов. Аргументы `wcsncmp` представляют собой двухбайтовые строки; аргументы `_mbsncmp` представляют собой многобайтовые строки. `_mbsncmp` распознает последовательности многобайтовых символов в соответствии с многобайтовой кодовой страницей и возвращает `_NLSCMPERROR` при ошибке.  
  
 Кроме того, функции `_mbsncmp` и `_mbsncmp_l` проверяют свои параметры. Если параметр `string1` или `string2` является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, то функции `_mbsncmp` и `_mbsncmp_l` возвращают ошибку `_NLSCMPERROR` и устанавливают для `errno` значение `EINVAL`. Функции `strncmp` и `wcsncmp` не проверяют свои параметры. В остальном эти функции ведут себя одинаково.  
  
 Способ сравнения `_mbsncmp` и `_mbsncmp_l` зависит от настройки категории `LC_CTYPE` языкового стандарта. Эта категория определяет обнаружение начальных и конечных байтов в многобайтовых символах. Дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функция `_mbsncmp` использует текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта. Функция `_mbsncmp_l` идентична за исключением того, что она использует вместо этого параметр `locale`. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md). Если языковой стандарт является однобайтовым, поведение этих функций идентично поведению `strncmp`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsnccmp`|`strncmp`|`_mbsncmp`|`wcsncmp`|  
|`_tcsncmp`|`strncmp`|`_mbsnbcmp`|`wcsncmp`|  
|`_tccmp`|Сопоставляется макросу или встроенной функции|`_mbsncmp`|Сопоставляется макросу или встраиваемой функции|  
|**Неприменимо**|**Неприменимо**|`_mbsncmp_l`|**Неприменимо**|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strncmp`|\<string.h>|  
|`wcsncmp`|\<string.h> или \<wchar.h>|  
|`_mbsncmp`, `_mbsncmp_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_strncmp.c  
#include <string.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n      %s\n      %s\n\n",  
           string1, string2 );  
   printf( "Function:   strncmp (first 10 characters only)\n" );  
   result = strncmp( string1, string2 , 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n\n", tmp );  
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );  
   result = _strnicmp( string1, string2, 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
      The quick brown dog jumps over the lazy fox  
      The QUICK brown fox jumps over the lazy dog  
  
Function:   strncmp (first 10 characters only)  
Result:      String 1 is greater than string 2  
  
Function:   strnicmp _strnicmp (first 10 characters only)  
Result:      String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_mbsnbicmp, _mbsnbicmp_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)