---
title: "_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strncoll"
  - "_mbsncoll_l"
  - "_wcsncoll"
  - "_wcsncoll_l"
  - "_mbsncoll"
  - "_strncoll_l"
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
  - "mbsncoll_l"
  - "strncoll"
  - "_wcsncoll"
  - "_tcsnccoll"
  - "_ftcsnccoll"
  - "wcsncoll"
  - "_mbsncoll"
  - "wcsncoll_l"
  - "strncoll_l"
  - "_ftcsncoll"
  - "_strncoll"
  - "_tcsncoll"
  - "mbsncoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsnccoll"
  - "_ftcsncoll - функция"
  - "_mbsncoll - функция"
  - "_mbsncoll_l - функция"
  - "_strncoll - функция"
  - "_strncoll_l - функция"
  - "_tcsnccoll - функция"
  - "_tcsncoll - функция"
  - "_wcsncoll - функция"
  - "_wcsncoll_l - функция"
  - "кодовые страницы, использование для сравнений строк"
  - "ftcsnccoll - функция"
  - "ftcsncoll - функция"
  - "mbsncoll - функция"
  - "mbsncoll_l - функция"
  - "строки [C++], сравнение по кодовой странице"
  - "strncoll - функция"
  - "strncoll_l - функция"
  - "tcsnccoll - функция"
  - "tcsncoll - функция"
  - "wcsncoll - функция"
  - "wcsncoll_l - функция"
ms.assetid: e659a5a4-8afe-4033-8e72-17ffd4bdd8e9
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сравнивает строки на основе данных языкового стандарта.  
  
> [!IMPORTANT]
>  `_mbsncoll` и `_mbsncoll_l` нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _strncoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsncoll(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strncoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsncoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsncoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `string1, string2`  
 Строки с завершающим нулем для сравнения.  
  
 `count`  
 Число сравниваемых символов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает значение, идентифицирующее отношение между подстроками `string1` и `string2`, как показано ниже.  
  
|Возвращаемое значение|Отношение string1 к string2|  
|---------------------------|---------------------------------|  
|\< 0|Значение `string1` меньше `string2`.|  
|0|Функция `string1` идентична функции `string2`.|  
|\> 0|Значение `string1` больше значения `string2`.|  
  
 Каждая из этих функций возвращает `_NLSCMPERROR`.  Чтобы использовать функцию `_NLSCMPERROR`, включите STRING.h или MBSTRING.h.  `_wcsncoll` может завершиться ошибкой, если `string1` или `string2` содержит коды расширенных символов, не входящие в последовательность сортировки.  При возникновении ошибки `_wcsncoll` может присвоить параметру `errno` значение `EINVAL`.  Чтобы проверить, не возникает ли ошибка при вызове функции `_wcsncoll`, присвойте параметру `errno` значение 0 и проверьте `errno` после вызова функции `_wcsncoll`.  
  
## Заметки  
 Каждая из этих функций сравнивает с учетом регистра первые несколько символов в строках `string1` и `string2` на основе кодовой страницы, используемой в данный момент \(количество сравниваемых символов определяется параметром `count`\).  Используйте эти функции для сравнения строк только в том случае, если есть различие между порядком символов в наборе и лексикографическим порядком символов в текущей кодовой странице и это различие представляет интерес при сравнении строк.  Порядок символов в наборе зависит от языкового стандарта.  В версиях этих функций без суффикса `_l` используется текущий языковой стандарт, а в версиях с суффиксом `_l` — переданный параметр языкового стандарта.  Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Все эти функции проверяют свои параметры.  Если параметр `string1` или `string2` является пустым указателем либо значение `count` больше `INT_MAX`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `_NLSCMPERROR` и устанавливают для `errno` значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsnccoll`|`_strncoll`|`_mbsncoll`|`_wcsncoll`|  
|`_tcsncoll`|`_strncoll`|[\_mbsnbcoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsncoll`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strncoll`, `_strncoll_l`|\<string.h\>|  
|`_wcsncoll`, `_wcsncoll_l`|\<wchar.h\> или \<string.h\>|  
|`_mbsncoll`, `_mbsncoll_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## См. также  
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)