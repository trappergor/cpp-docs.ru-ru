---
title: "strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcscoll"
  - "_mbscoll"
  - "_mbscoll_l"
  - "strcoll"
  - "_strcoll_l"
  - "_wcscoll_l"
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
  - "wcscoll"
  - "_mbscoll"
  - "_tcscoll"
  - "_ftcscoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "кодовые страницы, использование для сравнений строк"
  - "Функция mbscoll"
  - "Функция wcscoll_l"
  - "Функция ftcscoll"
  - "Функция wcscoll"
  - "Функция _strcoll_l"
  - "Функция tcscoll"
  - "Функция _ftcscoll"
  - "Функция _tcscoll"
  - "Функция _wcscoll_l"
  - "Функция _mbscoll"
  - "Функция strcoll_l"
  - "Функция strcoll"
  - "строки [C++], сравнение по кодовой странице"
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сравнивает строки, используя текущий языковой стандарт или указанную LC\_COLLATE категорию состояния преобразования.  
  
> [!IMPORTANT]
>  `_mbscoll` и `_mbscoll_l` невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
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
  
#### Параметры  
 `string1`, `string2`  
 Строки с завершающим нулем для сравнения.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает значение, указывающее отношение `string1` к `string2` следующим образом.  
  
|Возвращаемое значение|Отношение string1 к string2|  
|---------------------------|---------------------------------|  
|\< 0|`string1` меньше чем `string2`.|  
|0|`string1` идентична `string2`.|  
|\> 0|`string1` больше чем `string2`.|  
  
 Каждая из этих функций возвращает `_NLSCMPERROR` при ошибке.  Для использования `_NLSCMPERROR` включите либо STRING.H, либо MBSTRING.H.  `wcscoll` может завершиться неудачей, если либо `string1`, либо `string2` имеют значение NULL или содержат коды расширенных символов вне домена сортированной последовательности.  При возникновении ошибки `wcscoll` может установить `errno` в `EINVAL`.  Для проверки ошибок при вызове `wcscoll` установите `errno` в 0 и проверьте `errno` после вызова `wcscoll`.  
  
## Заметки  
 Каждая из этих функций выполняет сравнения с учетом регистра `string1` и `string2` в соответствии с использующейся кодовой страницей.  Эти функции следует использовать только в том случае, когда есть различие между порядком символов в наборе и лексикографическим порядке символов в текущей кодовой странице и данное различие представляет интерес во время сравнения строк.  
  
 Все эти функции производят проверку своих параметров.  Если либо `string1`, либо `string2` является указателем на null или если `count` больше `INT_MAX`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `_NLSCMPERROR` и устанавливают для `errno` значение `EINVAL`.  
  
 Сравнение двух строк — операция, зависимая от языкового стандарта, поскольку каждый языковой стандарт имеет различные правила упорядочивания символов.  Версии этих функций без суффикса `_l` используют языковой стандарт текущего потока для этого поведения, зависящего от языкового стандарта; версии с суффиксом `_l` совпадают с соответствующей функции без суффикса, за исключением того, что они используют языковой стандарт, передаваемый в качестве параметра вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcscoll`|`strcoll`|`_mbscoll`|`wcscoll`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strcoll`|\<string.h\>|  
|`wcscoll`|\<wchar.h\>, \<string.h\>|  
|`_mbscoll`, `_mbscoll_l`|\<mbstring.h\>|  
|`_strcoll_l`|\<string.h\>|  
|`_wcscoll_l`|\<wchar.h\>, \<string.h\>|  
  
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