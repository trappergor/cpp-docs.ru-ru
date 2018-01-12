---
title: "strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcscoll
- _mbscoll
- _mbscoll_l
- strcoll
- _strcoll_l
- _wcscoll_l
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
- wcscoll
- _mbscoll
- _tcscoll
- _ftcscoll
dev_langs: C++
helpviewer_keywords:
- code pages, using for string comparisons
- mbscoll function
- wcscoll_l function
- ftcscoll function
- wcscoll function
- _strcoll_l function
- tcscoll function
- _ftcscoll function
- _tcscoll function
- _wcscoll_l function
- _mbscoll function
- strcoll_l function
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e65837945b8c28ee0968dbeaded4fbdbf7e79c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="strcoll-wcscoll-mbscoll-strcolll-wcscolll-mbscolll"></a>strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l
Сравнивает строки с помощью текущего языкового стандарта или заданной категории состояния преобразования LC_COLLATE.  
  
> [!IMPORTANT]
>  Функции `_mbscoll` и `_mbscoll_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int strcoll(  
   const char *string1,  
   const char *string2   
);  
int wcscoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _strcoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale   
);  
int wcscoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale   
);  
int _mbscoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `string1`, `string2`  
 Строки с завершающим нулем для сравнения.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает значение, показывающее связь между `string1` для `string2`, как показано ниже.  
  
|Возвращаемое значение|Отношение string1 к string2|  
|------------------|----------------------------------------|  
|< 0|`string1` меньше `string2`|  
|0|`string1` идентично `string2`|  
|> 0|`string1` больше `string2`|  
  
 Каждая из этих функций возвращает `_NLSCMPERROR` в случае ошибки. Чтобы использовать функцию `_NLSCMPERROR`, включите STRING.H или MBSTRING.H. `wcscoll` может завершиться ошибкой, если `string1` или `string2` имеет значение NULL или содержит коды расширенных символов, не входящие в последовательность сортировки. При возникновении ошибки `wcscoll` может присвоить параметру `errno` значение `EINVAL`. Чтобы убедиться, не возникает ли ошибка при вызове функции `wcscoll`, присвойте параметру `errno` значение 0 и проверьте `errno` после вызова функции `wcscoll`.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций сравнивает с учетом регистра строки `string1` и `string2` в соответствии с используемой в настоящее время кодовой страницей. Эти функции следует использовать только в том случае, когда есть различие между порядком символов в наборе и лексикографическим порядком символов в текущей кодовой странице и данное различие представляет интерес во время сравнения строк.  
  
 Все эти функции проверяют свои параметры. Если параметр `string1` или `string2` является пустым указателем либо значение `count` больше `INT_MAX`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции возвращают `_NLSCMPERROR` и устанавливают для `errno` значение `EINVAL`.  
  
 Сравнение двух строк — это операция, зависящая от языкового стандарта, так как каждый языковой стандарт теперь имеет разные правила для сортировки символов. Версии этих функций без суффикса `_l` используют текущий языковой стандарт потока для данного поведения, зависимого от языкового стандарта. Версии с суффиксом `_l` идентичны соответствующей функции без суффикса, однако они используют переданный языковой стандарт в качестве параметра вместо текущего языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscoll`|`strcoll`|`_mbscoll`|`wcscoll`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strcoll`|\<string.h>|  
|`wcscoll`|\<wchar.h>, \<string.h>|  
|`_mbscoll`, `_mbscoll_l`|\<mbstring.h>|  
|`_strcoll_l`|\<string.h>|  
|`_wcscoll_l`|\<wchar.h>, \<string.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)