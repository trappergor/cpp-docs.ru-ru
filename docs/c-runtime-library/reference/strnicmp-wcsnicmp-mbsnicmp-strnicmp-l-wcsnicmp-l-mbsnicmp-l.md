---
title: "_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsnicmp"
  - "_strnicmp_l"
  - "_wcsnicmp_l"
  - "_strnicmp"
  - "_mbsnicmp"
  - "_mbsnicmp_l"
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
  - "wcsnicmp_l"
  - "_strnicmp"
  - "_ftcsnicmp"
  - "mbsnicmp_l"
  - "_ftcsncicmp"
  - "mbsnicmp"
  - "_tcsncicmp"
  - "_mbsnicmp"
  - "_tcsnicmp"
  - "strnicmp_l"
  - "_wcsnicmp"
  - "_wcsnicmp_l"
  - "CORECRT_WSTRING/_wcsnicmp"
  - "CORECRT_WSTRING/_wcsnicmp_l"
  - "string/_strnicmp"
  - "string/_strnicmp_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsncicmp - функция"
  - "_ftcsnicmp - функция"
  - "_mbsnicmp - функция"
  - "_mbsnicmp_l - функция"
  - "_strnicmp - функция"
  - "_strnicmp_l - функция"
  - "_tcsncicmp - функция"
  - "_tcsnicmp - функция"
  - "_wcsnicmp - функция"
  - "_wcsnicmp_l - функция"
  - "знаки [C++], сравнение"
  - "ftcsncicmp - функция"
  - "ftcsnicmp - функция"
  - "mbsnicmp - функция"
  - "mbsnicmp_l - функция"
  - "сравнение строк [C++], строчные буквы"
  - "сравнение строк [C++], strncmp - функция"
  - "строки [C++], сравнение символов"
  - "strncmp - функция"
  - "strnicmp_l - функция"
  - "tcsncicmp - функция"
  - "tcsnicmp - функция"
  - "wcsnicmp - функция"
  - "wcsnicmp_l - функция"
ms.assetid: df6e5037-4039-4c85-a0a6-21d4ef513966
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сравнивает указанное количество символов двух строк без учета регистра.  
  
> [!IMPORTANT]
>  `_mbsnicmp` и `_mbsnicmp_l` нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _strnicmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsnicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicmp_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicmp_l(  
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
 Отражает связь между подстроками указанным ниже образом.  
  
|Возвращаемое значение|Описание|  
|---------------------------|--------------|  
|\< 0|Подстрока `string1` меньше, чем подстрока `string2`.|  
|0|Подстрока `string1` идентична подстроке `string2`.|  
|\> 0|Подстрока `string1` больше, чем подстрока `string2`.|  
  
 При ошибке проверки параметра эти функции возвращают значение `_NLSCMPERROR`, которое определено в \<string.h\> и \<mbstring.h\>.  
  
## Заметки  
 Функция `_strnicmp` выполняет порядковое сравнение не более `count` первых символов строк `string1` и `string2`.  Сравнение выполняется без учета регистра путем преобразования каждого символа в нижний регистр.  `_strnicmp` — не чувствительная к регистру версия `strncmp`.  Сравнение заканчивается, если был достигнут завершающий нуль\-символ в любой из строк до того, как были сравнены `count` симв.  Если строки равны, когда завершающий нуль\-символ достигается в любой из строк до того, как `count` симв. сравнены, более короткая строка считается меньшей.  
  
 Символы от 91 до 96 в таблице ASCII \("\[", "\\", "\]", "^", "\_" и "\`"\) оцениваются как меньшие по сравнению с любым алфавитным символом.  Такое упорядочение идентично используемому функцией `stricmp`.  
  
 Функции `_wcsnicmp` и `_mbsnicmp` являются версиями функции `_strnicmp` для расширенных и многобайтовых символов.  Аргументы `_wcsnicmp` представляют собой двухбайтовые строки; аргументы `_mbsnicmp` представляют собой многобайтовые строки.  `_mbsnicmp` распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой кодовой страницей и возвращает `_NLSCMPERROR` при ошибке.  Для получения дополнительной информации см. [Кодовые страницы](../../c-runtime-library/code-pages.md).  В остальном эти три функции ведут себя идентично.  На эти функции влияет настройка языкового стандарта: версии без суффикса `_l` используют текущий языковой стандарт для зависящего от языкового стандарта поведения; версии с суффиксом `_l` используют переданный в них параметр `locale`.  Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Все эти функции проверяют свои параметры.  Если параметр `string1` или `string2` является пустым указателем, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `_NLSCMPERROR` и устанавливают для `errno` значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsncicmp`|`_strnicmp`|`_mbsnicmp`|`_wcsnicmp`|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsncicmp_l`|`_strnicmp_l`|`_mbsnicmp_l`|`_wcsnicmp_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strnicmp`, `_strnicmp_l`|\<string.h\>|  
|`_wcsnicmp`, `_wcsnicmp_l`|\<string.h\> или \<wchar.h\>|  
|`_mbsnicmp`, `_mbsnicmp_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример для функции [strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md).  
  
## Эквивалент в .NET Framework  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)