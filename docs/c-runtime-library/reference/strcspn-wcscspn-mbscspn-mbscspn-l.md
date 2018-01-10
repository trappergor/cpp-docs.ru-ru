---
title: "strcspn, wcscspn, _mbscspn, _mbscspn_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbscspn_l
- wcscspn
- _mbscspn
- strcspn
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strcspn
- _mbscspn
- wcscspn
- _ftcscspn
- _tcscspn
dev_langs: C++
helpviewer_keywords:
- strings [C++], searching
- ftcscspn function
- strcspn function
- _mbscspn function
- mbscspn_l function
- wcscspn function
- tcscspn function
- _ftcscspn function
- _mbscspn_l function
- mbscspn function
- _tcscspn function
ms.assetid: f73f51dd-b533-4e46-ba29-d05c553708a6
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83f11196d55392a776a0270032894ce9f486b7a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="strcspn-wcscspn-mbscspn-mbscspnl"></a>strcspn, wcscspn, _mbscspn, _mbscspn_l
Возвращает индекс первого вхождения в строке символа, который относится к набору символов.  
  
> [!IMPORTANT]
>  Функции `_mbschr` и `_mbschr_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t strcspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcscspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbscspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbscspn_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `str`  
 Строка, завершающаяся символом NULL, для поиска.  
  
 `strCharSet`  
 Набор символов, завершающийся символом NULL.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эти функции возвращают индекс первого символа в `str`, который находится в `strCharSet`. Если ни один из символов в `str` не находится в `strCharSet`, то возвращаемое значение представляет собой длину `str`.  
  
 Нет зарезервированных возвращаемых значений для указания ошибки.  
  
## <a name="remarks"></a>Примечания  
 Функции `wcscspn` и `_mbscspn` являются версиями функции `strcspn` для расширенных и многобайтовых символов. Аргументы `wcscspn` представляют собой двухбайтовые строки; аргументы `_mbscspn` представляют собой многобайтовые строки.  
  
 `_mbscspn` проверяет свои параметры. Если параметр `str` или `strCharSet` является пустым указателем, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает 0 и устанавливает `errno` в значение `EINVAL`. Функции `strcspn` и `wcscspn` не проверяют свои параметры. В остальном эти три функции ведут себя идентично.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данного поведения, зависимого от языкового стандарта. Версии с суффиксом `_l` идентичны, однако они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscspn`|`strcspn`|`_mbscspn`|`wcscspn`|  
|`n/a`|`n/a`|`_mbscspn_l`|`n/a`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strcspn`|\<string.h>|  
|`wcscspn`|\<string.h> или \<wchar.h>|  
|`_mbscspn`, `_mbscspn_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_strcspn.c  
  
#include <string.h>  
#include <stdio.h>  
  
void test( const char * str, const char * strCharSet )  
{  
   int pos = strcspn( str, strCharSet );  
   printf( "strcspn( \"%s\", \"%s\" ) = %d\n", str, strCharSet, pos );      
}  
  
int main( void )  
{  
   test( "xyzbxz", "abc" );  
   test( "xyzbxz", "xyz" );  
   test( "xyzbxz", "no match" );  
   test( "xyzbxz", "" );  
   test( "", "abc" );  
   test( "", "" );  
}  
```  
  
```Output  
strcspn( "xyzbxz", "abc" ) = 3  
strcspn( "xyzbxz", "xyz" ) = 0  
strcspn( "xyzbxz", "no match" ) = 6  
strcspn( "xyzbxz", "" ) = 6  
strcspn( "", "abc" ) = 0  
strcspn( "", "" ) = 0  
```  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)